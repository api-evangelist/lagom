---
title: "Lagom 1.5 Released: Akka Management, Kubernetes, OpenShift, gRPC, Couchbase and more"
url: "https://www.lagomframework.com/blog/lagom-1-5-0.html"
date: "2019-04-16T10:00:00.000+10:00"
author: "Ignasi Marimon-Clos"
feed_url: "https://www.lagomframework.com/blog/atom.xml"
---
<p>We are happy to announce the availability of Lagom 1.5.0. This is the GA release of Lagom 1.5.0 and is production ready. We invite all our users to upgrade.</p>
<p>This version builds on top of the <a href="https://blog.playframework.com/play-2-7-0-is-here/">2.7.x series of Play</a>, <a href="https://akka.io/blog/news/2019/02/28/alpakka-kafka-1.0-released">Alpakka Kafka 1.0</a>, and the latest improvements on Akka and Akka Management. See GitHub for the <a href="https://github.com/lagom/lagom/compare/1.4.11...1.5.0">full list of commits</a>. </p>
<p>Here’s a list of the most relevant improvements.</p>
<h2><a href="#akka-management" name="akka-management">Akka Management</a></h2>
<p><a href="https://developer.lightbend.com/docs/akka-management/current/">Akka Management</a> is a suite of tools for operating Akka powered applications. Akka Management uses a dedicated HTTP port to expose a few routes allowing remote inspection of the state of the Akka Actor System. For example, if the process is a member of an Akka Cluster, these endpoints will report if the node already joined the cluster.</p>
<p>Lagom exposes the Akka Management HTTP port out of the box. Lagom will add Health Check routes by default. You can reuse library provided health checks or plugin your own. For example, Lagom uses cluster status to determine when the node is healthy. This is called Cluster Membership Check and is provided by the Akka Cluster HTTP Management library.</p>
<p>Another improvement Lagom 1.5 introduces, thanks to the adoption of Akka Management, is the simpler, <strong>more robust cluster formation via <a href="https://developer.lightbend.com/docs/akka-management/current/bootstrap/">Akka Cluster Bootstrap</a></strong>. Instead of using a static list of seed nodes or relying on convoluted custom scripts to build the list of seed nodes dynamically, Cluster Bootstrap discovers the existing nodes via plugins adapting Akka Cluster Bootstrap to your orchestration environment (e.g. Kubernetes, Marathon). A static list of seed nodes is still supported but we recommend migrating to Cluster Bootstrap.</p>
<h2><a href="#deployment-with-kubernetes-or-red-hat-openshift" name="deployment-with-kubernetes-or-red-hat-openshift">Deployment with Kubernetes or Red Hat OpenShift</a></h2>
<p>Lagom 1.5.0 will no longer support Lightbend Orchestration (which was <a href="https://developer.lightbend.com/docs/reactive-platform/2.0/support-terminology/index.html#incubating">Incubating</a>). Despite accelerating the first deployment, using Lightbend Orchestration was producing friction and reducing flexibility to tune the deployment. Moving forward, there will be no automated handling of the deployment and the suggested way is to manually maintain the production settings, the deployment descriptors and related scripts.</p>
<p>If you are targeting OpenShift or Kubernetes environments the new <a href="https://developer.lightbend.com/guides/openshift-deployment/">Guide to Deploy Lightbend Applications</a> covers all the steps and details (including a sample application) to set up and tune your system.</p>
<h2><a href="#akka-grpc-integration" name="akka-grpc-integration">Akka gRPC integration</a></h2>
<p>Lagom 1.5.0 introduces <a href="https://developer.lightbend.com/docs/lightbend-platform/2.0/support-terminology/index.html#incubating">incubating</a> support for <a href="https://developer.lightbend.com/docs/akka-grpc/current/">Akka gRPC</a> for cross-service communication. The original HTTP/JSON-based transport is not disappearing but, instead, Lagom introduces gRPC so users can choose to expose alternative transports increasing the adoption of their services.</p>
<p>This feature drove some smaller improvements which non-gRPC users will also welcome.<br />Lagom already supported HTTP/2 since it is built on top of Play. In Lagom 1.5 we’ve reviewed all the necessary pieces so HTTP/2 can also be used on dev mode. In the same spirit, it is now also possible to use encrypted (TLS) communication on dev mode. </p>
<p>As a final improvement driven by the adoption of gRPC, Lagom 1.5 now supports Additional Routers (<a href="https://www.lagomframework.com/documentation/1.5.x/java/AdditionalRouters.html">Java API</a> / <a href="https://www.lagomframework.com/documentation/1.5.x/scala/AdditionalRouters.html">Scala API</a>), which lets you embed any vanilla Play Router into a Lagom service. You are now able to easily reuse the Play and Akka building blocks whenever the Lagom API is not enough to complete the task at hand. Using Additional Routers it is trivial to reuse Play code you already had or extend Lagom with low-level features supported in Play but not exposed in Lagom directly (such as uploading files).</p>
<h2><a href="#couchbase-persistence-support" name="couchbase-persistence-support">Couchbase Persistence Support</a></h2>
<p>Lagom 1.5 also offers optional support for <a href="https://www.couchbase.com/">Couchbase</a> as a new database option for persistent entities and read side processors through the <a href="https://doc.akka.io/docs/akka-persistence-couchbase/current/">Akka Persistence Couchbase</a> module. Currently available in an <a href="https://developer.lightbend.com/docs/lightbend-platform/2.0/support-terminology/index.html#incubating">Incubating</a> early access release, Akka Persistence Couchbase has been built to work with Lagom 1.5 and the 1.0 release is coming soon. See the documentation for <a href="https://doc.akka.io/docs/akka-persistence-couchbase/current/lagom-persistent-entity.html">Couchbase Persistent Entities</a> and <a href="https://doc.akka.io/docs/akka-persistence-couchbase/current/lagom-read-side.html">Couchbase Read-Side support</a> for more details.</p>
<h2><a href="#migrating-from-previous-versions" name="migrating-from-previous-versions">Migrating from previous versions</a></h2>
<p>This release introduces very little changes over the <code>1.5.0-RC2</code> so if you already moved to that version the upgrade should be trivial. If you are still using Lagom <code>1.4.x</code> we recommend you first migrate to the latest version available of Lagom 1.4 series and then migrate to Lagom 1.5. If you are using a version older than <code>1.4.x</code>, you should migrate one version at a time. For example: from <code>1.3.9</code> to <code>1.3.11</code> (because <code>1.3.11</code> is <code>1.3.latest</code>), then from <code>1.3.11</code> to <code>1.4.latest</code> and finally to <code>1.5.x</code>. Read the appropriate <a href="https://github.com/lagom/lagom/releases">release notes</a> and migration guides (<a href="https://www.lagomframework.com/documentation/latest/java/Migration15.html">Java</a> / <a href="https://www.lagomframework.com/documentation/latest/scala/Migration15.html">Scala</a>) on each step.</p>
<h2><a href="#credits" name="credits">Credits</a></h2>
<p>Thanks to the community for their detailed bug reports and contributions.</p>
<p>Thanks to <a href="https://www.lightbend.com/">Lightbend</a> for their continued sponsorship of the Lagom core team’s efforts. Lightbend offers <a href="https://www.lightbend.com/subscription">commercial support</a> for Lagom.</p>
<p>Special thanks to the following contributors who helped with this release:</p>
<pre class="prettyprint"><code>commits author    
     53 Ignasi Marimon-Clos
     37 Renato Cavalcanti
     20 Tim Moore
     16 Dale Wijnand
     15 Elijah Rippeth
     11 Marcos Pereira
      4 Martynas Mickevičius
      3 Ayush Prashar
      2 Alden Torres
      1 sullis
      1 danielklein45
      1 Zhonglai Zhang
      1 Sergey Morgunov
      1 Riccardo Sirigu
      1 Prashant Sharma
      1 Piyush Goyal
      1 Kunal sethi
      1 João Guitana
      1 Ido Shamun
      1 Enno
      1 Corey Auger
      1 Brent Eritou
      1 0xflotus
</code></pre>
