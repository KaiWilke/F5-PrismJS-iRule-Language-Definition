# Prism.js language definition for iRules
The repository contains a [Prism.js](https://prismjs.com/) language definition for F5 iRules, which are a scripting language used to customize and control the behavior of F5 load balancers. The language definition is based on a reduced TCL 8.4 syntax and F5-specific commands based on TMOS, specifically version 16.1.3. 

The language definition can be used to highlight iRule code within websites using the Prism.js framework.

![This is an image](/Highlight-Example.png)

## About iRule language definition
The iRule language definition is based on the TCL language definition created by [Peter Chaplin](https://github.com/PeterChaplin). I used his definition but then heavily customized the underlying RegEx signatures to improve the detection rate, boost performance, and include F5-specific commands.

The iRule language definition can be plugged into your website via the "language-irule" CSS class as shown below.
```
<code class="language-irule">
    #Insert iRule code
</code>
```
## About CSS support
The iRule language definition is based on the TCL language definition to support the various Prism.js color themes. The iRule language definition introduces new token classes for F5-specific commands ('f5keyword', 'f5denied', and 'f5removed') which default to the 'keyword' token class unless you explicitly add CSS to adjust their styles. For the screenshot above, I've used the CSS code below to adjust the styling of the individual token classes as needed.
```
/* Style definition for iRule Languge */
.token.comment { color: silver; }
.token.string { color: lightblue; }
.token.variable { color: darkorange; }
.token.keyword { color: deepskyblue; }
.token.builtin { color: yellow; }
span.token.f5keyword.keyword { color: #e4002b; }
span.token.f5denied.keyword { color: white; background-color: orange; text-decoration: line-through; }
span.token.f5removed.keyword { color: white; background-color: red; text-decoration: line-through; }
.token.operator { color: lime; }
```
Cheers, Kai
