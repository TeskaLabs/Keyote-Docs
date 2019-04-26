---
layout: default
title: Keyote documentation
sidebar: keyote
---

Keyote documentation
=======================

Welcome!

Keyote enables you to use a smartphone as a security token e.g. for secure remote access and digital signing. 


## Smartphone as a Security Token

_A security token is a physical device that acts as an electronic key.
The token is used in addition to or in place of a password._  
--- [Wikipedia](https://en.wikipedia.org/wiki/Security_token)

One very common example of the security token is a smard card,
the card used to secure access to office building etc.

Nearly every modern smartphone contains a special security chip today. Apple has Security Enclave, and Android introduced Trusted Execution Environment respective TrustZone. If your phone has a fingerprint reader or other biometric authorization, then it must also contain this security chip. Keyote leverages abilities of this security chip to turn the smartphone in a security token.

In the case of a smartphone, security is further enhanced by a biometric authentication. It means that a user must approve the use of private keys by Keyote by a fingerprint or Face ID. It is safer protection against a smart card or token protected only by PIN.

Keyote app generates an private key and pairs with one or more computers. Paired computers may request operations using the key such that the private key never leaves the smartphone.


## Quick start

<div class="container mt-5">
	<div class="row">
		<div class="col-sm">
			<a href="{{ site.url }}/start/install" class="btn btn-outline-primary btn-lg w-100">
				<div>
					<i class="fas fa-download"></i>
					<div class="cell-text">Install</div>
				</div>
			</a>
		</div>
		<div class="col-sm">
			<a href="{{ site.url }}/start/pair" class="btn btn-outline-primary btn-lg w-100">
				<div>
					<i class="fas fa-glass-cheers"></i>
					<div class="cell-text">Pair</div>
				</div>
			</a>
		</div>
		<div class="col-sm">
			<a href="{{ site.url }}/start/use" class="btn btn-outline-primary btn-lg w-100">
				<div>
					<i class="fas fa-user-shield"></i>
					<div class="cell-text">Use</div>
				</div>
			</a>
		</div>
	</div>
</div>
