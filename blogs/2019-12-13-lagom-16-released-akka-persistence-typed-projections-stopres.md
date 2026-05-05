---
title: "Lagom 1.6 Released: Akka Persistence Typed, Projections Stop/Resume, Akka Jackson support and more"
url: "https://www.lagomframework.com/blog/lagom-1-6-0.html"
date: "2019-12-13T11:00:00.000+11:00"
author: "Renato Cavalcanti"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>We are happy to announce the availability of Lagom 1.6.0. This is the GA release of Lagom 1.6.0 and is production ready. We invite all our users to upgrade.</p>
<p>This version builds on top of the <a href="https://blog.playframework.com/play-2-8-0-released/">2.8.x series of Play</a> and <a href="https://akka.io/blog/news/2019/11/06/akka-2.6.0-released">Akka 2.6</a>. See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.5.5...1.6.0">full list of commits</a>.</p>
<p>Here’s a list of the most relevant improvements.</p>
<h2><a href="#akka-typed-and-akka-persistence-typed" name="akka-typed-and-akka-persistence-typed">Akka Typed and Akka Persistence Typed</a></h2>
<p>Lagom 1.6 is based on the new Akka 2.6 release and has integrated support for Akka Typed.</p>
<p>As presented in the <a href="https://www.lightbend.com/blog/six-things-architects-should-know-about-akka-2.6">announcement for Akka 2.6</a>, the new Akka Actor APIs (known as Akka Typed) represent a major shift in the Akka ecosystem towards type-safety and more explicit guidance with Actors. We’re happy to bring this to all Lagom users as well.</p>
<p>Lagom includes dependency injection support for typed Actors in Akka 2.6 <a href="https://www.playframework.com/documentation/2.8.x/AkkaTyped#Integrating-with-Akka-Typed">through Play</a>.</p>
<p>While the Lagom Persistence API is still supported and maintained, the new Akka Persistence API (<a href="https://www.lagomframework.com/documentation/1.6.x/scala/UsingAkkaPersistenceTyped.html">Scala</a>/<a href="https://www.lagomframework.com/documentation/1.6.x/java/UsingAkkaPersistenceTyped.html">Java</a>) in Akka 2.6 is now the recommended default for persistence. This provides a more flexible API that gives you more control over some lower-level details while retaining some of the guided approaches that Lagom introduced. Akka Persistence can coexist with existing persistent entities, and the same read-side processor and topic producer APIs fully support both types of entities.</p>
<h2><a href="#jackson-serialization" name="jackson-serialization">Jackson serialization</a></h2>
<p>For Java API, Lagom now uses the Akka Jackson serializer, which is an improved version of the serializer in Lagom 1.5. You can find more information about the Akka Jackson serializer in the <a href="https://doc.akka.io/docs/akka/2.6/serialization-jackson.html">Akka documentation</a>.</p>
<p>It is compatible with Lagom 1.5 in both directions. See our migration guide (<a href="https://www.lagomframework.com/documentation/1.6.x/scala/Migration16.html">Scala</a>/<a href="https://www.lagomframework.com/documentation/1.6.x/java/Migration16.html">Java</a>) for detailed information in case you are upgrading an existing Lagom application.</p>
<p>For Scala API, in addition to <code>play-json</code> support, Akka Jackson serializer is now also supported. Akka Jackson serialization is especially useful when using Akka Persistence Typed API as it allows serialization of <code>ActorRef[T]</code> typically used when encoding command replies.</p>
<h2><a href="#stop-and-resume-projections" name="stop-and-resume-projections">Stop and Resume Projections</a></h2>
<p>Lagom 1.6 has a new API to programmatically stop and resume projections (<a href="https://www.lagomframework.com/documentation/1.6.x/scala/Projections.html">Scala</a>/<a href="https://www.lagomframework.com/documentation/1.6.x/java/Projections.html">Java</a>) (Read Side Processors and Topic Producers) allowing users to control when a projection should start, stop or resume.</p>
<h2>Support for Scala 2.13 and Java 11</h2>
<p>Lagom 1.6 supports the latest Scala version (2.13), LTS Java version (11), and sbt 1.3, as well as the earlier Scala 2.12 and Java 8 versions.</p>
<p>Scala 2.13 brings in a few performance improvements for its collection and async (Future) APIs. Although Java users are not exposed directly to Scala APIs, the Lagom itself is built in Scala and uses many Scala dependencies. That said, updating to Scala v2.13 is also beneficial for Java API users.</p>
<h2><a href="#multiple-changes-in-default-behaviors" name="multiple-changes-in-default-behaviors">Multiple changes in default behaviors</a></h2>
<ul>
  <li>Kafka client defaults to only 1 max inflight request per connection. This can mean a drop in throughput but also increases guarantees against duplication or reordering of messages.</li>
  <li>persistence sharding uses <code>ddata</code> strategy instead of persistence</li>
  <li>JSON compression only triggers for payloads bigger than 32kb</li>
  <li>java.time.* serializes using ISO-8601instead of custom Jackson formats (only affects Java Lagom users)</li>
</ul>
<h2><a href="#migrating-from-previous-versions" name="migrating-from-previous-versions">Migrating from previous versions</a></h2>
<p>This release introduces minimal changes over the <code>1.6.0-RC3</code>. Therefore if you already moved to that version, the upgrade should be trivial. If you are still using Lagom <code>1.5.x</code>, we recommend you first migrate to the latest version available of Lagom 1.5 series and then migrate to Lagom 1.6. If you are using a version older than <code>1.5.x</code>, you should migrate one version at a time. For example: from <code>1.4.9</code> to <code>1.4.15</code> (because <code>1.4.15</code> is <code>1.4.latest</code>), then from <code>1.4.15</code> to <code>1.5.latest</code> and finally to <code>1.6.x</code>. Read the appropriate <a href="https://github.com/lagom/lagom/releases">release notes</a> and migration guides (<a href="https://www.lagomframework.com/documentation/1.6.x/java/Migration16.html">Java</a> / <a href="https://www.lagomframework.com/documentation/1.6.x/scala/Migration16.html">Scala</a>) on each step.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code class="language-text">commits   added  removed  author
    249   25624    14553  Ignasi Marimon-Clos
    202   13607     7824  Renato Cavalcanti
    147    8846     3755  Marcos Pereira
     93    1704     2856  Dale Wijnand
     20     260      178  Tim Moore
     13     534      508  Patrik Nordwall
      6     200      155  Sergey Morgunov
      4      16       10  Alden Torres
      4      39       27  Enno Runne
      3      10        9  Martynas Mickevičius
      2       2        2  Abhiknoldur
      2     755      385  James Roper
      2      35       11  Ruth Stento
      1       3       46  Sethi, Kunal
      1       7        7  Juan Marin Otero
      1       7        7  Matthias Kurz
      1       2        2  Prashant Sharma
      1       0        0  0xflotus
      1       1        1  norfe
      1       0        6  Fabian Grutsch
      1       2        2  Fran Bermejo
      1       1        1  Johannes Rudolph
      1      24        1  Corey Auger
      1      10        0  Zhonglai Zhang
      1      72       60  Michael Liarakos
      1      27        3  Dmitriy Grigoryev
      1      23        1  Stephan Emmerich
      1       2        2  Steve Swing
</code></pre>
