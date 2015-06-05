# Mnemosyne

Add-ons to Markdown to add interactivity.

Mnemosyne takes advantage of the elegant human-and-machine-readable syntax of
[Markdown](http://daringfireball.net/projects/markdown/syntax) and adds a layer of interactivity
with a set of new rules and syntax.

## Format

Mnemosyne is meant to be readable in both plain-text and through a Markdown renderer; it is also
meant to be intuitively actionable in these formats - that is, anyone should be able to easily use
it for things like notes and todo-lists even through a text-editor. Mnemosyne is
backwards-compatible with Markdown and does not interfere with Markdown's styling.

What Mnemosyne adds is a set of rules to interpret Markdown and make it more interactive, so
that it can be used as a kind of PIM (personal information management) system. It stays true to
Markdown's philosophy of being *easy to read*, *easy to write*, and *looking like what it means*,
and also borrows from usability and user experience design principles to make it *easy to use* as
well.

Mnemosyne content can be all in one file or across multiple files; it doesn't matter because
Mnemosyne looks for keywords in the H2 headers to determine how to interpret content. The following
sections list the content-type keywords and the way Mnemosyne interprets their content. These
keywords are not case-sensitive.

## Tasks

Tasks are unordered lists, with each item being a task. Mnemosyne borrows from the
[todo.txt](http://todotxt.com/) rules to add completion, priority, and due date markup.

```
## Tasks

- This is an unchecked item
- x This is a completed item
- (A) This is a priority item
- 2000-01-01 This is an item due on January 1st, 2000
```

All list items that appear in the same list (same bullet style, no newlines between items) are
considered to be in one set of tasks; the tasks section can have multiple sets of tasks. Task can
optionally be named by preceding the list with a line of text.

```
## Tasks

Home Improvement
- The following tasks are part of the Home Improvement task list
- This is another task
- x This is a completed task

- Since this is separated from the above list by a newline, it is not part of the Home
  Improvement task list and is unnamed
* This is also in a separate task list since it uses a different bullet style, even
  though it isn't separated by a newline
  
Named Task Set
- This is another named task set
```

## Notes

Notes are separated by a horizontal rule. The first line is assumed to be the title.

```
## Notes

_____
This is a note

* * *
This is another note using a different horizontal rule syntax

_____
This is a note. This line is the title.
This line is still the title.

This line is not. It is the content.
```


## Tags

Hashtags can be used to add context to content. Tag format is whitespace, followed by a
single hash character (#), followed by any non-whitespace characters. Tags are attributed to the
line that they appear in.

Examples:

```
## Tasks

- This task is tagged with personal #personal
- This task is not
- This task is also not tagged @personal
- This task is tagged with both personal and pets #personal #pets

## Notes

_____
This line in this note is tagged with personal #personal

This line is tagged with work #work
```
