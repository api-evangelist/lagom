---
title: "Lagom 1.5.0-RC2 released!"
url: "https://www.lagomframework.com/blog/lagom-1-5-0-RC2.html"
date: "2019-02-25T11:00:00.000+11:00"
author: "Marcos Pereira"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>We are happy to announce the availability of Lagom 1.5.0-RC2. This is the second release candidate of Lagom 1.5.0. We expect this to be considerably more stable than the milestone releases, not only in terms of functionality but we are also moving closer to the idea of freezing the APIs. Our plan is to later promote this release candidate to a stable release if we don&rsquo;t find major issues.</p>
<p>Because of that, and as with milestones, the primary goal is to get feedback, so please let us know if something isn&rsquo;t working or you see something that should be improved. If there are changes not well documented in javadocs, scaladocs or our migration guides, please, let us know so that we can improve them before the general availability release.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<h3><a href="#deployment" name="deployment">Deployment</a></h3>
<p>Since version <code>1.5.0-RC2</code> Lagom no longer supports <a href="https://developer.lightbend.com/docs/lightbend-orchestration/current/">Lightbend Orchestration</a>. If you depend on Lightbend Orchestration to produce your <code>Dockerfile</code> and deployment specs (Kubernetes or DC/OS) refer to the <a href="https://www.lagomframework.com/documentation/latest/scala/Migration15.html">Lagom 1.5 Migration Guide</a>.</p>
<p>If your deployment target is OpenShift you can also refer to the <a href="https://developer.lightbend.com/guides/openshift-deployment/">Deploying Lightbend applications to OpenShift</a> guide.</p>
<h3><a href="#upgrades-for-major-dependencies" name="upgrades-for-major-dependencies">Upgrades for major dependencies</a></h3>
<ul>
  <li>Play upgraded to 2.7.0 (<a href="https://blog.playframework.com/play-2-7-0-is-here/">release notes</a>)</li>
  <li>Akka upgraded to 2.5.21 (<a href="https://akka.io/blog/news/2019/02/13/akka-2.5.21-released">release notes</a>, but we also recommend that you read other release notes since Akka 2.5.18)</li>
  <li>Alpakka Kafka upgraded to 1.0-RC2 (<a href="https://doc.akka.io/docs/akka-stream-kafka/current/release-notes/1.0-RC2.html">release notes</a>)</li>
  <li>Slick upgraded to 3.3.0 (<a href="http://slick.lightbend.com/news/2019/01/30/slick-3.3.0-released.html">release notes</a>)</li>
</ul>
<p>There is also a brand new integration with <a href="https://developer.lightbend.com/docs/akka-management/current/">Akka Management</a> providing an easier way to do cluster bootstrap, health-checks enabled by default, and works better with our <a href="https://github.com/lagom/akka-discovery-service-locator">new implementation of ServiceLocator</a> based on <a href="https://doc.akka.io/docs/akka/2.5/discovery/index.html">Akka Discovery</a>.</p>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.5.0-RC1...1.5.0-RC2">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/44?closed=1">1.5.0-RC2 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.5.0-RC2</h2>
<p>First, make sure you read the Lagom 1.5 Migration Guide for <a href="https://www.lagomframework.com/documentation/latest/scala/Migration15.html">Scala</a> or <a href="https://www.lagomframework.com/documentation/latest/java/Migration15.html">Java</a>.</p>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author
     13    767      362   Renato Cavalcanti
      7   1090      697   Ignasi Marimon-Clos
      4    176      100   Marcos Pereira
      2      6        5   Martynas Mickevičius
      2     55       36   Dale Wijnand
      1     10        0   Zhonglai Zhang
      1     24       18   Enno
      1      2        2   Fran Bermejo
      1      2        2   Prashant Sharma
</code></pre>
