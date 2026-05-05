---
title: "Quarkus 3.33 LTS - new LTS version"
url: "https://quarkus.io/blog/quarkus-3-33-released/"
date: "Wed, 25 Mar 2026 00:00:00 +0000"
author: "Guillaume Smet (https://twitter.com/gsmet_)"
feed_url: "https://quarkus.io/feed.xml"
---
<div class="paragraph">
<p>It is our pleasure to announce the release of Quarkus 3.33, which is our new LTS (Long Term Support) version.</p>
</div>
<div class="paragraph">
<p>This version is built on the top of Quarkus 3.32.
New features landed in <a href="https://quarkus.io/blog/quarkus-3-34-released/">Quarkus 3.34</a>, which was also released today.</p>
</div>
<div class="paragraph">
<p>If you want to know more about our LTS policy, the <a href="https://quarkus.io/blog/lts-releases/">LTS announcement</a> is a must read.</p>
</div>
<div class="paragraph">
<p>LTS releases are supported for 12 months.</p>
</div>
<div class="paragraph">
<p>If you are coming from the previous LTS, Quarkus 3.27 LTS, there are a lot of exciting new features and we recommend reading the following announcements:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="https://quarkus.io/blog/quarkus-3-28-released/">Quarkus 3.28 - More security features, custom Grafana dashboards, support for multiple clients in Liquibase MongoDB, and more</a></p>
</li>
<li>
<p><a href="https://quarkus.io/blog/quarkus-3-29-released/">Quarkus 3.29 - Multiple cache backends and Qute DAP debugger support</a></p>
</li>
<li>
<p><a href="https://quarkus.io/blog/quarkus-3-30-released/">Quarkus 3.30 - JsonView on REST Client, Hibernate Validator 9.1, CLI decrypt command, and more</a></p>
</li>
<li>
<p><a href="https://quarkus.io/blog/quarkus-3-31-released/">Quarkus 3.31 - Full Java 25 support, Quarkus Maven packaging, Panache Next, and more!</a></p>
</li>
<li>
<p><a href="https://quarkus.io/blog/quarkus-3-32-released/">Quarkus 3.32 - Project Leyden integration, more graceful shutdown, automatic Consul registration and more!</a></p>
</li>
</ul>
</div>
<div class="sect1">
<h2 id="update"><a class="anchor" href="#update"></a>Update</h2>
<div class="sectionbody">
<div class="paragraph">
<p>To update to Quarkus 3.33 LTS, we recommend updating to the latest version of the Quarkus CLI and run:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="highlightjs highlight"><code class="language-bash hljs">quarkus update</code></pre>
</div>
</div>
<div class="paragraph">
<p>Note that <code>quarkus update</code> can update your applications from any version of Quarkus (including 2.x) to Quarkus 3.33 LTS.</p>
</div>
<div class="paragraph">
<p>If you are upgrading from 3.32, there&#8217;s nothing to do as 3.33 LTS is the direct continuation of 3.32.</p>
</div>
<div class="paragraph">
<p>If you are upgrading from the previous LTS, Quarkus 3.27 LTS, please refer to the following migration guides:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.28">Migration guide for 3.28</a></p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.29">Migration guide for 3.29</a></p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.30">Migration guide for 3.30</a></p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.31">Migration guide for 3.31</a></p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.32">Migration guide for 3.32</a></p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.33">Migration guide for 3.33</a> - this one is empty as 3.33 is the continuation of 3.32</p>
</li>
</ul>
</div>
<div class="paragraph">
<p>Note that <code>quarkus update</code> should handle most of the heavy lifting for you,
but there are still cases that should be handled manually and we recommend reading these migration guides carefully.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="whats-new"><a class="anchor" href="#whats-new"></a>What&#8217;s new?</h2>
<div class="sectionbody">
<div class="sect2">
<h3 id="platform-component-upgrades"><a class="anchor" href="#platform-component-upgrades"></a>Platform component upgrades</h3>
<div class="paragraph">
<p>Various Platform components were upgraded including:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>Quarkus CXF to 3.33.0 - see <a href="https://docs.quarkiverse.io/quarkus-cxf/dev/release-notes/3.33.0.html">release notes</a></p>
</li>
<li>
<p>Camel Quarkus to 3.33.0</p>
</li>
<li>
<p>Quarkus Operator SDK to 7.7.3</p>
</li>
<li>
<p>Quarkus Vault to 4.7.0</p>
</li>
<li>
<p>Quarkus Qpid JMS to 2.12.0</p>
</li>
</ul>
</div>
</div>
</div>
</div>
<div class="sect1">
<h2 id="full-changelog"><a class="anchor" href="#full-changelog"></a>Full changelog</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The core part of Quarkus 3.33 LTS is based on Quarkus 3.32 with some additional fixes included in 3.33.1.</p>
</div>
<div class="paragraph">
<p>You can get the full changelog of <a href="https://github.com/quarkusio/quarkus/releases/tag/3.33.1">3.33.1</a> on GitHub.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="contributors"><a class="anchor" href="#contributors"></a>Contributors</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The Quarkus community is growing and has now <a href="https://github.com/quarkusio/quarkus/graphs/contributors">1173 contributors</a>.
Many many thanks to each and everyone of them.</p>
</div>
<div class="paragraph">
<p>In particular for the 3.33 release, thanks to Ales Justin, Alexey Loubyansky, Andy Damevin, Asger Askov Blekinge, Aurea Munoz, Aurélien Pupier, brunobat, Clement Escoffier, Clément de Tastes, David M. Lloyd, Dmitri Bourlatchkov, Erwin Oegema, Faisal Dilawar, Foivos Zakkak, Gaelle Fournier, George Gastaldi, Georgios Andrianakis, Guillaume Smet, Holly Cummins, Jakub Jedlicka, jcarranzan, Jens Teglhus Møller, Julien Ponge, Katia Aresti, Kristian Rickert, Ladislav Thon, Luca Molteni, Martin Kouba, Martin Panzer, María Arias de Reyna Domínguez, Matej Novotny, Michal Maléř, Michal Vavřík, Nico Hinrichs, Ozan Gunalp, Patrick Schaub, Phillip Kruger, Roberto Cortez, Sanne Grinovero, Sergey Beryozkin, shjones, Stéphane Épardaud, Thomas McWork, tiwari91, Tom Schindl, and Yoann Rodière.</p>
</div>
<div class="paragraph">
<p>The list is a bit smaller than usual as 3.33 LTS only contains bugfixes on top of 3.32.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="come-join-us"><a class="anchor" href="#come-join-us"></a>Come Join Us</h2>
<div class="sectionbody">
<div class="paragraph">
<p>We value your feedback a lot so please report bugs, ask for improvements&#8230;&#8203; Let&#8217;s build something great together!</p>
</div>
<div class="paragraph">
<p>If you are a Quarkus user or just curious, don&#8217;t be shy and join our welcoming community:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>provide feedback on <a href="https://github.com/quarkusio/quarkus/issues">GitHub</a>;</p>
</li>
<li>
<p>craft some code and <a href="https://github.com/quarkusio/quarkus/pulls">push a PR</a>;</p>
</li>
<li>
<p>discuss with us on <a href="https://quarkusio.zulipchat.com/">Zulip</a> and on the <a href="https://groups.google.com/d/forum/quarkus-dev">mailing list</a>;</p>
</li>
<li>
<p>ask your questions on <a href="https://stackoverflow.com/questions/tagged/quarkus">Stack Overflow</a>.</p>
</li>
</ul>
</div>
</div>
</div>
