# This is a heading 1 
## This is a heading 2 
### This is a heading 3 
#### This is a heading 4 
##### This is a heading 5 
###### This is a heading 6

**Bold text**
*Italic text*
~~Striked out text~~
==Highlighted text==
**Bold text and 
_nested italic_ text**
***Bold and italic text***

# Emojis 
#emojis
💡🔥⚡✅💻</>📱🧰⚙️🛠️🔧🔩🤖🚩⚠️📍👾🔎📖📚📕📘📓📔
📝📋📌☕︎🧋🧩 💦🌱☀️🌞🌙🌟💫👩🏽‍💻👩🏻‍💻👨🏽‍💻👨🏿‍💻
**^are supported, FYI

# Links and Aliases
#linking #alias
### There are 3 ways to link
+ Linking [[]]
	+ Wiki Link: [[Objectives]] -creates links between notes used in Obsidian's Graph View
	+ Markdown: [Project Tracker](Project%20Tracker.md) general external/internal linking
+ Aliases *like linking on a Google doc, you can rename the link*
	+   [Interview Prep](<obsidian://open?vault=EngineerAtlas&file=Overview.md>)
	+ Rename the URL by writing it in (<>)
	+ [Obsidian Help](https://help.obsidian.md)
+ Embedded files *like a picture* ![[.file_type]]

# Quotes

>I would stand and look out over the roofs of Paris and think, ‘Do not worry. You have always written before and you will write now

\- Ernest Hemingway

>You are all a lost generation

\-Gertrude Stein

>One generation passeth away, and another generation cometh; but the earth abideth forever… The sun also ariseth, and the sun goeth down, and hasteth to the place where he arose… The wind goeth toward the south, and turneth about unto the north; it whirleth about continually, and the wind returneth again according to its circuits… All the rivers run into the sea; yet the sea is not full; unto the place from whence the rivers come thither they return again.

\- Ecclesiastes

# Lists
For an unordered list - * or + before the text
- First list item 
- Second list item 
- Third list item
Ordered list
 1. First list item 
 2. Second list item 
 3. Third list item

## Tasks List
start each list item with a hyphen and space followed by `[ ]`
- [x] This is a completed task. 
- [ ] This is an incomplete task.

## Nested Lists
1. First list item 
	1. Ordered nested list item 
2. Second list item 
	- Unordered nested list item
- [ ] Task item 1 
	- [ ] Subtask 1 
- [ ] Task item 2 
	- [ ] Subtask 1

# Horizontal Rule
Use three or more stars `***`, hyphens `---`, or underscore `___` on its own line to add a horizontal bar. You can also separate symbols using spaces.
*** 
**** 
* * * 
* ---
* ---- 
- - -
- ___ ____ 
- _ _ _

# Code Blocks

```js 
function fancyAlert(arg) { 
	if(arg) { 
	$.facebox({div:'#foo'}) 
	} 
} 
```
refer to [Supported languages](https://prismjs.com/#supported-languages)

# Footnotes
This is a simple footnote[^1]. 
[^1]: This is the referenced text.
[^2]: Add 2 spaces at the start of each new line. 
This lets you write footnotes that span multiple lines. 
[^note]: Named footnotes still appear as numbers, but can make it easier to identify and link references.

*Note: Inline footnotes only work in reading view, not in Live Preview.*


### Tags and Search #tags

To create a tag, enter a hash symbol (`#`) in the editor, followed by a keyword. For example, `#meeting`.

You can also add tags using the `tags` [property](https://help.obsidian.md/Editing+and+formatting/Properties). Tags in YAML should always be formatted as a list:
```yaml
---
tags:
  - recipe
  - cooking
---
```

### Nested Tags
Nested tags define tag hierarchies that make it easier to find and filter related tags.

Create nested tags by using forward slashes (`/`) in the tag name, for example `#inbox/to-read` and `#inbox/processing`.

#### Tag Formatting
You can use any of the following characters in your tags:

- Alphabetical letters
- Numbers
- Underscore (`_`)
- Hyphen (`-`)
- Forward slash (`/`) for [Nested tags](https://help.obsidian.md/Editing+and+formatting/Tags#Nested%20tags)

### Tags Syntax
Tags can't contain blank spaces. To separate two or more words, you can instead use the following formats:

- [#camelCase](https://publish.obsidian.md/#camelCase)
- [#PascalCase](https://publish.obsidian.md/#PascalCase)
- [#snake_case](https://publish.obsidian.md/#snake_case)
- [#kebab-case](https://publish.obsidian.md/#kebab-case)




Related: #obsidian_editing