---
title: "Lagom 1.5.0-M3 released!"
url: "https://www.lagomframework.com/blog/lagom-1-5-0-M3.html"
date: "2018-09-04T10:00:00.000+10:00"
author: "Ignasi Marimon-Clos"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>We are happy to announce the availability of Lagom 1.5.0-M3. This new milestone towards the releasing of Lagom 1.5.0 introduces important improvements to support gRPC in Lagom. This release includes Play 2.7.0-M3 and Akka 2.5.16.</p>
<p>Note that this should not be used in production, that Lightbend Orchestration (sbt-reactive-app) does not yet support Lagom 1.5.0-M3, and that ConductR will not be supported for Lagom 1.5.0. Also note that this is an unsupported, pre-release milestone and we don&rsquo;t guarantee API stability or binary compatibility between milestones.</p>
<h2><a href="#highlights" name="highlights">Highlights</a></h2>
<h3><a href="#updates-play-and-akka" name="updates-play-and-akka">Updates Play and Akka</a></h3>
<ul>
  <li>Bump dependencies: Play was bumped to 2.7.0-M3 (<a href="https://blog.playframework.com/play-2-7-0-m3-released/">release notes</a>) and, since Lagom 1.5.0-M2, we&rsquo;ve bumped Akka to 2.5.16 (<a href="https://akka.io/blog/news/2018/08/29/akka-2.5.16-security-fix-released">release notes</a>). See also the <a href="https://akka.io/blog/news/2018/08/24/akka-2.5.15-released">release notes</a> for Akka 2.5.15.</li>
</ul>
<h2><a href="#grpc" name="grpc">gRPC</a></h2>
<p>Lagom 1.5.0-M2 started laying groundwork for integration with <a href="https://github.com/akka/akka-grpc">Akka gRPC</a> to add it as a transport alternative, allowing seamless communication between applications written using Akka, Play, Lagom and other stacks using gRPC.</p>
<p>In this release,the following are introduced as part of the effort to support gRPC:</p>
<ul>
  <li>It is now possible to add additional Play <code>Router</code>s to a Lagom Service (next to the Lagom Router built from the <code>Service.Descriptor</code>). This allows wiring a <a href="https://developer.lightbend.com/docs/akka-grpc/current/play-framework.html">Play router that handles gRPC</a> traffic next to the Lagom router provided out of the box.</li>
  <li>Lagom&rsquo;s Dev Mode now binds an SSL port for each service next to HTTP port already bound. This changes the default behavior in Dev Mode and there’s <a href="https://github.com/lagom/lagom/issues/1537">ongoing effort</a> to restore the default which only binds HTTP and make the use of SSL an opt-in.</li>
</ul>
<p>See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.5.0-M2...1.5.0-M3">full list of commits</a> and the issues and pull requests assigned to the <a href="https://github.com/lagom/lagom/milestone/36?closed=1">1.5.0-M3 milestone</a>.</p>
<h2>Updating a Lagom project to version 1.5.0-M3</h2>
<p>To update an sbt project, change the version of <code>lagom-sbt-plugin</code> in your <code>project/plugins.sbt</code> file.</p>
<p>To update a Maven project, change the <code>lagom.version</code> property in your top-level <code>pom.xml</code>.</p>
<p>After updating, it is recommended to fix any new deprecation warnings you see when compiling or running your services.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits  added  removed  author    
    9    1098     367    Renato Cavalcanti
    6    1469     608    Ignasi Marimon-Clos
    2      40      64    Tim Moore
    2       2       2    kunals201
    2       6       2    Ayush Prashar
    2       9       7    Dale Wijnand
    2      12      11    Marcos Pereira
    1      27      27    Elijah Rippeth
    1       1       1    Jo Vanthournout
    1      16      14    João Guitana
</code></pre>
