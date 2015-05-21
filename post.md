(This is the first rough draft of the paper on
https://github.com/jlettvin/Ellipsis)
<hr/>

## Abstract
Economical markdown and rapid rendering aids rapid turnaround in drafting
which is more about expressing and organizing ideas than aesthetics.
Figures, graphs, charts, tables, listings, equations, references, and more
are numbered, labelled, positioned, and referenced easily.
Directory structure mimics paper sections and subsections.

...Contents files identify delivered sections.
__Service__ modules use externally defined languages used to render
number and label objects to be placed in the draft.
Each of the following (and more) may be used as a ``` `service` ```.
* __equation__
* __listing__
* __figure__
* __graphviz__
* __gnuplot__

Markdown uses a lightweight syntax for minimum impact on drafting.
For example: ``` `equation.gauss|The Gaussian|a e^{\frac{b x^2}{c^2}}` ```
will cause the equation to be rendered by MathJax and displayed and
``` `equation.gauss` ``` will make a standard reference to the equation.
* __SYNTAX__
* ``` `service.id|label|code` ``` Defines and renders an object;
* ``` `service.id` ``` Refers to an object
* ``` `service?notes` ``` Positions a reminder (post-it) note for later action
* ``` `service?` ``` Positions a "how-to" help note directly inline
* ``` `service` ``` Shows the current defaults for the service

## Introduction
<table><tr><td><big><b>
Sometimes you just want to write a quick draft of a scientific paper,
</b></big></td></tr></table>

but you really can't because setup for writing a paper
takes so much effort that it just isn't worth it until your material
has reached some critical level of content.
Then you have to take time away from the thoughts you want to publish
to refresh your paper-writing skills.
<table><tr><td><big><big><b>WHY?</b></big></big></td></tr></table>

Scientific communication should not be burdened by obsolete methodologies.
Let's give drafting a power boost,
and communicate more effectively and quickly. 

## Example papers (and this project) are on github.
[The Ellipsis project](https://github.com/jlettvin/Ellipsis)
has a file [Ellipsis.pdf](https://github.com/jlettvin/Ellipsis/blob/master/Ellipsis.pdf) in the top directory
illustrating some of its capabilities.
The file [VisualPhotons.pdf](https://github.com/jlettvin/Ellipsis/blob/master/example/VisualPhotons/VisualPhotons.pdf)
shows a more detailed example of Ellipsis in action.
All the sources and markdown are present in this project
to produce both these papers.

## Writing scientific papers takes patience.
Authors must generate images, graphs, plots, tables,
equations, references, listings, and other displayable objects.
These must be labelled, numbered, and referred to from the text.
A paper has sections, subsections, titles, subtitles, and time stamps.
All of this must be supported by software which is
installed, configured, updated, upgraded, and relearned.

## Currently this takes much experience to perform well.
Each object must be produced using separate software packages
for which version and order of execution may be critical.
Special knowledge is required to run programs like LaTEX
in order to have forward references and a bibliography.
Then there are so many libraries from which to choose
some of which conflict with each other.
The author must jump around from this editor to that editor,
from this software to that software,
from this library to that library,
and assemble everything in an orderly manner
with everything carefully arranged.

## Ellipsis simplifies drafting with customized mixed-language markdown
In the typical Ellipsis session, the author has two windows open:
1. their favorite browser (I use chrome or firefox)
2. their favorite programmer's editor (I use vim)

The author modifies Ellipsis markdown files
then refreshes the browser window to see the result.
That's it.

They do not write Makefiles, or run programs, or configure software.
All they need to do is write their thoughts
using a very lightweight markdown language
specialized for scientific writing.

The markdown is designed for the specific needs of scientists.
For instance, you may wish to forward reference `` `equation.euler` ``
(which would display as Equation<sup>1</sup>)
before you display it in the paper using markup this simple:
```
`equation.euler|Euler's identity|e^{i\pi}+1=0`
```
where the equation would be converted to symbolic math using MathJAX
and labelled Equation<sup>1</sup>.

You may wish to plot a comparison of the
Sinc and Airy functions `` `gnuplot.SincAiry` ``.
Ellipsis markdown enables inline specification.
```
`gnuplot.SincAiry|Comparison of Sinc and Airy|
{align="right"}
uparam(x)=pi*x/(2*1.219)
plot (sin(x)/x)**2, (2*besj1(uparam(x))/uparam(x))**2;
`
```
This markdown is converted to an in-place plot of the two functions
replacing the markdown and labelled accordingly.
Similar markdown is available for most other objects
that might appear in a scientific paper.
Where it is not supported, writing a support module for a new object
is as easy as copying one of the existing service modules
and modifying it to meet the new needs.

As can be seen, there is a very light burden on the author.

I would enjoy collaboration with another developer
who sees the potential value of optimizing
the development cycle for writing scientific papers.
