---
title: "Lagom 1.4.11 released!"
url: "https://www.lagomframework.com/blog/lagom-1-4-11.html"
date: "2019-02-11T11:00:00.000+11:00"
author: "Marcos Pereira"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>The Lagom team has released Lagom 1.4.11.</p>
<p>This release upgrades Akka to resolve a compatibility problem with Lightbend Orchestration 1.7.3.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<ul>
  <li>Updates Akka to version <a href="https://akka.io/blog/news/2019/01/29/akka-2.5.20-released">2.5.20</a> which stabilizes some APIs and brings bug fixes.</li>
</ul>
<p>If you are a user of <a href="https://developer.lightbend.com/docs/lightbend-orchestration/current/setup/project-setup.html">Lightbend Orchestration</a> you will have to upgrade your dependency of the <code>sbt-reactive-app</code> plugin to <code>1.7.0</code>.</p>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.4.10...1.4.11">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/42?closed=1">1.4.11 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.4.11</h2>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author
1            4        2  Renato Cavalcanti
1           23       10  Ignasi Marimon-Clos
1            1        1  Marcos Pereira
1            3        3  Tim Moore
1           26        7  Dale Wijnand
</code></pre>
