# Hypermarkdown.com

---

!!! warning
    This site is currently being constructed, and has not reached a release. When this warning is removed, a version has been achieved. I'm taking a good, hard look at this, because there are some things that might be "enough", and that they just need codified.


We all know the story. [John Gruber and Aaron Swartz makes Markdown](https://en.wikipedia.org/wiki/Markdown#History), and suddenly there's an itch scratched. A simple, readable format to text that is transferrable and can be rendered everywhere.

But there's one problem. A very big problem. There are so many more things that Markdown can and should do, everyone went off and made the thing they needed. Github made the most headway with GFM, but MultiMarkdown does some great stuff. Critic Markup. All the Python extensions. More and more and more...

And so it is time to evolve. Text became Hypertext. Now Markdown becomes Hypermarkdown.

---

## What is it?

Hypermarkdown is a specification. It seeks to unify several different ideas while never violating the original concept of human-readable text as source.

To start with, there is no compiler yet. The first part of this project is to lay out what and how, and then a spec will drive development.

## Concept and Compatibility

> Axiom: All Hypermarkdown files must be plain text.

- Hypermarkdown files should have the extension .hmd, or .hypermd
- Hypermarkdown styles should have the extension .hcss, or .hypercss

Hypermarkdown files stand on their own with formatting according to the Hypermarkdown spec. This means that every [Commonmark](https://commonmark.org) format will work, no matter what.

!!! Info
    Axiom: The Commonmark specification is a complete subset within Hypermarkdown.

Hypermarkdown styles can be fashioned in an accompanying file. This means that if `file.hmd` and `file.hcss` exist in the same path, the style is automatically applied.

!!! Info
    Axiom: All Hypermarkdown files will automatically obey its accompanying .hcss file for style.

Secondarily, within any path, a special name of hyperstyle.hcss will apply its rules second, but are available to all files in that path.

!!! Info
    Axiom: All Hypermarkdown files will automatically obey `hyperstyle.hcss` in its path, secondarily.

If a `hyperstyle.hcss` is not found, rendering will go up one level and check until it runs out of levels, or finds a `hyperstyle.hcss` file. 

!!! Info
    Axiom: Rendering will attempt to find `hyperstyle.hcss` in higher paths unless told not to look.

All `.hcss` file content must start with:

```hcss
Use hyperstyle = "no"
```
or

```hcss
Use hyperstyle = "yes"
```

And the default will be `"no"`


_And that's it for files._

---

Now, let's talk about all the cool things you can do within Hypermarkdown...

