---
title: "Lagom 1.5.0-RC1 released!"
url: "https://www.lagomframework.com/blog/lagom-1-5-0-RC1.html"
date: "2018-11-16T11:00:00.000+11:00"
author: "Renato Cavalcanti"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>We are happy to announce the availability of Lagom 1.5.0-RC1. This is the first release candidate of Lagom 1.5.0. We expect this to be considerably more stable than the milestone releases, not only in terms of functionality but we are also moving closer to the idea of freezing the APIs.</p>
<p>As with milestones, the primary goal is to get feedback, so please let us know if something isn&rsquo;t working or you see something that should be improved. If there are changes not well documented in javadocs, scaladocs or our migration guides, please, let us know so that we can improve them before the general availability release.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<h3><a href="#upgrades-for-play-akka-and-alpakka-kafka" name="upgrades-for-play-akka-and-alpakka-kafka">Upgrades for Play, Akka and Alpakka Kafka</a></h3>
<ul>
  <li>Play upgraded to 2.7.0-RC3 (<a href="https://blog.playframework.com/play-2-7-0-rc3-released/">release notes</a>)</li>
  <li>Akka upgraded to 2.5.18 (<a href="https://akka.io/blog/news/2018/10/07/akka-2.5.18-released">release notes</a>)</li>
  <li>Alpakka Kafka upgraded to 1.0-M1 (<a href="https://doc.akka.io/docs/akka-stream-kafka/current/release-notes/1.0-M1.html">release notes</a>)</li>
</ul>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.5.0-M4...1.5.0-RC1">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/39?closed=1">1.5.0-RC1 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.5.0-RC1</h2>
<p>First, make sure you read the Lagom 1.5 Migration Guide for <a href="https://www.lagomframework.com/documentation/latest/scala/Migration15.html">Scala</a> or <a href="https://www.lagomframework.com/documentation/latest/java/Migration15.html">Java</a>.</p>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author    
      3    103      126  Dale Wijnand
      1     30        8  Ignasi Marimon-Clos
      1      4        4  danielklein45
      1     21       19  Martynas Mickevičius
</code></pre>
