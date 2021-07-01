# A Peek Behind the "Link", the Web's Superpower

## The Link Is Born

If the web is essentially a way to exchange text, how is it better than books?
In addition to being freely accessible and distributable for virtually no cost,
texts created on the web can refer to one another, a process that's so common
we might miss how special it is. On the Web, HTML documents can organically
relate (link) to one another, allowing pieces of information to reference one
another without the constraint of a hierarchical structure.

This idea was discovered by [Tim Berners-Lee][TBL] while he was working at
European Organization for Nuclear Research (CERN).

## A Blueprint for Implementing Links

How can one text reference another text? Let's daydream and figure out the
components needed so that one document can refer to another.

```
Socrates bio

Socrates was a classical Greek philosopher credited as one of the founders of
Western philosophy and is known as the first moral philosopher...
```

And...

```
Plato bio
...
Along with his teacher, Socrates (we would like to reference the `Socrates bio` here)...
```

How can `Plato's bio` reference `Socrates bio`?

1. We need an "address" for the `Socrates bio` document
2. We need to have a word or idea suggest "Socrates", a "trigger."

To achieve these two goals we need to _describe_ the data in the document using
the _same_ technology ("text") that makes up the document. We need to provide
"metadata" &mdash; data about data.  Below we'll explore Tim Berners-Lee's
approach.

## How Tim Berners-Lee Solved the Problem

Tim Berners-Lee developed an annotation language named Hypertext Markup
Language (HTML).  HTML is a language to create content _as well as_ describe
the _meaning_ of certain blocks of text.

"Meaning" is denoted by "wrapping" the text in "tags" or built-in content 
classifications. Each tag broadly defines the marked-up content. Slight 
variations between usages of a tag can be captured by providing a specific 
_tag_ with an _attribute_. These terms might seem abstract, but should become 
clearer with an example. We could imagine a tag called `<telephone>` which has 
attribute `location="work"` or `location="mobile"` and which wraps content like 
`(415)555-1212`.

Let's move _back_ from the specific to the abstract and take a look at the
generalized format of an HTML tag.

## Anatomy of an HTML Tag

```html
<opening tag content-attribute=attribute value>
    Content
</closing tag> <!-- its a closing tag because the tag name begins with a '/'. By the way, this is an HTML comment -->
```

To return to our question, how do we "link" data in HTML?

In our case, we want to describe a link between two pieces of information, Socrates' and Plato's bios. If
we were to Google [how to define a link with html]()

![Google search result for "How to define a link with HTML][search-result]

Google provides a good start. From the top result snippet, we learn that:

1. Use the `<a>` **tag** (a type of element) to define a link
2. Use the `href` **attribute** to state where the external data is located

With these instructions, we can translate our generic tag into an `<a>` tag.

We replace this generic form:

```html
<!-- These are comments  -->
<!-- Generic tag -->
<opening tag content-attribute=attribute value>
    Content
</closing tag>
```

with:

```html
<!-- Actual link tag -->
<a href='https://en.wikipedia.org/wiki/Socrates'>
    Socrates
</a>
```

We just used HTML to build a link and express one of the most fundamental
features of the web. The ability to relate information to one another.

This simple pattern applies to all HTML elements.

1. Tags classify the type of data
2. Attributes describe the specific occurrence of an HTML element

Referring back to our original "Socrates" example.

1. Universal addresses are called URL (Uniform Resource Locator). We specify
   the pointed-to resource's address (URL) in an attribute called the `href`
   within the markup tag `<a>`
2. `<a>` "wraps" the "trigger" word "Socrates" and denotes the ending of the
   "wrapping" with its closing tag `</a>`.

**We'll explore actually writing tags more in subsequent sections, so if you feel
like you need more practice we'll be revisiting and reviewing these concepts in
fine detail in the next section**.


[TBL]: https://en.wikipedia.org/wiki/Tim_Berners-Lee
[search-result]: https://curriculum-content.s3.amazonaws.com/web-development/how-to-define-a-link-with-html.jpeg

## Does this need an update?

Please open a [GitHub issue](https://github.com/learn-co-curriculum/phrg-a-peek-behind-the-link/issues) or [pull-request](https://github.com/learn-co-curriculum/phrg-a-peek-behind-the-link/pulls). Provide a detailed description that explains the issue you have found or the change you are proposing. Then "@" mention your instructor on the issue or pull-request, and send them a link via Connect.

<p data-visibility='hidden'>PHRG A Peek Behind the "Link", the Web's Superpower</p>
