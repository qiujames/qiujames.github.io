```python
print("Python Code from Another Markdown File :)");
```

You can add markdown content through a specified file now!

Since the {% raw %}`{% include %}`{% endraw %} tag
oesn't go through the necessary liquid front matter
preprocessing that Jekyll normally does, nested
tab lists aren't supported.  

Here's what the code.md that's generating this text looks like (kinda meta!)

~~~md
# code.md

```python
print("Python Code from Another Markdown File :)");
```

You can add markdown content through a specified file now!

Since the {% raw %}`{% include %}`{% endraw %} tag
oesn't go through the necessary liquid front matter
preprocessing that Jekyll normally does, nested
tab lists aren't supported.  

Here's what the code.md that's generating this text looks like (kinda meta!)
~~~