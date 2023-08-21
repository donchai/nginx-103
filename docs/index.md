# NGINX 103

Streamline Your App and API Management with NGINX Management Suite using NIM. This lab is an introduction to NGINX Management Suites (NMS) with various modules: API Connectivity Manager (ACM), Instance Manager (NIM), and Security Monitoring (SM). It includes the usage of NGINX Plus as a load balancer and API Gateway, as well as NGINX App Protect for API Security Protection.

Original Lab Author: Ewen Low

**Lab Overview**

For the demonstration, we will build a demo setup consisting of 1 x LB fronting API gateway clusters that connect to the API endpoints (httpbin API)."

<img width="885" alt="Screenshot 2023-08-21 at 10 45 26 PM" src="https://github.com/donchai/nginx-103/assets/6828772/fa05f8f8-ff1f-49e7-acc7-c42ff16d95f5">

```bash
copy me!
```

If the code block overlaps to the right of the text area, you can just click
the button to get the whole thing.

```bash
123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789123456789
```

You can configure `sphinx-copybutton` to detect *input prompts* in code
cells, and then both remove these prompts before copying, as well as skip
lines that *don't* start with prompts (in case they are output lines).

For example, this site has been configured to strip Python prompts (">>> ") and output lines.
Try copy-pasting the code block below.

```python
>>> a = 2
>>> print(a)
2
>>>
>>> b = 'wow'
>>> print(b)
wow
```

## Install

You can install `sphinx-copybutton` with `pip`:

```bash
pip install sphinx-copybutton
```

Or with `conda` via `conda-forge`:

```bash
conda install -c conda-forge sphinx-copybutton
```

[Here's a link to the sphinx-copybutton GitHub repository](https://github.com/ExecutableBookProject/sphinx-copybutton).

## Use

In your `conf.py` configuration file, add `sphinx_copybutton` to your
extensions list. E.g.:

```python
extensions = [
    ...
    'sphinx_copybutton'
    ...
]
```

When you build your site, your code blocks should now have little copy buttons
to their right. Clicking the button will copy the code inside!

See [](use.md) for more information about how to use `sphinx-copybutton`.

```{toctree}
:maxdepth: 2
use
contribute/index
reference/example
changelog
```

## Inspiration

The UI and design elements of `sphinx-copybutton` are heavily inspired by [GitHub's design choices](https://primer.style).
The icon we use is from [Tabler's icons set](https://tablericons.com/).
