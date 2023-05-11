# Public repository of instructions on how to collaborate

This repoository contains instructions on how to collaborate with[LPT](https://www.unibw.de/plasmatechnik).

## Overview

Since the early days of [inflowencer's](https://github.com/inflowencer) work in the industry and academics, he quickly
noticed that sending back and forth endless Word files etc. quickly leads to chaos and bloated inboxes. Fortunately,
smart people in the world have already found solutions for this and created

* Decentralized version control for tracking each contributor's commits
* Markdown for a unified exchange of information and minimal file size
* Software for automatic conversion of Markdown into LaTeX PDF (incl. bibliography), Word, Excel, etc.
* Virtual machines for
  - Unifying the software **regardless of the operating system** that each contributor uses so no more installation hustles of different versions
  - Running native Linux terminal regardless of the operating system

## Decentralized version control with `git`

An absolute must-know for each software developer, scientist engineer and even writer. See the [Wikipedia
article](https://en.wikipedia.org/wiki/Git#:~:text=Git%20(%2F%C9%A1ɪt%2F,source%20code%20during%20software%20development.)
for a detailed description. Basically a command-line based tool that keeps track of each contributor's file changes.
Changes are tracked through commits, that the author of the changes can arbitrarily compose and then push to the server.
These commits can then be pulled by other contributors and merged with their own ones.

* [1h YouTube tutorial for Git beginners](https://www.youtube.com/watch?v=8JJ101D3knE)
* [Online w3schools tutorial](https://www.w3schools.com/git/)

##  Markdown for unified exchange of information

Super-easy syntax for writing text documents (reports), documenting code, or writing notes. Also natively supports LaTeX equations. The following code block produces

```markdown
### Rarefied gases

Rarefied gases are characterized by non-continuous, *statistical* (free molecular) movement of the particles given by the Knudsen number

$$
\mathrm{Kn} = \frac{k_B \lambda}{\sqrt{2}\pi d^2 p \mathrm{L}} > 1 \:.
$$

A summary of gas regimes is given in the table below:

| Regime         | Knudsen number  | Example                                  |
| -------------- | --------------- | ---------------------------------------- |
| Continuum      | Kn < 0.01       | Air at ambient conditions ($p$ = 1E5 Pa) |
| Transitional   | 0.01 < Kn < 0.1 | Microchannel fluid flow ($D$ < 1E-6 m)   |
| Free molecular | Kn > 1          | Reentry of a spacecraft ($h$ > 100 km)   |
```

### Rarefied gases

Rarefied gases are characterized by non-continuous, *statistical* (free molecular) movement of the particles given by the Knudsen number

$$
\mathrm{Kn} = \frac{k_B \lambda}{\sqrt{2}\pi d^2 p \mathrm{L}} > 1 \:.
$$

A summary of gas regimes is given in the table below:

| Regime         | Knudsen number  | Example                                  |
| -------------- | --------------- | ---------------------------------------- |
| Continuum      | Kn < 0.01       | Air at ambient conditions ($p$ = 1E5 Pa) |
| Transitional   | 0.01 < Kn < 0.1 | Microchannel fluid flow ($D$ < 1E-6 m)   |
| Free molecular | Kn > 1          | Reentry of a spacecraft ($h$ > 100 km)   |

[See this guide on how to write Markdown](https://quarto.org/docs/authoring/markdown-basics.html)

