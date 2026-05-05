---
title: "Lagom 1.4.9 released!"
url: "https://www.lagomframework.com/blog/lagom-1-4-9.html"
date: "2018-11-15T11:00:00.000+11:00"
author: "Ignasi Marimon-Clos"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>The Lagom team has released Lagom 1.4.9.</p>
<p>This release provides a few bug fixes and an improvement.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<ul>
  <li>Updates Akka to <a href="https://akka.io/blog/news/2018/10/07/akka-2.5.18-released">2.5.18</a>. This Akka release introduces few improvements on the DNS implementation. It also improves the cluster membership handling so if you are using Akka&rsquo;s <a href="https://developer.lightbend.com/docs/akka-commercial-addons/current/split-brain-resolver.html">Split Brain Resolver</a> you may want to upgrade.</li>
  <li>Updates Akka HTTP to <a href="https://akka.io/blog/news/2018/09/06/akka-http-10.1.5-10.0.14-security-fix-released">10.0.14</a> with an important security fix. It&rsquo;s is unlikely that as a Lagom user you were exposed to the vulnerability, though.</li>
  <li>Updates Play to <a href="https://blog.playframework.com/play-2-6-20-released/">2.6.20</a> with some minor improvements.</li>
  <li>Fixes <a href="https://github.com/lagom/lagom/issues/1557">a regression</a> on <code>LagomClientFactory</code> introduced on the <code>1.4.x</code> series which was causing a <code>LagomClientFactory</code> running inside a Lagom service to interfere with the service in some scenarios causing failures at boot time.</li>
</ul>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.4.8...1.4.9">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/37?closed=1">1.4.9 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.4.9</h2>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author    
    4       4      10    Dale Wijnand
    3      82      48    Ignasi Marimon-Clos
    2       2       2    Martijn Riemers
    1       1       1    Ravi Thinakkal
    1     506      76    Renato Cavalcanti
</code></pre>
