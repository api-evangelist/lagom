---
title: "Lagom 1.4.10 released!"
url: "https://www.lagomframework.com/blog/lagom-1-4-10.html"
date: "2019-01-11T11:00:00.000+11:00"
author: "Ignasi Marimon-Clos"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>The Lagom team has released Lagom 1.4.10.</p>
<p>This release upgrades Play (and transitively upgrades Akka and Akka HTTP) and Scala.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<ul>
  <li>Updates Play to <a href="https://blog.playframework.com/play-2-6-21-released//">2.6.21</a> with some minor improvements. This upgrade transitively upgrades Akka and Akka HTTP. Make sure you review Play&rsquo;s announcement for details.</li>
</ul>
<p>If you are a user of <a href="https://developer.lightbend.com/docs/lightbend-orchestration/current/setup/project-setup.html">Lightbend Orchestration</a> you will have to upgrade your dependency of the <code>sbt-reactive-app</code> plugin to <code>1.6.1</code>.</p>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.4.9...1.4.10">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/41?closed=1">1.4.10 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.4.10</h2>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author    
      2     673     661  Ignasi Marimon-Clos
      1      28      28  Dale Wijnand
      1       2       2  Fran Bermejo
</code></pre>
