---
theme: mp-theme
size: 16:9
transition: slide 
# see https://github.com/marp-team/marp-cli/blob/main/docs/bespoke-transitions/README.md#built-in-transitions
marp: true
---

#### Scala in 2025
# How to Start, What to Learn

![bg right:30% 70%](./img/scala-spiral.png)

<!-- class: line-numbers -->

<!-- 
Talk plan

1. Briefly what Scala is
 * OOP and FP
 * Multiplatform
 * Backed by academia, not corporations
2. IDEs 
 * Intellij 
   * How to install
   * Scala plugin (https://github.com/JetBrains/intellij-scala)
   * Pros (out of the box, familiar for Java devs/Pycharm users)
   * Cons (errors can be out of sync, non OSS editor)
 * Metals 
   * How to install (Editor of choice)
   * Pros (in sync with the compiler, latest compiler features)
   * Cons (unequal experience across editors, requires reimport more often than intellij)
3. Build tools
 * What are they
 * sbt, scala-cli, just mention mill
 * scala-cli good enough for starters
4. Flavors of Scala
 * Good old OOP with https://www.playframework.com
 * Python like with Li Haoi https://www.lihaoyi.com/post/12yearsofthecomlihaoyiScalaPlatform.html
 * Direct style concurrency with Ox https://ox.softwaremill.com/latest
 * Hardcore FP with Cats Effect https://typelevel.org/cats-effect
 * Actors with Pekko/Akka
 * Many more
   * ZIO
   * Spark
   * Casual FP
   * Everything in between 
5. Benefits of giving it a try (key takeaways)
 * Scala fits many problem spaces, perhaps it fits yours
 * Type system can make the experience safer and more pleasant
 * Multi-platforming across JVM, JS and Native is an added benefit
 * Learn a lot, broaden your horizons
 * Coding styles can be mixed

ideas:
 * consider mentioning companies that use Scala
 * list learning resources, probably done best next to each subpoint of #4

todos:
 * validate code samples, perhaps extract them with mdoc
 * verify the dependencies, if they are necessary and on latest versions

 -->


---

# Before we move on ☝️

Something too obvious? missing? 
Let me know!

![bg right:40% 80%](./img/homepage.png)

---

# What is Scala?

* Provides reliability through typesafety
* Typed language that feels like dynamic one
* Runs on JVM, JavaScript, and Native platforms

---

# Academic Roots

- Developed at EPFL, by Martin Odersky 
- Community-driven evolution rather than corporate interests

---

# Why try Scala?

![bg right:30% 70%](./img/scala-spiral.png)


1) Reliability through types
2) Multi-Platform Support (JVM, JS, Native)
3) Modern Features
4) Ecosystem Diversity
5) Career Growth

---

# Is Scala still relevant?
<!-- _transition: fade -->

![bg 100% blur:2px brightness:0.3](./img/pexels-pixabay-237258.jpg)

---

# Companies using Scala


![bg 100% blur:5px brightness:0.3](./img/pexels-pixabay-237258.jpg)

<!-- 
Some research entry points:
- https://en.wikipedia.org/wiki/Scala_(programming_language)#Companies
- https://www.phind.com/search/cm7t37cup00002v6mor2h2097
- https://github.com/uhub/awesome-scala
- https://www.perplexity.ai/search/i-m-working-on-an-introduction-GZXmiB0QTRqiG7.XyvUP3g
- https://github.com/stkeky/best-of-scala
 -->
<!-- 
[Twitter/X](https://github.com/twitter/finagle)
[The Guardian](https://github.com/guardian/grid)
[Lichess](https://github.com/lichess-org/lila)
[Netflix](https://github.com/Netflix/atlas)
[Linkedin](https://github.com/linkedin/isolation-forest)
[Coursera](https://github.com/coursera/courier)
[Apple](https://jobs.apple.com/en-us/details/200589146/sr-development-data-engineer-music-books-podcasts-content-data-services?team=SFTWR)
[SiriusXM](https://siriusxm.github.io/snapshot4s/)
[Zalando](https://engineering.zalando.com/posts/2018/01/why-we-do-scala.html)
[Morgan Stanley](https://github.com/morganstanley/optimus-cirrus)
[JP Morgan](https://jpmc.fa.oraclecloud.com/hcmUI/CandidateExperience/en/sites/CX_1001/requisitions?keyword=Scala&mode=location)
[HMRC and more of gov.uk](https://github.com/hmrc)
[Duolingo](https://blog.duolingo.com/rewriting-duolingos-engine-in-scala/)
[M1 Finance](https://github.com/m1finance)
[LEGO](https://github.com/LEGO/woof)
[Airbnb](https://github.com/airbnb/chronon)
[Spotify](https://github.com/spotify/scio)
[PayPal](https://github.com/paypal/squbs)
[Softwaremill](https://github.com/softwaremill)
[Virtuslab](https://virtuslab.com/expertise/scala/)
[Databricks](https://github.com/databricks/sjsonnet)
[Tesla](https://www.infoq.com/presentations/tesla-vpp/)
[Workday](https://github.com/Workday/warp-core)
[Disney Streaming](https://disneystreaming.github.io/smithy4s)
[Salesforce](https://github.com/salesforce/orchard)
[Thoughtworks](https://github.com/ThoughtWorksInc/Dsl.scala) -->


<style>
  .companies-cloud {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }
  .companies-cloud a {
    text-decoration: none;
    color: white;
    margin-right: 20px;
    opacity: 0;
    animation: fadeIn 0.5s ease-in forwards;
  }
  .companies-cloud a:hover {
    text-decoration: underline;
  }
  .font-size-32 { font-size: 32px; }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  /* Set different animation delays for each link */
  .companies-cloud a:nth-child(1) { animation-delay: 0s; }
  .companies-cloud a:nth-child(2) { animation-delay: 0.2s; }
  .companies-cloud a:nth-child(3) { animation-delay: 0.4s; }
  .companies-cloud a:nth-child(4) { animation-delay: 0.6s; }
  .companies-cloud a:nth-child(5) { animation-delay: 0.8s; }
  .companies-cloud a:nth-child(6) { animation-delay: 1s; }
  .companies-cloud a:nth-child(7) { animation-delay: 1.2s; }
  .companies-cloud a:nth-child(8) { animation-delay: 1.4s; }
  .companies-cloud a:nth-child(9) { animation-delay: 1.6s; }
  .companies-cloud a:nth-child(10) { animation-delay: 1.8s; }
  .companies-cloud a:nth-child(11) { animation-delay: 2s; }
  .companies-cloud a:nth-child(12) { animation-delay: 2.2s; }
  .companies-cloud a:nth-child(13) { animation-delay: 2.4s; }
  .companies-cloud a:nth-child(14) { animation-delay: 2.6s; }
  .companies-cloud a:nth-child(15) { animation-delay: 2.8s; }
  .companies-cloud a:nth-child(16) { animation-delay: 3s; }
  .companies-cloud a:nth-child(17) { animation-delay: 3.2s; }
  .companies-cloud a:nth-child(18) { animation-delay: 3.4s; }
  .companies-cloud a:nth-child(19) { animation-delay: 3.6s; }
  .companies-cloud a:nth-child(20) { animation-delay: 3.8s; }
  .companies-cloud a:nth-child(21) { animation-delay: 4s; }
  .companies-cloud a:nth-child(22) { animation-delay: 4.2s; }
  .companies-cloud a:nth-child(23) { animation-delay: 4.4s; }
  .companies-cloud a:nth-child(24) { animation-delay: 4.6s; }
  .companies-cloud a:nth-child(25) { animation-delay: 4.8s; }
  .companies-cloud a:nth-child(26) { animation-delay: 5s; }
  .companies-cloud a:nth-child(27) { animation-delay: 5.2s; }
  .companies-cloud a:nth-child(28) { animation-delay: 5.4s; }
  .companies-cloud a:nth-child(29) { animation-delay: 5.6s; }
  .companies-cloud a:nth-child(30) { animation-delay: 5.8s; }

</style>

<div class="companies-cloud">
<a href="https://github.com/twitter/finagle" class="font-size-32">Twitter/X</a>
<a href="https://github.com/guardian/grid" class="font-size-32">The Guardian</a>
<a href="https://github.com/lichess-org/lila" class="font-size-32">Lichess</a>
<a href="https://github.com/Netflix/atlas" class="font-size-32">Netflix</a>
<a href="https://github.com/linkedin/isolation-forest" class="font-size-32">Linkedin</a>
<a href="https://github.com/coursera/courier" class="font-size-32">Coursera</a>
<a href="https://jobs.apple.com/en-us/details/200589146/sr-development-data-engineer-music-books-podcasts-content-data-services?team=SFTWR" class="font-size-32">Apple</a>
<a href="https://siriusxm.github.io/snapshot4s/" class="font-size-32">SiriusXM</a>
<a href="https://engineering.zalando.com/posts/2018/01/why-we-do-scala.html" class="font-size-32">Zalando</a>
<a href="https://github.com/morganstanley/optimus-cirrus" class="font-size-32">Morgan Stanley</a>
<a href="https://jpmc.fa.oraclecloud.com/hcmUI/CandidateExperience/en/sites/CX_1001/requisitions?keyword=Scala&mode=location" class="font-size-32">JP Morgan  </a>
<a href="https://github.com/hmrc" class="font-size-32">HMRC / gov.uk</a>
<a href="https://blog.duolingo.com/rewriting-duolingos-engine-in-scala/" class="font-size-32">Duolingo</a>
<a href="https://github.com/m1finance" class="font-size-32">M1 Finance</a>
<a href="https://github.com/LEGO/woof" class="font-size-32">LEGO</a>
<a href="https://github.com/airbnb/chronon" class="font-size-32">Airbnb</a>
<a href="https://github.com/spotify/scio" class="font-size-32">Spotify</a>
<a href="https://github.com/paypal/squbs" class="font-size-32">PayPal</a>
<a href="https://github.com/softwaremill" class="font-size-32">Softwaremill</a>
<a href="https://virtuslab.com/expertise/scala/" class="font-size-32">Virtuslab</a>
<a href="https://github.com/databricks/sjsonnet" class="font-size-32">Databricks</a>
<a href="https://www.infoq.com/presentations/tesla-vpp/" class="font-size-32">Tesla</a>
<a href="https://github.com/Workday/warp-core" class="font-size-32">Workday</a>
<a href="https://disneystreaming.github.io/smithy4s" class="font-size-32">Disney Streaming</a>
<a href="https://github.com/salesforce/orchard" class="font-size-32">Salesforce</a>
<a href="https://github.com/ThoughtWorksInc/Dsl.scala" class="font-size-32">Thoughtworks</a>
<a href="https://swissborg.com/" class="font-size-32">SwissBorg</a>
<a href="https://xebia.com/blog/" class="font-size-32">Xebia Functional</a>
<a href="https://careers.wolt.com/en/blog/tech/scala-at-wolt-our-scala-organization-part-i" class="font-size-32">Wolt</a>
</div>



<!-- _footer: Not a comprehensive list, last access 3.03.25, just a trainride of research 🚄 -->

---

# IDE Choice

![bg 100% blur:6px brightness:0.3](./img/ide-trim.jpg)

---

# IDE Choice: IntelliJ

![bg right:20% 70%](./img/intellij.png)


1. Download IntelliJ IDEA (Community or Ultimate)
2. Install Scala plugin: Settings → Plugins → "Scala"

---

# IntelliJ: Pros & Cons

✅ Familiar interface for Java/PyCharm users, rich features out of the box
❌ Compiler errors can be out of sync, non-open-source editor

---

# IntelliJ: Install

https://www.jetbrains.com/help/idea/get-started-with-scala.html

---

# IDE Choice: Metals

![bg right:20% 70%](./img/scalameta-logo.png)

Language Server that works with VS Code, Vim, Emacs, and others. 

Install through your editor's extension marketplace.

---

# Metals: Pros & Cons

✅ Always in sync with compiler, supports latest features
❌ Experience varies between editors


---

# Metals: Install

https://scalameta.org/metals/docs

---

![bg blur:1px brightness:0.3](./img/build-tools.jpg)

# Build Tools Overview

### Manage dependencies, compile code, and run tests

---

# scala-cli: The Simple Choice

![bg right:20% 70%](./img/scala-cli.png)


* ❌ Not technically a build tool
* ✅ Nobody cares

---

# scala-cli: The Simple Choice

![bg right:20% 70%](./img/scala-cli.png)

Modern, user-friendly build tool designed for:
- Single-file scripts
- Small projects
- Quick prototypes

---

# scala-cli: Install

Just install Scala!

https://docs.scala-lang.org/getting-started/install-scala.html

---

# scala-cli: Perfect for Learning

```scala
// add dependencies
//> using dep com.lihaoyi::pprint:0.9.0

// define scala version
//> using scala 3.3.5

@main def hello() = 
  pprint.log("No build config needed!")
```

---

# scala-cli: Just run it


```bash
# Run a single file
scala Hello.scala
scala-cli Hello.scala 
# ☝️ if you installed from https://scala-cli.virtuslab.org/
```

---

# sbt: The Power Tool


![bg right:30% 70%](./img/sbt-logo-reverse.svg)


Industry standard build tool for:
- Multi-module projects
- Complex dependency management 
- Custom build tasks
- Code generation

---

# sbt: Project Structure

```markdown
build.sbt            # build config
project/
  build.properties   # sbt version
  plugins.sbt        # plugins
src/
  main/
    scala/           # source code
  test/
    scala/           # test code
```

---

# sbt: Configuration Example

```scala
// build.sbt
name := "my-project"
version := "0.1.0"

lazy val root = (project in file("."))
  .settings(
    scalaVersion := "3.3.1",
    libraryDependencies ++= Seq(
      "org.typelevel" %% "cats-effect" % "3.5.4",
      "org.scalatest" %% "scalatest" % "3.2.15" % Test
    )
  )
```

---

# When to Use What?
<style scoped>
.columns {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
}
</style>

<div class="columns">
  <ul><strong>scala-cli</strong>
    <li>Learning Scala</li>
    <li>Scripts & prototyping</li>
    <li>Single-module applications</li>
  </ul>
  <ul><strong>sbt</strong>
    <li>Multi-module applications</li>
    <li>Code generation</li>
    <li>Managing CI/CD pipelines</li>
  </ul>
</div>


---

# Mill: Alternative

* Multi-language build tool: Scala, Java, Kotlin, Python
* https://github.com/com-lihaoyi/mill

---

# Flavors of Scala

Coding styles and frameworks


![bg 100% blur:2px brightness:0.6](./img/spices.jpg)

---

![bg 100% blur:6px brightness:0.4](./img/cask.jpg)

# Cask: Flask but for Scala

Li Haoyi Style

Inspired by Python's Flask

https://com-lihaoyi.github.io/cask/


---

# Li Haoyi Style: Getting Started

Create new directory and file:
```bash
mkdir cask-demo
cd cask-demo
touch app.scala
```

---

# Li Haoyi Style: Web Server with Cask

```scala
//> using dep "com.lihaoyi::cask:0.9.2"
object app extends cask.MainRoutes:

  @cask.post("/greet")
  def greet(name: String) = s"Hello, $name!"
  
  @cask.get("/users/:userId")
  def user(userId: Int) = 
    val users = Map(1 -> "Alice", 2 -> "Bob")
    users.getOrElse(userId, "User not found")

  initialize()

// Start server
@main def run() = 
  cask.main.Main.main(args = Array("app"))
```

---

# Li Haoyi Style: Testing the API

Run with: `scala-cli app.scala`

```bash
# Test the endpoints
curl http://localhost:8080
curl -X POST -d "name=John" http://localhost:8080/greet
curl http://localhost:8080/users/1
```

---

# Li Haoyi: Development platform

There's more: Scalatags, FastParse, uTest, uPickle, Ammonite, Sourcecode, Mill, PPrint, OS-Lib, Requests-Scala, Cask, MainArgs, ScalaSql

Read more in [12 years of the com.lihaoyi Scala Platform](https://www.lihaoyi.com/post/12yearsofthecomlihaoyiScalaPlatform.html#what-is-the-comlihaoyi-platform)


---

# Play Framework: Web Development

Full-stack framework with all of the components you need to build a Web Application or a REST service


![bg right:20% 70%](./img/playframework.png)


---

# Play Framework: Stack


![bg right contain](./img/play-stack.svg)


---

# Play Framework: Web Development

Start with sbt:
```bash
sbt new play-scala-seed.g8
cd play-scala-seed
sbt run
```

---

# Play Framework: Hello World

```scala
// app/controllers/HelloController.scala
package controllers
import javax.inject._
import play.api.mvc._

@Singleton
class HelloController @Inject()(val controllerComponents: ControllerComponents) 
    extends BaseController {

  def hello() = Action { implicit request: Request[AnyContent] =>
    Ok("Hello, World!") // here goes your logic
  }
}
```

---

# Play Framework: Route Configuration

```groovy
# conf/routes
GET     /hello      controllers.HelloController.hello()
```

Run `sbt run` and visit http://localhost:9000/hello to see your message!



---

# Tapir 


![bg right:40% 70%](./img/tapir.svg)
<!-- ![bg right contain](./img/tapir.svg) -->


Programmer-friendly, reasonably type-safe API to expose, consume and document HTTP endpoints

---

# Tapir: Dependencies

```scala
//> using scala 3.6.3
//> using dep com.softwaremill.sttp.tapir::tapir-http4s-server:1.11.15
//> using dep org.http4s::http4s-ember-server:0.23.30
//> using dep com.softwaremill.sttp.tapir::tapir-json-circe:1.11.15
//> using dep ch.qos.logback:logback-classic:1.5.16
```

---

# Tapir: Endpoint definition

```scala
object Endpoints {
  val booksListing: PublicEndpoint[String, Unit, List[Book], Any] = endpoint.get
    .in("books" / "list" / query[String]("filter"))
    .out(jsonBody[List[Book]])
  
  val booksListingServerEndpoint: ServerEndpoint[Any, IO] = 
    booksListing.serverLogicSuccess(filter => Library.books(filter))

  val all: List[ServerEndpoint[Any, IO]] = List(booksListingServerEndpoint)
}

object Library {
  case class Author(name: String)
  case class Book(title: String, year: Int, author: Author)

  def books(filter: String): IO[List[Book]] = /* irrelevant */
}
```

---

# Tapir: Main application

```scala
object Main extends IOApp {

  override def run(args: List[String]): IO[ExitCode] =

    val routes = Http4sServerInterpreter[IO]().toRoutes(Endpoints.all)

    val port = sys.env
      .get("HTTP_PORT")
      .flatMap(_.toIntOption)
      .flatMap(Port.fromInt)
      .getOrElse(port"8080")

    EmberServerBuilder
      .default[IO]
      .withHost(Host.fromString("localhost").get)
      .withPort(port)
      .withHttpApp(Router("/" -> routes).orNotFound)
      .build
      .use{ server =>
        for
          _ <- IO.println(s"Server started at http://localhost:${server.address.getPort}. Press ENTER key to exit.")
          _ <- IO.readLine
        yield ()
      }.as(ExitCode.Success)
}
```

---

# Adopt Tapir!

https://adopt-tapir.softwaremill.com

![bg right:40% 70%](./img/tapir.svg)

---

![bg right:30% 90%](./img/pekko.png)

# Pekko

Concurrent, distributed, resilient systems with Actor model

---

![bg 90%](./img/actor-model-0.svg)


<!-- _transition: fade -->

---

![bg 90%](./img/actor-model-1.svg)


<!-- _transition: fade -->

---

![bg 90%](./img/actor-model-2.svg)


<!-- _transition: fade -->

---

![bg 90%](./img/actor-model-3.svg)


<!-- _transition: fade -->

---

![bg 90%](./img/actor-model-4.svg)


<!-- _transition: fade -->

---

![bg 90%](./img/actor-model-5.svg)


---

# Pekko: Actor Systems

Create new project:
```bash
mkdir pekko-demo
cd pekko-demo
touch Counter.scala
```

---

# Pekko: Message Protocol

```scala
//> using dep "org.apache.pekko::pekko-actor-typed:1.0.2"
import org.apache.pekko.actor.typed.{ActorRef, ActorSystem, Behavior}
import org.apache.pekko.actor.typed.scaladsl.Behaviors

object Counter:
  // Define messages our actor can receive
  enum Message:
    case Increment
    case GetValue(replyTo: ActorRef[Int])
```

---

# Pekko: Actor Implementation

```scala
object Counter:
  // Previous Message definition...
  
  def apply(): Behavior[Message] = counter(0)

  private def counter(value: Int): Behavior[Message] =
    Behaviors.receive { (context, message) =>
      message match
        case Message.Increment =>
          println(s"Incrementing counter to ${value + 1}")
          counter(value + 1)
          
        case Message.GetValue(replyTo) =>
          replyTo ! value
          Behaviors.same
    }
```

---

# Pekko: Running the System

```scala
@main def run() =
  // Create the actor system
  val system = ActorSystem(Counter(), "CounterSystem")
  
  // Create an actor to receive responses
  val printer = ActorSystem(
    Behaviors.receive[Int] { (context, msg) =>
      println(s"Current value: $msg")
      Behaviors.same
    },
    "printer"
  )
  
  // Send messages
  system ! Counter.Message.Increment
  system ! Counter.Message.Increment
  system ! Counter.Message.GetValue(printer.ref)
  
  // Keep the program running
  Thread.sleep(1000)
  
  // Shutdown
  system.terminate()
  printer.terminate()
```

---

# Pekko: Running the Example

Run the program:
```bash
scala-cli Counter.scala
```

Output:
```bash
Incrementing counter to 1
Incrementing counter to 2
Current value: 2
```

---

# Laminar: User Interfaces for Scala.js 


![bg right:20% 70%](./img/laminar-logo.png)

Native Scala.js library for building user interfaces


---

# Laminar: Example

![](./img/laminar-counter.png)


---

# Laminar: Example

```scala
package example

import com.raquo.laminar.api.L.{*, given}

object CounterView {

  def apply(): HtmlElement = {
    div(
      cls("CounterView"),
      Counter(label = "Foo", initialStep = 1),
    )
  }

  /* Counter implementation */
}
```

---

# Laminar: Example

```scala
package example

import com.raquo.laminar.api.L.{*, given}

object CounterView {
  def Counter(label: String, initialStep: Int): HtmlElement = {
    val allowedSteps = List(1, 2, 3, 5, 10)
    val stepVar = Var(initialStep)
    val diffBus = new EventBus[Int]
    val countSignal: Signal[Int] = diffBus.events.scanLeft(initial = 0)(_ + _)

    div(
      cls("Counter"),
      p(
        "Step: ",
        select(
          value <-- stepVar.signal.map(_.toString),
          onChange.mapToValue.map(_.toInt) --> stepVar,
          allowedSteps.map { step => option(value := step.toString, step) }
        )
      ),
      p(
        label + ": ",
        b(text <-- countSignal),
        " ",
        button("–", onClick.mapTo(-1 * stepVar.now()) --> diffBus),
        button("+", onClick(_.sample(stepVar.signal)) --> diffBus)
      )
    )
  }
}
```

---

# Laminar: Example

![](./img/laminar-counter.png)


---

# Scala.js: Resources

- https://www.youtube.com/watch?v=AQix1WaWuOo - Daniel Ciocîrlan GENERATIVE ART WITH SCALA, NO AI REQUIRED
- https://www.lihaoyi.com/hands-on-scala-js - Hands on Scala.js by Li Haoyi
- https://tyrian.indigoengine.io/documentation - Tyrian, Elm-inspired frontend framework
- https://slinky.dev - Write React apps in Scala just like you would in ES6


---

# That's just the beginning!

<!-- _transition: fade -->

![bg 100% blur:2px brightness:0.5](./img/long-way.jpg)

---

# Other Popular Flavors

![bg 100% blur:2px brightness:0.3](./img/long-way.jpg)

* [Spark](https://spark.apache.org/docs/latest/quick-start.html): Big data processing
* Functional streams with [FS2](https://fs2.io/#/)
* [Cats Effect](https://typelevel.org/cats-effect/): The pure asynchronous runtime for Scala
* [ZIO](https://zio.dev/): Effect system with built-in dependency injection
* [Kyo](https://getkyo.io): Novel approach based on algebraic effects
* [Gears](https://lampepfl.github.io/gears/): Experimental async programming for Scala
* Casual FP: Mix and match functional concepts
* [Indigo](https://indigoengine.io/): Make games with Scala
* [Souds of Scala](https://github.com/pauliamgiant/sounds-of-scala): Build music applications
* And a lot more

---

# Learning

![bg 100% blur:2px brightness:0.3](./img/learning.jpg)

<!-- _transition: fade -->

---

![bg 100% blur:5px brightness:0.2](./img/learning.jpg)


# Learning is a process

There are plenty of ways to learn

1) Courses
2) Books
3) Blogs
4) Forums
5) Meetups and conferences

---
![bg 100% blur:3px brightness:0.2](./img/online-course.jpg)

# Courses

---

![bg right:30% 70%](./img/epfl-logo.svg)
# Functional Programming in Scala Specialization
##### (a.k.a.) Coursera Course

Co-authored by Martin Odersky, author of Scala

---

<!-- 
In my private opinion, two first should be mandatory.

Even if you don't plan to use Scala professionally, it teaches you a lot about functional programming techinques
-->

![bg right:30% 70%](./img/epfl-logo.svg)
# Functional Programming in Scala Specialization

5 courses specialization

1. Functional Programming Principles in Scala
2. Functional Program Design in Scala
3) Parallel programming
4) Big Data Analysis with Scala and Spark
5) Functional Programming in Scala Capstone

https://www.coursera.org/specializations/scala

---

<!-- Paid, discount codes available -->

![bg right:30% 70%](./img/rockthejvm.png)

# Rock the JVM

Led by Daniel Ciocîrlan, offers Scala courses all proficiency levels

https://courses.rockthejvm.com

* [Scala at Light Speed](https://www.youtube.com/playlist?list=PLmtsMNDRU0BxryRX4wiwrTZ661xcp6VPM) free on Youtube
* Scala Essentials 
* The Scala Bundle 

---


![bg right:30% 70%](./img/rockthejvm.png)

# Rock the JVM: Discount code!

<!-- _transition: fade -->

---


![bg right:30% 70%](./img/rockthejvm.png)

# Rock the JVM: Discount code!

`FUNCTIONAL_TALKS`

---

![bg right:20% 70%](./img/learn-scala-dev.png)

# Alvin's Courses

Created by Alvin Alexander, author of https://alvinalexander.com/, 
["Functional Programming, Simplified"](https://alvinalexander.com/scala/functional-programming-simplified-book/), ["Scala Cookbook"](https://scalacookbook.com/)

Offers free Scala courses at https://www.learnscala.dev/

---

![bg right:30% 70%](./img/yt_logo_rgb_light.png)

# Youtube channels

## Podcasts & talks
[Scala Space](https://www.youtube.com/@scalaspace) · [Scala for fun and profit](https://www.youtube.com/@Scala-for-Fun-and-Profit/videos) · [Softwafemill](https://www.youtube.com/@SoftwareMillCom/videos) · [Scaladays](https://www.youtube.com/@ScalaDaysConferences)

## Learning
[Rock The Jvm](https://www.youtube.com/@rockthejvm) · [Jakub Kozłowski](https://www.youtube.com/@kubukoz_/videos) · [Dev inside you](https://www.youtube.com/@DevInsideYou/videos) · [IntelliJ IDEA, a JetBrains IDE](https://www.youtube.com/@intellijidea/videos)

And more https://www.nbshare.io/blog/best-scala-tutorials-on-youtube/

---

# Books
<!-- _transition: fade -->

![bg 100% blur:0px brightness:0.7](./img/covers/combined.png)


---

# Books
<!-- _transition: fade -->

![bg 100% blur:8px brightness:0.2](./img/covers/combined.png)

* **Programming in Scala**
Comprehensive guide by Martin Odersky

* **Scala for the impatient**
Compact introduction guide for those already competent in other languages like Java, C#, Python, JS or C++

* **Grokking functional programming**
by Michał Płachta easy way to learn functional programming for those familiar with the OOP ideas

* **Functional Programming Strategies In Scala with Cats**
by Noel Welsh, compendium on learning Cats library

---

# Books
![bg 100% blur:8px brightness:0.2](./img/covers/combined.png)

* **Functional programming in Scala**
a.k.a. "The red book", your go-to book for hands-on, advanced functional programming 

* **Practical FP in Scala**
For those familiar with functional programming in Scala who are yet not confident about architecting an application from scratch

* **Functional Event-Driven Architecture**
Explore the event-driven architecture (EDA) in a purely functional way.

* Many more https://docs.scala-lang.org/books.html https://whatpixel.com/best-scala-books/


---

# Blogs
<!-- _transition: fade -->
![bg 100% blur:0px brightness:0.7](./img/blog.jpg)

---

# Blogs
<!-- _transition: fade -->
![bg 100% blur:3px brightness:0.2](./img/blog.jpg)

<style>
  .tag-cloud {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    /* font-size: 16px; */
    gap: 10px;
  }
  .tag-cloud a {
    text-decoration: none;
    color: white;
    padding: 5px;
  }
  .tag-cloud a:hover {
    text-decoration: underline;
  }
  .font-size-18 { font-size: 18px; }
  .font-size-20 { font-size: 20px; }
  .font-size-22 { font-size: 22px; }
  .font-size-24 { font-size: 24px; }
  .font-size-26 { font-size: 26px; }
  .font-size-28 { font-size: 28px; }
  .font-size-30 { font-size: 30px; }
  .font-size-32 { font-size: 32px; }

</style>

<div class="tag-cloud">
  <a href="https://www.softinio.com" class="font-size-18">Salar Rahmanian</a>
  <a href="https://www.scala-lang.org/blog/" class="font-size-22">Scala Lang</a>
  <a href="https://typelevel.org/blog/" class="font-size-20">Typelevel</a>
  <a href="https://mpilquist.github.io/" class="font-size-24">Michael Pilquist</a>
  <a href="http://justinhj.github.io/" class="font-size-26">Justin Heyes-Jones</a>
  <a href="https://www.chris-kipp.io/" class="font-size-28">Chris Kipp</a>
  <a href="https://blog.indoorvivants.com" class="font-size-30">Anton Sviridov</a>
  <a href="https://jamesward.com" class="font-size-32">James Ward</a>
  <a href="https://eed3si9n.com/" class="font-size-18">Eugene Yokota</a>
  <a href="https://alexn.org/blog/" class="font-size-22">Alexandru Nedelcu</a>
  <a href="https://blog.kubukoz.com/" class="font-size-20">Jakub Kozłowski</a>
  <a href="https://yadukrishnan.live/" class="font-size-24">Yadu Krishnan</a>
  <a href="https://blog.michal.pawlik.dev/" class="font-size-26">Michał Pawlik</a>
  <a href="https://www.lihaoyi.com/" class="font-size-28">Haoyi Li</a>
  <a href="https://blog.rockthejvm.com/" class="font-size-30">Rock The JVM Blog</a>
  <a href="https://toniogela.dev/" class="font-size-32">Antonio Gelameris</a>
  <a href="https://juliano-alves.com/" class="font-size-18">Juliano Alves</a>
  <a href="https://inner-product.com/" class="font-size-22">Inner Product</a>
  <a href="https://rossabaker.com/" class="font-size-20">Ross Baker</a>
  <a href="https://xebia.com/blog/" class="font-size-24">Xebia</a>
  <a href="https://chollinger.com/blog/" class="font-size-26">Chistian Hollinger</a>
  <a href="https://antonkw.github.io/" class="font-size-28">Anton Kovalevsky</a>
  <a href="https://medium.com/tag/scala" class="font-size-30">Medium (tag Scala)</a>
  <a href="https://virtuslab.com/blog/" class="font-size-32">VirtusLab</a>
  <a href="https://www.madewithtea.com" class="font-size-18">Jendrik Poloczek</a>
  <a href="https://blog.pierre-ricadat.com/" class="font-size-22">Pierre Ricadat</a>
  <a href="https://lachlan.hashnode.dev" class="font-size-20">Lachlan O'Dea</a>
  <a href="https://softwaremill.com/blog/" class="font-size-24">SoftwareMill</a>
  <a href="https://github.com/rssh/notes" class="font-size-26">Ruslan Shevchenko</a>
  <a href="https://neander.tech" class="font-size-28">Neandertech</a>
  <a href="https://scalameta.org/metals/blog/" class="font-size-30">Scala Metals</a>
  <a href="https://podcasters.spotify.com/pod/show/julien-truffaut" class="font-size-32">Scala for Fun and Profit</a>
  <a href="https://cloudmark.github.io/" class="font-size-18">Mark Galea</a>
  <a href="https://blog.rhetoricalmusings.com" class="font-size-22">A Developer's Experience</a>
  <a href="https://day-to-day-stuff.blogspot.com/" class="font-size-20">Erik van Oosten</a>
</div>


---

# Blogs
![bg 100% blur:3px brightness:0.2](./img/blog.jpg)

https://www.scalanews.net/Resources/Blog_Directory.html

---

# Community

Your go-to list of forums, chat rooms, local user groups, and conferences

https://www.scala-lang.org/community


---

# Forums

[Scala](https://discord.com/invite/scala) on discord
[Reddit r/scala](https://old.reddit.com/r/scala/)
[Scala Users Discourse](https://users.scala-lang.org/)
[Scala Contributors Discourse](https://contributors.scala-lang.org/)
[Scala Poland 🇵🇱](https://join.slack.com/t/scala-poland/shared_invite/zt-1jeq834yd-iOTH4U1Gto3YWu_lEVY5oA) on Slack

---

# Forums


**[IntelliJ](https://discord.gg/aUKpZzeHCK)** · **[Scalameta](https://discord.gg/RFpSVth)** · **[Play Framework](https://discord.gg/g5s2vtZ4Fa)** · **[Typelevel](https://discord.gg/XF3CXcMzqD)** · **[ZIO](https://discord.gg/2ccFBr4)** · **[Laminar](https://discord.gg/JTrUxhq7sj)** · **[Smithy4s](https://discord.gg/wvVga94s8r)** · **[indigo](https://discord.gg/b5CD47g)** · **[Scala Space](https://discord.gg/vcHsmEQx)** · **[Business4s](https://bit.ly/business4s-discord)** · **[Creative Scala](https://discord.gg/rRhcFbJxVG)** 


---

# Meetups 🎙️

- London Scala User Group
- Warsaw Scala Enthusiasts
- Kraków Scala User Group
- Wrocław Scala User Group
- Bay Area Scala
- SF Scala
- Scala Bay
- Atlanta Scala
- Dallas Scala Enthusiasts
- Functional World (online)

---

# Meetups & conferences

[Scalendar](https://scalac.io/blog/category/events/) by Scalac


---

# News

![bg fill  blur:2px brightness:0.3](./img/news.jpg)

---

# Scala Times

by Softwaremill

https://scalatimes.com/

![bg right:50% 100%](./img/scalatimes.png)


---

# Scala Times

by Petr Zapletal

https://thisweekinscala.substack.com/ 

![bg right:48% 100%](./img/thisweekinscala.png)

---

# Scala Feed on Bluesky

by Michał Pawlik

https://bsky.app/profile/michal.pawlik.dev/feed/scala-feed 


![bg right:40% 80%](./img/scalafeed.png)


---

# Wrapping up

![bg 100% blur:2px brightness:0.3](./img/wrapping.jpg)

<!-- _footer: Whatever they tell you online, this image does **not** present a monad -->

---

# Start Your Journey

1) Begin with scala-cli and simple scripts
2) Pick a style that feels natural
3) Learn by building real projects
4) Join the community (Slack, Discord, Reddit)

![bg 100% blur:2px brightness:0.3](./img/long-way.jpg)

---


# Thank you!

<style scoped>
/* Styling for centering (required in default theme) */
h1, h2, h3, h4, h5, p, ul, li {
  text-align: center;
}
</style>

Keep in touch! 🤝

Blog: [blog.michal.pawlik.dev](https://blog.michal.pawlik.dev)
Linkedin: [Michał Pawlik](https://www.linkedin.com/in/michał-pawlik/)
Github: [majk-p](https://github.com/majk-p)
Bluesky: [michal.pawlik.dev](https://bsky.app/profile/michal.pawlik.dev)

![bg right:40% 80%](./img/homepage.png)
