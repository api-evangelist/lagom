---
title: "Lagom 1.5.0-M4 released!"
url: "https://www.lagomframework.com/blog/lagom-1-5-0-M4.html"
date: "2018-10-15T11:00:00.000+11:00"
author: "Ignasi Marimon-Clos"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>We are happy to announce the availability of Lagom 1.5.0-M4. This new milestone towards the releasing of Lagom 1.5.0 continues to improve support for gRPC in Lagom. This release includes Play 2.7.0-M4, Akka 2.5.17 and Akka-HTTP 10.1.5.</p>
<p>Note that ConductR will not be supported for Lagom 1.5.0. Also note that this is an unsupported, pre-release milestone and we don&rsquo;t guarantee API stability or binary compatibility between milestones.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<h3><a href="#updates-play-and-akka" name="updates-play-and-akka">Updates Play and Akka</a></h3>
<ul>
  <li>Bump dependencies: Play was bumped to 2.7.0-M4 (<a href="https://blog.playframework.com/play-2-7-0-m4-released/">release notes</a>) and, since Lagom 1.5.0-M2, we&rsquo;ve bumped Akka to 2.5.17 (<a href="https://akka.io/blog/news/2018/09/27/akka-2.5.17-released">release notes</a>) and Akka-HTTP to 10.1.5(<a href="https://akka.io/blog/news/2018/09/06/akka-http-10.1.5-10.0.14-security-fix-released">release notes</a>).</li>
</ul>
<h2><a href="#grpc" name="grpc">gRPC</a></h2>
<p>Previous milestones of Lagom 1.5.0 started laying the groundwork for integration with <a href="https://github.com/akka/akka-grpc">Akka gRPC</a> to add it as a transport alternative. In Lagom 1.5.0-M4 we&rsquo;ve improved the Lagom testkit so you can also test the gRPC of your Lagom application.</p>
<p>In this release, the following are introduced as part of the effort to support gRPC:</p>
<ul>
  <li>It is now possible to run the <code>TestServer</code> with SSL enabled and build a gRPC client to interact with the gRPC endpoints offered.</li>
  <li>Lagom 1.5.0-M3 enabled SSL by default in Lagom&rsquo;s Dev Mode. In Lagom 1.5.0-M4 we&rsquo;ve restored the previous behavior where only HTTP is used in Dev Mode and made SSL an Opt-In feature in Dev Mode. Use <code>lagomServiceEnableSsl in ThisBuild := true</code> to start your service with both HTTP and HTTPS ports bound.</li>
</ul>
<h2><a href="#miscellaneous-improvements" name="miscellaneous-improvements">Miscellaneous improvements</a></h2>
<p>This release includes a few other small improvements:</p>
<ul>
  <li><a href="https://github.com/lagom/lagom/issues/1475">1475</a> handle no body as a valid input contributed by Ido Shamun</li>
  <li><a href="https://github.com/lagom/lagom/issues/1572">1572</a> which improves Dev Mode&rsquo;s Service Gateway to stack Host header into X-Forwarded-Host so the target service running behind service Gateway still sees the data sent on the original request.</li>
</ul>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.5.0-M3...1.5.0-M4">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/38?closed=1">1.5.0-M4 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.5.0-M4</h2>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author    
    8     347      94    Ignasi Marimon-Clos
    6     342     242    Dale Wijnand
    4     515      77    Renato Cavalcanti
    2      68      10    Marcos Pereira
    2       2       2    Martijn Riemers
    1       1       1    Ravi Thinakkal
    1     148     146    Kunal sethi
    1     156       2    Ido Shamun
</code></pre>
