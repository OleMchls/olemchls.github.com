---
title: '&#8220;RDBMS&#8221; oder Woaaasssssss?'
author: Ole Michaelis
layout: post
permalink: /2009/rdbms-oder-woaaasssssss/
categories:
  - One Step
tags:
  - Abstrackte Klassen
  - Datenbanken
  - RDBMS
  - Sicherheit
---

Hallo liebe Freunde und Verwandte, jemand anderes erreiche ich hiermit wohl auch kaum.

Nichtsdestotrotz gibt’s will ich jetzt hier zuerst einmal die Überschrift auflösen, RDBMS – **R**elationale **D**aten**b**ank **M**anagement **S**ysteme. Was eine Datenbank ist denke ich brauche ich jetzt nicht mehr zu erwähnen. Aber, was ist ein Datenbank Management System, diese System verwaltet, Daten (ohohoh, wer hätte das gedacht) in so genannten Tabellen, diese können eine Beziehung zueinander haben (deshalb ist das DBMS auch Relational) und das Management System trennt Daten, Rechten und Struktur – ist also doch gar nicht so schwer.

Nun möchte ich hier noch einen kleinen Ein- bzw. Überblick über die verschiedenen Möglichkeiten eine abstrakte Datenbankklasse zu erstellen geben.

Die 3 die ich jetzt hier vorstellen will sind:

*   Ad Hoc Abfragen
*   Active Record Pattern
*   Mapper Pattern

**Ad Hoc- Abfragen** kennt wohl jeder, wenn auch nicht unter diesem namen, auch diejenigen die noch nicht wirklich viel mit OOP in PHP zu tun gehabt haben. Wir bauen uns einen query und schicken Ihn direkt an die Datenbank und verarbeiten dann das Ergebnis. Dieses verfahren nutzen wir in der Firma auch. Über Sinn und Unsinn lässt sich sicherlich streiten aber diese Methode ist auf jedenfall am flexibelsten.

**Active Record Pattern**, hier wird es jetzt langsam spannen, wir haben eine Klasse und diese Klasse beinhaltet Methoden für den Datenbankzugriff. Also beispielsweise haben wir die Klasse User, diese hat dann die Methoden save und load und vielleicht sogar delete. Dann brauchen wir dem Objekt nur noch beim Aufruf der Methode die User ID zu übergeben und haben sonst nichts mehr mit der DB abfrage zu tun.

**Mapper Pattern**, es geht noch abstrakter wir bauen eine Klasse z.B. User wie in dem Beispiel von eben, diesmal hat aber auch die Methode User keinerlei Zugriff au die Datenbank. Es giebt eine weitere Klasse, sozusagen einer Helfer-klasse die der Klasse User die Datenbank abfragen abnimmt. Nennen wir sie UserMapper, diese behält dann die Methoden save, load und delete. Das hat den Vorteil das wenn wir die DB Struktur ändern nur noch an der Mapperklasse etwas geändert werden muss. Ich empfinde diese Methode hat eindeutig zu viel Overhead.

Dann habe ich heute noch ein wenig über die Sicherheit von Passwörtern, Usern und Sessions gelernt, aber das war eigentlich mehr eine Wiederholung. Denn wer 3 jahrelang an die 400 Arztpraxen in HH betreut hat die alle (ich meine wirklich ALLE) das selbe Passwort hatten, dann hat man sich bereits genug mit dem Thema befasst. Allerdings wurde noch eine Methode vorgestellt die sichere Passwörter erzeugt, aber euch geht es bestimmt so wie mir. Diese selbst generierten Passwörter kann sich doch eh keine Sau merken.

So long…

