---
theme: mp-theme
size: 16:9
transition: slide 
# see https://github.com/marp-team/marp-cli/blob/main/docs/bespoke-transitions/README.md#built-in-transitions
marp: true
---

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
