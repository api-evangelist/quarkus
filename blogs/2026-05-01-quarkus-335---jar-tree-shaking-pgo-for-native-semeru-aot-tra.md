---
title: "Quarkus 3.35 - JAR tree-shaking, PGO for native, Semeru AOT, @Transactional for Hibernate Reactive, and more"
url: "https://quarkus.io/blog/quarkus-3-35-released/"
date: "Fri, 01 May 2026 00:00:00 +0000"
author: "Guillaume Smet (https://twitter.com/gsmet_)"
feed_url: "https://quarkus.io/feed.xml"
---
<div class="paragraph">
<p>We&#8217;re pleased to announce the release of Quarkus 3.35.</p>
</div>
<div class="paragraph">
<p>This release brings several notable features:</p>
</div>
<div class="ulist">
<ul>
<li>
<p><a href="https://github.com/quarkusio/quarkus/pull/53295">#53295</a> - JAR tree-shaking to eliminate unused classes</p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/pull/53278">#53278</a> - Profile-Guided Optimization (PGO) support for native builds</p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/pull/53339">#53339</a> - Semeru AOT support</p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/pull/51063">#51063</a> - Support <code>@Transactional</code> for Hibernate Reactive</p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/pull/53432">#53432</a> - CORS support for the management interface</p>
</li>
<li>
<p><a href="https://github.com/quarkusio/quarkus/pull/52919">#52919</a> - Remove the use of System Properties to propagate configuration in tests</p>
</li>
<li>
<p>New snapshot distribution infrastructure</p>
</li>
</ul>
</div>
<div class="sect1">
<h2 id="update"><a class="anchor" href="#update"></a>Update</h2>
<div class="sectionbody">
<div class="paragraph">
<p>To update to Quarkus 3.35, we recommend updating to the latest version of the Quarkus CLI and run:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="highlightjs highlight"><code class="language-bash hljs">quarkus update</code></pre>
</div>
</div>
<div class="paragraph">
<p>Note that <code>quarkus update</code> can update your applications from any version of Quarkus (including 2.x) to Quarkus 3.35.</p>
</div>
<div class="paragraph">
<p>For more information about the adjustments you need to make to your applications, please refer to the <a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.35">Quarkus 3.35 migration guide</a>.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="whats-new"><a class="anchor" href="#whats-new"></a>What&#8217;s new?</h2>
<div class="sectionbody">
<div class="sect2">
<h3 id="jar-tree-shaking"><a class="anchor" href="#jar-tree-shaking"></a>JAR tree-shaking</h3>
<div class="paragraph">
<p>A new experimental <code>quarkus.package.jar.tree-shake</code> option enables build-time dependency tree-shaking.
When set to <code>classes</code>, Quarkus performs bytecode reachability analysis to identify and exclude unused classes from runtime dependencies, reducing application JAR size.</p>
</div>
<div class="paragraph">
<p>The analysis traces references through supertypes, annotations, <code>ServiceLoader</code> entries, reflective class loading, and more.</p>
</div>
<div class="paragraph">
<p>As an example, running tree-shaking on the Quarkus CLI removes over 6,000 unreachable classes, saving around 18 MB (39.5%).</p>
</div>
<div class="paragraph">
<p>This feature supports <code>fast-jar</code>, <code>uber-jar</code>, <code>legacy-jar</code>, and <code>aot-jar</code> packaging types.</p>
</div>
<div class="paragraph">
<p>As mentioned, this new feature is experimental, and feedback is highly welcome!</p>
</div>
</div>
<div class="sect2">
<h3 id="profile-guided-optimization-for-native-builds"><a class="anchor" href="#profile-guided-optimization-for-native-builds"></a>Profile-guided optimization for native builds</h3>
<div class="paragraph">
<p>You can now opt in to Profile-Guided Optimization (PGO) for native builds by setting <code>quarkus.native.pgo.enabled=true</code>.</p>
</div>
<div class="paragraph">
<p>Note that PGO is a feature of Oracle GraalVM and is not available in GraalVM Community Edition.</p>
</div>
<div class="paragraph">
<p>When enabled, Quarkus uses your integration tests as the workload to profile the application.
The resulting PGO data is then fed into the native compilation for better runtime performance.</p>
</div>
<div class="paragraph">
<p>The implementation follows a similar pattern to the Project Leyden AOT support introduced in Quarkus 3.32.</p>
</div>
</div>
<div class="sect2">
<h3 id="semeru-aot-support"><a class="anchor" href="#semeru-aot-support"></a>Semeru AOT support</h3>
<div class="paragraph">
<p>Building on the Project Leyden AOT integration from Quarkus 3.32, Quarkus now also supports IBM Semeru&#8217;s AOT features.</p>
</div>
<div class="paragraph">
<p>In initial testing on the <code>rest-json</code> quickstart with IBM Semeru Runtime Open Edition 25, startup time was cut roughly in half (from ~380 ms down to ~190 ms).</p>
</div>
<div class="paragraph">
<p>For now, this is limited to building JARs with Semeru AOT, automatic container image building (as available with Leyden) is not yet supported.</p>
</div>
</div>
<div class="sect2">
<h3 id="transactional-for-hibernate-reactive"><a class="anchor" href="#transactional-for-hibernate-reactive"></a><code>@Transactional</code> for Hibernate Reactive</h3>
<div class="paragraph">
<p>Quarkus now supports the <code>@Transactional</code> annotation for Hibernate Reactive, thanks to a new <code>quarkus-reactive-transactions</code> extension.</p>
</div>
<div class="paragraph">
<p>This means you can use the familiar <code>@Transactional</code> annotation on methods that return <code>Uni</code>, and the transaction lifecycle (begin, commit, rollback) will be managed within the reactive pipeline.</p>
</div>
<div class="paragraph">
<p>A few things to keep in mind:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>Only <code>TxType.REQUIRED</code> is currently supported.</p>
</li>
<li>
<p>Mixing <code>@Transactional</code> with <code>@WithTransaction</code> or <code>@WithSessionOnDemand</code> is not allowed.</p>
</li>
<li>
<p>Methods annotated with <code>@Transactional</code> are no longer automatically considered <code>@Blocking</code>. If your method is blocking but returns <code>Uni</code>, you now need an explicit <code>@Blocking</code> annotation. See the <a href="https://github.com/quarkusio/quarkus/wiki/Migration-Guide-3.35">migration guide</a> for details.</p>
</li>
</ul>
</div>
</div>
<div class="sect2">
<h3 id="cors-support-for-the-management-interface"><a class="anchor" href="#cors-support-for-the-management-interface"></a>CORS support for the management interface</h3>
<div class="paragraph">
<p>The management interface now has its own dedicated CORS configuration, allowing you to set CORS policies independently from the main HTTP interface.</p>
</div>
</div>
<div class="sect2">
<h3 id="testing-improvements"><a class="anchor" href="#testing-improvements"></a>Testing improvements</h3>
<div class="paragraph">
<p>The test infrastructure no longer uses System Properties to propagate configuration from Dev Services, Test Resources, and Test Profiles.
This change opens the door for better parallel test execution (which we hope to achieve at some point in the future) and makes the Config system truly immutable.</p>
</div>
<div class="paragraph">
<p>Tests using <code>QuarkusDevModeTest</code>, <code>QuarkusIntegrationTest</code>, or <code>QuarkusMainIntegrationTest</code> can now declare a <code>Config</code> field or method parameter to access the updated configuration.</p>
</div>
</div>
<div class="sect2">
<h3 id="new-snapshot-distribution"><a class="anchor" href="#new-snapshot-distribution"></a>New snapshot distribution</h3>
<div class="paragraph">
<p>Quarkus snapshots are no longer published to Sonatype, which had reliability issues with the volume of artifacts involved.
Snapshots are now published daily as GitHub Releases in the <a href="https://github.com/quarkusio/quarkus-ecosystem-ci/releases">quarkusio/quarkus-ecosystem-ci</a> repository, with version <code>999-SNAPSHOT</code>.
Each release contains a <code>maven-repo.tar.gz</code> asset with pre-built Maven artifacts that you can extract into your local Maven repository.</p>
</div>
<div class="paragraph">
<p>For CI setups, a dedicated <a href="https://github.com/quarkusio/install-quarkus-snapshots-action/">GitHub Action</a> is also available.</p>
</div>
<div class="paragraph">
<p>More details can be found in the <a href="https://github.com/quarkusio/quarkus/blob/main/CONTRIBUTING.md#using-snapshots">Using snapshots</a> section of the contributing guide.</p>
</div>
</div>
<div class="sect2">
<h3 id="jackson-reflection-free-serializers-for-quarkus-rest"><a class="anchor" href="#jackson-reflection-free-serializers-for-quarkus-rest"></a>Jackson reflection-free serializers for Quarkus REST</h3>
<div class="paragraph">
<p>We initially planned to make Jackson reflection-free serializers the default for Quarkus REST in 3.35.
However, thanks to several community members who tested this feature and reported issues, we identified a number of edge cases that still need to be addressed.
We decided to postpone making it the default to 3.36, so that we can fix these issues first.</p>
</div>
<div class="paragraph">
<p>We are very grateful to everyone who took the time to report problems, your feedback is what makes Quarkus better.</p>
</div>
<div class="paragraph">
<p>In the meantime, we very much welcome more testing from our community.
You can enable reflection-free serializers by adding the following property to your configuration:</p>
</div>
<div class="listingblock">
<div class="content">
<pre class="highlightjs highlight"><code class="language-properties hljs">quarkus.rest.jackson.optimization.enable-reflection-free-serializers=true</code></pre>
</div>
</div>
<div class="paragraph">
<p>Please report any issues you encounter on <a href="https://github.com/quarkusio/quarkus/issues">GitHub</a>.</p>
</div>
</div>
<div class="sect2">
<h3 id="platform-updates"><a class="anchor" href="#platform-updates"></a>Platform updates</h3>
<div class="paragraph">
<p>Various Platform components were upgraded including:</p>
</div>
<div class="ulist">
<ul>
<li>
<p>Camel Quarkus to 3.35.0</p>
</li>
<li>
<p>Quarkus CXF to 3.35.1 - see release notes for <a href="https://docs.quarkiverse.io/quarkus-cxf/dev/release-notes/3.35.0.html">3.35.0</a> and <a href="https://docs.quarkiverse.io/quarkus-cxf/dev/release-notes/3.35.1.html">3.35.1</a></p>
</li>
<li>
<p>Quarkus Amazon Services to 3.18.0</p>
</li>
<li>
<p>Quarkus MCP Server to 1.12.0</p>
</li>
<li>
<p>Quarkus Flow to 0.9.0</p>
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
<p>You can get the full changelog of <a href="https://github.com/quarkusio/quarkus/releases/tag/3.35.0.CR1">3.35.0.CR1</a>, <a href="https://github.com/quarkusio/quarkus/releases/tag/3.35.0">3.35.0</a>, and <a href="https://github.com/quarkusio/quarkus/releases/tag/3.35.1">3.35.1</a> on GitHub.</p>
</div>
</div>
</div>
<div class="sect1">
<h2 id="contributors"><a class="anchor" href="#contributors"></a>Contributors</h2>
<div class="sectionbody">
<div class="paragraph">
<p>The Quarkus community is growing and has now <a href="https://github.com/quarkusio/quarkus/graphs/contributors">1188 contributors</a>.
Many many thanks to each and everyone of them.</p>
</div>
<div class="paragraph">
<p>In particular for the 3.35 release, thanks to Ales Justin, Alexey Loubyansky, andreatp, Andy Damevin, anuragg-saxenaa, Arseni Buinitski, Aurea Munoz, Aurélien Pupier, Bruno Baptista, brunobat, Carles Arnal, Cesar M. Romero-Pedraza, Chris Laprun, Chris Ruffalo, Clement Escoffier, Cristiano Nicolai, DerFrZocker, Dmitri Bourlatchkov, Faisal Dilawar, Foivos Zakkak, George Gastaldi, Georgios Andrianakis, Guillaume Smet, Holly Cummins, Inaki Villar, Jakub Jedlicka, Jamal Dabari, Jan Martiska, Jens Teglhus Møller, Julien Ponge, Karm Michal Babacek, Katia Aresti, keshavprashatdeshpande, Ladislav Thon, lberrymage, Luca Molteni, marco sappe griot, mariofusco, marko-bekhta, Martin Kouba, Matej Novotny, Matej Vašek, Max Rydahl Andersen, Maximilian Zellhofer, Melloware, Michael Edgar, Michal Maléř, Michal Vavřík, Mihajlo Veljković, Nick Robison, Nico Hinrichs, Ozan Gunalp, Paramvir Jindal, Phillip Kruger, Phillip Krüger, PreetiYadav, Robert Toyonaga, Roberto Cortez, Rolfe Dlugy-Hegwer, Rostislav Svoboda, Sergey Beryozkin, Simon Scatton, Simon Scholz, Stéphane Épardaud, Teymur Babayev, Thomas Segismont, tiwari91, Tiziano Basile, tom, xstefank, Yoann Rodière, and Yoshikazu Nojima.</p>
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
