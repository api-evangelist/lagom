---
title: "Lagom 1.5.1 and 1.4.12 Released: Akka Service Discovery integration"
url: "https://www.lagomframework.com/blog/lagom-1-5-1-and-1-4-12.html"
date: "2019-04-30T10:00:00.000+10:00"
author: "Renato Cavalcanti"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>The Lagom team has released the versions 1.5.1 and 1.4.12. For a list of the specific changes in Lagom 1.5.1, see the <a href="https://github.com/lagom/lagom/compare/1.5.0...1.5.1">change log (1.5.1)</a>, and for a list of changes in Lagom 1.4.12 see the <a href="https://github.com/lagom/lagom/compare/1.4.11...1.4.12">change log (1.4.12)</a>.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<p>These two releases bring into Lagom a new <code>Service Locator</code> implementation, based on <a href="https://doc.akka.io/docs/akka/2.5/discovery/index.html">Akka&rsquo;s Service Discovery</a>. This component was previously released as an apart library, <a href="https://github.com/lagom/lagom-akka-discovery-service-locator/">lagom-akka-discovery-service-locator</a>, and intended to be a replacement for the Service Locator previously offered by <a href="https://developer.lightbend.com/docs/lightbend-orchestration/current/index.html">Lightbend Orchestration</a>.</p>
<p>In order to allow a smoother transition for Lagom 1.4 users, we decided to include it in 1.4.12 and 1.5.1. So users can choose to first migrate their Lagom 1.4 application to Akka Service Discovery and then to Lagom 1.5. Of course, this is not a required step. It is also possible to migrate directly from Lagom 1.4 and Lightbend Orchestration to Lagom 1.5 and Akka Service Discovery.</p>
<p>For more information, consult the corresponding documentation for Akka Discovery integration:</p>
<ul>
  <li><a href="https://www.lagomframework.com/documentation/1.4.x/java/AkkaDiscoveryIntegration.html">Java API Lagom 1.4</a></li>
  <li><a href="https://www.lagomframework.com/documentation/1.4.x/scala/AkkaDiscoveryIntegration.html">Scala API Lagom 1.4</a></li>
  <li><a href="https://www.lagomframework.com/documentation/1.5.x/java/AkkaDiscoveryIntegration.html">Java API Lagom 1.5</a></li>
  <li><a href="https://www.lagomframework.com/documentation/1.5.x/scala/AkkaDiscoveryIntegration.html">Scala API Lagom 1.5</a></li>
</ul>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release: <em>Renato Cavalcanti</em>, <em>Steve Swing</em>, <em>Ignasi Marimon-Clos</em>, <em>Dale Wijnand</em>, <em>Tim Moore</em>, <em>Alden Torres</em>.</p>
