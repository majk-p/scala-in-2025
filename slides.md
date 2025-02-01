---
theme: mp-theme
size: 16:9
transition: slide 
# see https://github.com/marp-team/marp-cli/blob/main/docs/bespoke-transitions/README.md#built-in-transitions
marp: true
---

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

 -->


--------------------------

Template left below

<!-- _class: intro -->
# Presentation intro slide :hamster:

---

# Regular slide 

Presenting some interesting content

---
<!-- _class: divider -->
# New section divider

Default divider has a blue background

Just add:
```html
<!-- _class: divider -->
```

---
# Slide with code

```scala
@main
def main() =
  println("hello world")
```

---

# Slide with code

Add line numbers with `<!-- _class: line-numbers -->`

<!-- _class: line-numbers -->

```scala
@main
def main() =
  println("hello world")
```
---
# Slide with complex code

<!-- _class: line-numbers -->

With line numbers

```scala
case class Record(
  id: String,
  value: Long
) derives Codec.AsObject
```

---
<!-- _class: divider -->
# Unordered lists

---

# Slide with non-fragmented list

- One
- Two
- Three
---
<!-- _class: divider lime-background -->
# Fragmented list

Default can have a lime background using

```html
<!-- _class: divider lime-background -->
```

---

# Slide with fragmented list

* One
* Two
* Three

---
<!-- _class: divider yellow-background -->
# Ordered and fragmented ordered lists

Default can have a yellow background using


```html
<!-- _class: divider yellow-background -->
```

---

# Ordered and fragmented ordered lists


Ordered:

1. One
2. Two
3. Three

Ordered and fragmented:

1) One
2) Two
3) Three

---

<!-- _class: divider -->

# Images

---

# Image on the left

![bg left](https://picsum.photos/720?image=29)

Syntax:
```markdown
![bg left](https://picsum.photos/720?image=29)
```

---

# Image on the right

![bg right](https://picsum.photos/720?image=11)

Syntax:
```markdown
![bg right](https://picsum.photos/720?image=11)
```
---

# Free image sources

- https://unsplash.com
- https://freeimages.com
- https://freepik.com
- https://pixabay.com
- https://pexels.com/

---

# Learn more

For more Marp syntax check out:

- https://marpit.marp.app/markdown
- https://marpit.marp.app/image-syntax
- https://github.com/marp-team/marp-core
- https://github.com/marp-team/marp-cli
- https://github.com/marp-team/marp-cli/blob/main/docs/bespoke-transitions/README.md#built-in-transitions
- Or search https://github.com/orgs/marp-team/discussions/
