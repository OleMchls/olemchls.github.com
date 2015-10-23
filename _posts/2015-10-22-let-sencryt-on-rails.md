---
layout: post
title: "Let's Encrypt (beta) on rails"
description: ""
tech: true
categories:
  - OpenSource
  - Development
tags:
  - tech
  - heroku
  - rails
  - ssl
---

[Let's Encrypt](https://letsencrypt.org) is here to fix the web with free SSL certificates for everyone, and I hope they will gain a lot of tracing with this! [slidr.io](https://slidr.io/) was choosen as a beta tester. And operates with a Let's Encrypt certificate I want to share how I got through the challenges with my rails app hosted on Heroku and uploaded the certificate.

## Setup
Follow the steps in the [installation instructions](https://letsencrypt.readthedocs.org/en/latest/using.html#installation-and-usage).

## Generating the certificate

```bash
./letsencrypt-auto --agree-dev-preview --server \
      https://acme-v01.api.letsencrypt.org/directory auth
```

The first question is if you'd like the standalone verification or the manual one. I'd go for the `manual` one as I've no access to the "server".

The client will ask you for the domain(s) you want to have included in the certificate.

Next you will be presented with a challenge which looks basically like this:

```bash
Make sure your web server displays the following content at
http://slidr.io/.well-known/acme-challenge/<some hash> before continuing:

{"header": {"alg": "RS256", "jwk": {"e": "AQAB", "kty": "RSA", "n": "..."}}, "payload": "...", "signature": "..."}

Content-Type header MUST be set to application/jose+json.
[...]
Press ENTER to continue
```

*headsup: the url is http, and as of now their client does not follow 30* redirects, also non to https :wink:*

### Passing the challenge with rails
To pass this challenge I've to get my Rails app to respond, here's the change set I've figured out working nicely for me:

```ruby
# config/routes.rb
get '/.well-known/acme-challenge/:id' => 'welcome#letsencrypt'
```

```ruby
# app/controllers/welcome_controller.rb
def letsencrypt
  response.headers["Content-Type"] = "application/jose+json"
  render body: '{"header": {"alg": "RS256", "jwk": {"e": "AQAB", "kty": "RSA", "n": "..."}}, "payload": "...", "signature": "..."}'
end
```

As I mentioned it will not follow redirects, so make sure you **temporarily** disable it.

```ruby
# config/environments/production.rb
config.force_ssl = false
```

## Uploading the certificate to Heroku ssl
After pressing `Enter` and waiting a few secs, I was presentes with the following message

```
IMPORTANT NOTES:
 - Congratulations! Your certificate has been saved at
   /etc/letsencrypt/live/slidr.io/cert.pem and will expire on
   2016-01-20. To obtain a new version of the certificate in the
   future, simply run Let's Encrypt again.
```

Now I had to upload the cert to Heroku:

```bash
sudo heroku certs:update /etc/letsencrypt/live/slidr.io/fullchain.pem /etc/letsencrypt/live/slidr.io/privkey.pem
```

*headsup: it is important that you choose the `fullchain.pem` because otherwise some browsers might mark your site as untrusted.*

That's it already. I hope this little guide helps you too, or gave you some insights how the Let's Encrypt process looks like.

I also want to say a huge THANK YOU to everyone involved with Let's Encrypt it's a great project involving a lots of efforts. You folks rock! <3
