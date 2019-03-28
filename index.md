---
layout: default
title: Keyote documentation
sidebar: toc
---

Keyote documentation
=======================

Welcome!

Keyote enables you to use a smartphone as a security token e.g. for secure remote access and digital signing. 


## Smartphone as a Security Token

_A security token is a physical device that acts as an electronic key to something.
The token is used in addition to or in place of a password._  
--- [Wikipedia](https://en.wikipedia.org/wiki/Security_token)

One very common example of the security token is a smard card,
the card used to secure access to office building etc.

Kazdy moderni smartphone ma v dnesni sobe kryptograficky chip.
Zjednodusene reseno, pokud telefon ma ctectu otisku prstu nebo jinou biometrickou autorizaci, pak take musi obsahovat kryptograficky chip.
Keyote vyuziva vlasnosti kryptografickeho chipu smartphone k tomu,
aby bylo mozne telefon pouzivat jako security token.

V pripade smartphone je bezpecnost navic jeste vylepsena moznosti pouzit biometrickou autorizaci.
Znamena to, ze pouziti privatnich klicu z telefonu musi byt potvrzeno pomoci napr. otisku prstu.
Toto je bezpecnejsi ochrana oproti smard card nebo tokenu, kde se bezne pouziva pouze PIN, ktery je mozne napr. odpozorovat.

Keyote app generates an private key and pairs with one or more computers. Paired computers may request operations using the key such that the private key never leaves the smartphone.


## Quick start

<div class="container mt-5">
	<div class="row">
		<div class="col-sm">
			<a href="{{ site.baseurl }}/start/install" class="btn btn-outline-primary btn-lg w-100">
				<div>
					<i class="fas fa-download"></i>
					<div class="cell-text">Install</div>
				</div>
			</a>
		</div>
		<div class="col-sm">
			<a href="{{ site.baseurl }}/start/pair" class="btn btn-outline-primary btn-lg w-100">
				<div>
					<i class="fas fa-glass-cheers"></i>
					<div class="cell-text">Pair</div>
				</div>
			</a>
		</div>
		<div class="col-sm">
			<a href="{{ site.baseurl }}/start/use" class="btn btn-outline-primary btn-lg w-100">
				<div>
					<i class="fas fa-user-shield"></i>
					<div class="cell-text">Use</div>
				</div>
			</a>
		</div>
	</div>
</div>
