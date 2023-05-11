# Public repository of instructions on how to collaborate

This repoository contains instructions on how to collaborate with [LPT](https://www.unibw.de/plasmatechnik).

## Quick start

| Step | Note | Link |
| --- | ------ | -------------- |
| Install WSL2 (Ubuntu) | This step is only required for Windows users | [https://learn.microsoft.com/en-us/windows/wsl/install](https://learn.microsoft.com/en-us/windows/wsl/install) |
| Install Visual Code | IDE & source control | [https://code.visualstudio.com](https://code.visualstudio.com) |
| Install docker desktop | Light-weight virtual machine | [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/) |
| Create a GitHub account | For GitHub and Gitlab | [https://github.com](https://github.com) |

Now you're good to go. To access the repositories for collaboration, you have to:

1. Login to Github and create a [personal access token](https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). Be sure to save it somewhere save on your computer.
2. Login to [https://gitlab.com](https://gitlab.com) and create a [personal access token](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html#create-a-personal-access-token). Be sure to save it somewhere save on your computer.
3. Send your **GitHub** and **Gitlab usernames** to inflowencer so he can add you to the repositories and give you required access rights.
4. Install `glab` for your terminal and login: 
   ```sh
   cd ~
   mkdir -p Downloads && cd Downloads
   wget https://gitlab.com/gitlab-org/cli/-/releases/v1.29.2/downloads/glab_1.29.2_Linux_x86_64.deb
   sudo apt install ./glab_1.29.2_Linux_x86_64.deb
   # Login
   glab auth login # use gitlab.com, your gitlab username and personal access token to login
   ```

Now you're set to clone, pull and push to repositories inside Gitlab and GitHub. Yay!

## Recommendations

| Software | Recommendation |
| ----- | ------------------|
| Visual Code Extensions | pandoc-citer &bullet; markdown all in one &bullet; markdown preview enhanced &bullet; git lens &bullet; git history &bullet; python &bullet; openfoam &bullet; PDF viewer &bullet; rainbow csv &bullet; remote ssh &bullet; wsl
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

An absolute must-know for each software developer, scientist engineer and even writer. See the [Wikipedia article](https://en.wikipedia.org/wiki/Git#:~:text=Git%20(%2F%C9%A1ɪt%2F,source%20code%20during%20software%20development.)
for a detailed description. Basically a command-line based tool that keeps track of each contributor's file changes.
Changes are tracked through commits that the author of the changes can arbitrarily compose and then push to the server.
These commits can then be pulled by other contributors and merged with their own ones.

* [1h YouTube tutorial for Git beginners](https://www.youtube.com/watch?v=8JJ101D3knE)
* [Online w3schools tutorial](https://www.w3schools.com/git/)

## `Markdown` for unified exchange of information

Super-easy syntax for writing text documents (reports), documenting code, or writing notes. Also natively supports LaTeX equations. The following code block produces

`````markdown
### Rarefied gases

Rarefied gases are characterized by non-continuous, *statistical*
(free molecular) movement of the particles given by the Knudsen number

$$
\mathrm{Kn} = \frac{k_B T}{\sqrt{2}\pi d^2 p \mathrm{L}} > 1
$$

A summary of gas regimes is given in the table below:

| Regime         | Knudsen number  | Example                                  |
| -------------- | --------------- | ---------------------------------------- |
| Continuum      | Kn < 0.01       | Air at ambient conditions ($p$ = 1E5 Pa) |
| Transitional   | 0.01 < Kn < 0.1 | Microchannel fluid flow ($D$ < 1E-6 m)   |
| Free molecular | Kn > 1          | Reentry of a spacecraft ($h$ > 100 km)   |

Corresponding `Python` code to calculate Kn:

```python
import numpy as np

k_B = 1.38E-23  # Boltzmann Constant, J/K
T   = 300       # Temperature, K
d   = 3.6E-10   # Nitrogen kinetic diameter, m
p   = 1E5       # Pressure, Pa
L   = 0.35      # Characteristic length, m

Kn = k_B * T / ( np.sqrt(2) * np.pi * d**2 * p * L)

print(round(Kn, 3))
```
`````

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

Corresponding `Python` code to calculate Kn:

```python
import numpy as np

k_B = 1.38E-23  # Boltzmann Constant, J/K
T   = 300       # Temperature, K
d   = 3.6E-10   # Nitrogen kinetic diameter, m
p   = 1E5       # Pressure, Pa
L   = 0.35      # Characteristic length, m

Kn = k_B * T / ( np.sqrt(2) * np.pi * d**2 * p * L)

print(round(Kn, 3))
```

[See this guide on how to write Markdown](https://quarto.org/docs/authoring/markdown-basics.html)

## `pandoc` for automatic conversion of `Markdown`

