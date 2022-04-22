
# Syntax

Basically the syntax is the markdown syntax,
following the [CommonMarkdown spec](https://spec.commonmark.org),
plus Sphinx's roles and directives (that are the ones of reST plus a few more,
and you can also define yours).

That means that roles are now: 

```md
{role}`content`
```

and [directives](https://myst-parser.readthedocs.io/en/latest/syntax/syntax.html#directives-a-block-level-extension-point)

````md
```{directivename} arguments
---
key1: val1
key2: val2
---
This is
directive content
```
````

or for [sort options](https://myst-parser.readthedocs.io/en/latest/syntax/syntax.html#parameterizing-directives)

````md
```{directivename} arguments
:key1: val1
:key2: val2

This is
directive content
```
````


Using markdown syntax offers some advantages as simpler hyperlinks
but also some drawbacks (e.g. missing [literal blocks](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html#literal-blocks)).

Directives
----------

Directives can be nested by having more backticks in the outer blocks.
In addition, inner blocks can (but do not need to) be indented:

`````md

    ````{note}
    The next info should be nested
        ```{warning}
        Here's my warning
        ```
    ````

`````

Alternatively, colons can be used for [markdown-friednly
directives](https://myst-parser.readthedocs.io/en/latest/syntax/syntax.html#markdown-friendly-directives)
by simply adding `"colon_fence"` to `myst_enable_extensions`.

```md
    :::{directive}
    ...
    :::
```

This syntax is specially useful for admonitions and tables
with headers (`table` directive), as they are markdown compliant.

Math
----

The `"dollarmath"` extension allows to parse \$ and \$\$ for math equations.
In addition, setting `myst_dmath_double_inline` option to `True` allows
for writing equations with \$\$ and inline context.


It is also possible to add labels to equations

```latex
$$
e = mc^2
$$ (myeq)
```

and reference it as
```
{eq}`myeq`
```


## Substitutions

[Substitutions](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html#substitutions-with-jinja2) 
are a replacement for [reST substitutions](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html#substitutions).
They require `"substitution"` in `myst_enable_extensions`.

Substitutions can be added to {file}`conf.py`:

```python
myst_substitutions = {
  "key1": "I'm a **substitution**"
}
```

or at the top of each file:

```md
---
substitutions:
  key1: "I'm a **substitution**"
---
```

Substitutions are invoked as `{{ key1 }}` and accept
Jinja2 expressions and `env` can be used to reference
the [Sphinx environment](https://www.sphinx-doc.org/en/master/extdev/envapi.html).

## Special lists

[Definition lists](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html#definition-lists)
can be used by adding `"deflist"` to `myst_enable_extensions`:

```md
Term 1
: Definition

Term 2
: Definition
```

[Task lists](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html#task-lists)
require `"tasklist"` in `myst_enable_extensions`,
and are used as

```md
- [ ] An item that needs doing
- [x] An item that is complete
```

[Field lists](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html#field-lists)
use `"fieldlist"` in `myst_enable_extensions`
and their syntax looks like:

```md
:short: line
:long:
  with 
  several
  lines

  or even paragraphs
```

## Images

Beside the standard markdown syntax

```md
![img](img/something.png)
```

and the option to use reST directives such as
`image` or `figure`, there is the option to use
a [markdown compatible syntax](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html#markdown-figures).

## Tables

Tables follow [Github syntax](https://github.github.com/gfm/#tables-extension-)

## Footnotes

Footnotes are declared as `[^name]`
and referenced as `[^name]: description`.
They are auto-numbered unless an integer is used as name.

By default, a transition line will be placed before any footnotes.

## Extra

**Comments** are declared with `%`.

Targets are `(name)=` and can be referenced following
reST or markdown syntax:

```
{ref}`name`
{ref}`text <name>`
[](name)
[text](name) 
```

