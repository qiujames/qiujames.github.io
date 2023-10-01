---
title: "Improving Tabbed Content"
toc: true
tablist:
  - title: Tablist w/ Markdown File Content
    content_md_file: tabbed_content/code.md
  - title: Normal Tablist
    language: python
    code_content: |
        print("This is code written from a normal tablist")
---

It's been over a year since I've lasted posted on this blog and a lot has happened
since then. Work's been picking up and I'm getting a lot more responsibilities.
It's been a lot of fun (shoutout to my team), but that means I haven't been blogging as much as I want to.
I have a lot of things I want to write about that I really should come around to
getting to. 

Anyways, I created a panel/tab implementation for Minimal Mistakes a while
back and quite recently I had a user comment saying it worked for them! 

Pretty satisfying. 

They wanted an improved way to write the content for their tabs. Previously, 
content was specified in the markdown header of the file which isn't extensible
if your want your tabs to contain a lot of content. 

```yaml
tablist: 
  - title: Code written in the YAML Front Matter
    language: python
    code_content: |
      print("Hello World");
      print("Some more code written in the header")
      print("This is a problem if this content is longer")
  - title: Java...
```

You get the picture. This blows up your YAML front matter.

## Writing Tabbed Content in Markdown
Instead of writing the content in the header, now users can write the content in 
a separate markdown file. 

In a sample _content.md_ file, users can type their markdown content they want
and their tab will be populated with that supplemental file content.

~~~yaml
```python
print("Python Code from Another Markdown File :)");
```
~~~

They can they point their tablist to use this _code.md_ markdown
file in the YAML Front Matter like so:
~~~yaml
tablist: 
  - title: Code written in a Markdown File
    content_md_file: content.md
~~~


## Demo

It'll look the exact same as the tabbed content before 
which is a good thing! Thank you abstraction :)

{% include tablist %}


## Usage

To place a tab within a tablist that loads content from
an external markdown file, you can now specify the new `content_md_file` argument 
within a tablist tab in the YAML front matter.

| Name           | Required     | Description                                                                                                           |
| -------------- | ------------ | --------------------------------------------------------------------------------------------------------------------- |
| **title** | **Required** | Title of the content tab.  |
| **language**  | Optional | Specified programming language of the code content for syntax highlighting. See [Rouge](http://rouge.jneen.net/) for a list of supported languages |
| **code_content**  | Optional     | Code content.                                                                                             |
| **text_content**  | Optional     | Text content (markdown parsable). |
| **content_md_file** | Optional  | Markdown file name containing any tabbed content. |

And then again, drop-in the tablist include in the body where you'd like it to appear.

| Include Parameter | Required | Description                                                                                                                                                       | Default                                                                      |
| ----------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **id**            | Optional | To add multiple tablists to a document uniquely name them in the YAML Front Matter and reference in `{% raw %}{% include tablist id="tablist_id" %}{% endraw %}` | `tablist`                                                                    |

```liquid
{% raw %}{% include tablist %}{% endraw %}
<!-- OR -->
{% raw %}{% include tablist id="tablist_id" %}{% endraw %}
```


If you specify both `code_content/text_content` in _addition_ to
the newly added `content_md_file` argument, then
it will first insert the tabbed content from the markdown, and then insert
the code_content and text content. You can easily customize this
behavior if you modify the {% raw %}\_includes\tablist_content{% endraw %} file.
{: .notice--warning}

## Implementation Limitations

There's a few limitations with the implementation so far. 

The yaml files are searched relative
to the `_posts/` directory. However, you can specify a directory
when you pass in the values for `content_md_file` for some more organization.

Lastly, this is implemented using an {% raw %}`{% include_relative %}`{% endraw %} tag
which *doesn't* go through the necessary liquid front matter
preprocessing that Jekyll normally does. As a result nested
tab lists aren't supported yet.

Let me know if this works well for you if you want any further improvements!