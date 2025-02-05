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

# What is Scala?

A modern programming language that combines Object-Oriented and Functional Programming paradigms. Runs on JVM, JavaScript, and Native platforms.

---

# Academic Roots

Developed at EPFL, by Martin Odersky. Community-driven evolution rather than corporate interests.

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

# Metals: Modern Alternative

![bg right:20% 70%](./img/scalameta-logo.png)

Language Server that works with VS Code, Vim, Emacs, and others. 

Install through your editor's extension marketplace.

---

# Metals: Pros & Cons

✅ Always in sync with compiler, supports latest features
❌ Experience varies between editors, more frequent project reimports


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
//> using lib com.lihaoyi::pprint:0.9.0

// define scala version
//> using scala 3.3.5

@main def hello() = 
  pprint.log("No build config needed!")
```

---

# scala-cli: Just run it


```bash
# Run a single file
scala-cli Hello.scala
```

---

# sbt: The Power Tool


![bg right:20% 70%](./img/sbt-logo-reverse.svg)


Industry standard build tool for:
- Multi-module projects
- Complex dependency management 
- Custom build tasks
- Code generation

---

# sbt: Project Structure

```markdown
project/
  build.properties   # sbt version
  plugins.sbt        # plugins
build.sbt            # build config
src/
  main/
    scala/          # source code
  test/
    scala/          # test code
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

Another build tool with Python-inspired syntax. Popular in some communities but less common than sbt.

---

# Flavors of Scala

Coding styles and frameworks


![bg 100% blur:2px brightness:0.6](./img/spices.jpg)

---

# Play Framework: Web Development


![bg right:20% 70%](./img/playframework.png)


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
    Ok("Hello, World!")
  }
}
```

---

# Play Framework: Route Configuration

```groovy
# conf/routes
GET     /hello      controllers.HelloController.hello()
```

Visit http://localhost:9000/hello to see your message!


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
//> using lib "com.lihaoyi::cask:0.9.2"

object app extends cask.MainRoutes:
  @cask.get("/")
  def hello() = "Hello World!"
  
  @cask.post("/greet")
  def greet(name: String) = s"Hello, $name!"
  
  @cask.get("/users/:userId")
  def user(userId: Int) = 
    val users = Map(1 -> "Alice", 2 -> "Bob")
    users.getOrElse(userId, "User not found")

  initialize()

// Start server
@main def run() = 
  println("Starting server at http://localhost:8080")
  cask.main.Main.main(args = Array("app"))
```

Run with: `scala-cli app.scala`

---

# Li Haoyi Style: Testing the API

```bash
# Test the endpoints
curl http://localhost:8080
curl -X POST -d "name=John" http://localhost:8080/greet
curl http://localhost:8080/users/1
```

[Rest of the slides remain the same]

---

# Ox: Modern Concurrency

Create new project:
```bash
mkdir ox-demo
cd ox-demo
touch Main.scala
```

---

# Ox: Dependencies

```scala
//> using lib "com.softwaremill.ox::ox-core:0.0.10"
//> using lib "org.http4s::http4s-ember-client:1.0.0-M40"

import ox.*
import cats.effect.*
import org.http4s.ember.client.EmberClientBuilder

@main def download() = ox.scoped {
  // Download multiple URLs concurrently
  val urls = List(
    "https://example.com",
    "https://example.org"
  )
  
  urls.parTraverse { url =>
    println(s"Downloading $url...")
    Thread.sleep(1000) // Simulate work
    println(s"Downloaded $url")
  }
}
```

Run with: `scala-cli Main.scala`

---

# Cats Effect: Dependencies

```scala
//> using lib "org.typelevel::cats-effect:3.5.4"
```

---

# Cats Effect: Program Structure

```scala
import cats.effect.{IO, IOApp}

object FileStats extends IOApp.Simple {
  def run: IO[Unit] = {
    for {
      _ <- IO.println("Starting file analysis...")
      files <- listFiles
      stats <- analyzeFiles(files)
      _ <- printStats(stats)
    } yield ()
  }
}
```

---

# Cats Effect: Safe File Operations

```scala
import java.nio.file.{Files, Path, Paths}
import scala.jdk.CollectionConverters.*

def listFiles: IO[List[Path]] = {
  IO.blocking {
    Files.list(Paths.get("."))
      .iterator()
      .asScala
      .filter(_.toString.endsWith(".scala"))
      .toList
  }
}

def analyzeFiles(files: List[Path]): IO[Map[String, Long]] = {
  files.parTraverse { path =>
    IO.blocking {
      val size = Files.size(path)
      path.getFileName.toString -> size
    }
  }.map(_.toMap)
}
```

---

# Cats Effect: Error Handling

```scala
def printStats(stats: Map[String, Long]): IO[Unit] = {
  for {
    _ <- IO.println("\nFile Statistics:")
    _ <- stats.toList.traverse_ { case (name, size) =>
      IO.println(s"$name: ${size / 1024} KB")
        .handleErrorWith { error =>
          IO.println(s"Error processing $name: ${error.getMessage}")
        }
    }
  } yield ()
}
```

---

# Pekko: Actor Systems

Create new project:
```bash
mkdir pekko-demo
cd pekko-demo
touch Counter.scala
```

---

# Pekko: Dependencies

```scala
//> using lib "org.apache.pekko::pekko-actor-typed:1.0.2"
```

---

# Pekko: Message Protocol

```scala
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

# Other Popular Flavors

- ZIO: Effect system with powerful error handling
- Functional streams with FS2
- Spark: Big data processing
- Casual FP: Mix and match functional concepts

---

# Why try Scala?

1. Type-Driven Development
2. Multi-Platform Support
3. Ecosystem Diversity
4. Career Growth
5. Modern Features

---

# Type-Driven Development

```scala
// The compiler catches errors before runtime
case class User(name: String, age: Int)

def processUser(user: User): String = {
  // Won't compile if we try to treat age as String
  s"${user.name} is ${user.age} years old"
}
```

---

# Multi-Platform Support

```scala
// Same code, different platforms
object HelloWorld {
  def sayHello(): String = "Hello, World!"
}

// JVM:    scala-cli run .
// JS:     scala-cli --platform js run .
// Native: scala-cli --platform native run .
```

---

# Ecosystem Diversity

Choose your style:
```scala
// Object-Oriented with Play
class UserController extends Controller {
  def users = Action { Ok(getUsers()) }
}

// Functional with Cats Effect
def users[F[_]: Async]: F[List[User]] = 
  UserRepo[F].findAll

// Script-style with Cask
@get("/users") def users() = getUserList()
```

---

# Career Growth

- Scala developers average 15-30% higher salaries
- High demand in data engineering and distributed systems
- Strong presence in fintech and streaming platforms

---

# Modern Features

```scala
// Pattern matching
value match {
  case Success(data) => process(data)
  case Failure(err)  => handleError(err)
}

// Extension methods
extension (n: Int) {
  def squared: Int = n * n
}

// Context functions
given Config = loadConfig()
def setup(): Unit = ???
```

---

# Start Your Journey

- Begin with scala-cli and simple scripts
- Pick a style that feels natural
- Join the community (Discord, Reddit) <!-- TODO add links -->
- Learn by building real projects
