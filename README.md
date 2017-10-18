# chroma-powershellconsole-css

PowerShell Console CSS for the Chroma Syntax Highlighter (as used by [Hugo](https://gohugo.io))

This is a stylesheet you can use with [Chroma](https://github.com/alecthomas/chroma) to create code sections in the style of the PowerShell default console window.

To use (for Hugo):

1. Set `pygmentsUseClassic` to `false` (or remove it entirely as Hugo defaults to Chroma);
2. Set `pygmentsUseClasses` to `true` (this allows the CSS stylesheet to work);
3. Put the `chroma-powershellconsole.css` stylesheet into `static\css` in your Hugo site;
4. Add loading the `css\chroma-powershellconsole.css` into the <head> of your page (using for example `<link rel="stylesheet" type="text/css" href="/css/chroma-powershellconsole.css"`);

That's it.

Let me know of any suggestions or issues. PR's are welcome.

## How To Have Error Messages Display In Your Code In Hugo

The Chroma lexers (or the Pygments ones that they are based on) don't detect error messages in your PowerShell code text so I've added styling of error lines like the PowerShell console. To have them displayed properly use this in your post:

```
// Your post markdown

<div id="pscode-highlight-error"> 
{{< highlight powershell "hl_lines=3-5" .}}
PS> Some code

Some error text
that spills onto multiple
lines
{{< / highlight }}
</div>

// Your post markdown
```

Make sure you have the <div id="pscode-highlight-error"> tag before the code block. Then highlight those lines you want to appear as error messages using the [hl_lines option in Hugo](https://gohugo.io/content-management/syntax-highlighting/#configure-syntax-hightlighter). Don't forget to close the <div> tag.

What this does it restyle the highlighted code to appear as error styled text. However for each code block you can't have highlighted text and error styled text. You get one or the other.

You could used a shortcode for this in Hugo if you wanted. This is just the CSS. How you implement it is entirely up to you!