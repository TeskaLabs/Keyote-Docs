---
layout: default
title: Install Keyote
permalink: start/install
---

Install Keyote
====================

Keyote consists of two parts: the mobile app and the desktop app.
Please install both of them.

<div class="container mt-5">
	<div class="row">
		<div class="col-sm text-center">
			<h2>iOS</h2>
			<p class="text-danger">Currently available only for invited early users via Testflight.</p>
			<p><img src="{{ site.url }}/assets/images/AppStoreBadge3x.png" style="width: 40%"></p>
			<p>Install the Keyote mobile app from Apple AppStore.</p>
		</div>
		<div class="col-sm text-center">
			<h2>macOS</h2>
			<p>
				<a id="macos-download-url" href="#">
					<i class="fas fa-download fa-3x fa-border"></i>
				</a>
			</p>
			<p>
				Download the Keyote desktop app installer and launch it.
			</p>
		</div>
	</div>
</div>

<div class="container mt-5">
	<div class="row">
		<div class="col-sm-12 text-center">
			<hr />
			<a href="pair">
				Continue to pairing
			</a>
		</div>
	</div>
</div>

<script type="text/javascript">
(function() {
	var jqxhr = $.ajax("https://keyote.blob.core.windows.net/get/macos/latest.json")
	.done(function(data) {
		$('#macos-download-url').attr("href", data.url);
	})
})();
</script>
