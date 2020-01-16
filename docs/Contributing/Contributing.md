---
layout: default
title: Contributing
has_children: true
nav_order: 100
has_toc: false
---
# Contributing to Epitaph
{: .no_toc}
Welcome to the Epitaph wikipedia. Thank you for displaying interest in sharing your valuable knowledge to the Halo modding community.

## Articles
{: .no_toc .text-delta }

1. [Markdown Playground](docs/Contributing/markdown/)
2. [Example Article](docs/Contributing/Example/)
{:custom_toc}

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}
---
# Style Guide

All articles must have a suitable topic. The title must mirror the topic except for when the topic name is too long. Sub-topics or headings are used to separate longer articles.

* Surround single words or lines of `code` in tilda's.
* Format links using: `[click here](example.com)`
* Format images using: `![alt_text](example.com/example.png)` Alt text is displayed if the image cannot load and should describe the image in a few words. Ex. Turret on vehicle.

## Writing an Article
Every article contains an argument, an approach, and a methodology. Whether the argument communicates that an object exists or the correct steps to achieving a desirable outcome, an author still disseminates those three concepts. Authors should consider those notions while writing and reviewing their article. Articles are submitted through the [pull request](https://github.com/HaloBible/wiki/pulls) button on Github.

Epitaph contributors and maintainers expect submitted articles to be in a completed state. Authors can preview their articles by using the fork button on Github. Articles do not need to cover every concept or idea, but included information should be in a completed and presentable state. Submitting an unfinished article will result in contributors providing advice to bring it up to standards.

Every document must contain the following header data:
```
 ---
layout: default
title: Contributing -- File name and article topic
parent: Contributing -- Reflects the title of the parent file
has_children: true -- Remove if the file will have no sub-topics.
nav_order: 5 -- Alters articles listed position
has_toc: false -- Disables table of contents auto-generation.
grand_parent: Tools -- The title of the parent of the parent
 ---
 ```
* Insert quotes if special characters such as `:` are required.
* Articles under the directory "docs" do not require `parent`.
* Remove `has_toc` if wanting auto-generated table of contents.
* Articles within articles must contain the `grand_parent` line, reflecting the parent of the parent. Note that `grand_parent` non-intuitively requires an underscore separating `grand` and `parent`.

Review [Epitaph Github source](https://github.com/HaloBible/wiki/tree/gh-pages) and [Markdown Playground](docs/Contributing/Contributing/markdown/) for more formatting and styling demonstrations.

## Page Types
Epitaph implements two kinds of pages. "Home" pages and guides. A guide thoroughly explains the topic. Pages under [tools](docs/Tools/Tools/) generally contain a home page for each tool. These pages only require the necessary information for a reader to understand what the tool is, does, and its download link. More information is good, but not necessary. Guides are posted under a given tools directory.

## Headings
The `#` symbol followed with a space creates headings. Add extra hashtag symbols to create smaller headings. Main topic headings should use one hashtag symbol. Subtopics should use two hashtag symbols. Links should use three hashtag symbols. Table of contents headings should use two hash tag symbols.
If necessary, one hashtag is suitable after a table of contents. See [Assembly and Its Functionality](docs/Tools/Assembly/Assembly/#assembly-and-its-functionality) as an example.

## Inserting Table of Contents

To add a table of contents to a specific spot use the following:
```
## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}
---
```
Add `---` after the TOC to insert a line break. The next heading should appear directly after.

The command `{: .no_toc }` written under a heading stops the wiki from including that heading in the table of contents.

For more detail review [Auto-generating Table of Contents](https://pmarsceill.github.io/just-the-docs/docs/navigation-structure/#auto-generating-table-of-contents).

### Custom Table of Contents

To display sub-articles in a main article, create a custom table of contents using the following method:
```
## Custom Table Name
{: .no_toc .text-delta }
1. [Poking](docs/Tools/Assembly/Poking/)
2. Another list item
3. etc. etc. etc.
{: .custom_toc}
```
Custom table of contents requires {: .custom_toc} to add an underline to the links. Note that epitaph.dev links only require `docs/` onwards and not the entire web address.

## Citations and Crediting
Use the `>` at the start of the quote and in new lines that the quote is part of.

Place a dash, the author, followed with the place it came from. Ex. - Batman, Halo Mods Discord #channel_name.
If necessary use `[Discord](example.com)` to link to the source.

Pages under tools needing to credit authors use the following guidelines:
* A heading named `Project Contributors`
* Cite a maximum of three authors in a list.
Adjustment of these guidelines are allowed if needed to fulfil a specific purpose. Example: [Opus](docs/Tools/Opus/Opus/).

## Grammar
Write with standard English spellings such as colour and armour not "color" and "armor."

Avoid non-academic and colloquial language. Do not write "you", "me", "I", and "we." Also, avoid writing in passive voice and repeating the same word many times.
Examples:
"First, I modified the vehicle tag to be better at towing"
"The vehicle tag is the best way to edit vehicles"
To make these sentences active take the verb (action word) and place it at the beginning of the sentence then try to re-write it without the words "is" and "to be" or "can be." The second sentence lacks a detailed explanation. It needs to answer the question "Why is it better?"
"Tow heavier loads through modifying the vehicle tag."
"Editing the vehicle tag allows modders to effectively create new vehicles"