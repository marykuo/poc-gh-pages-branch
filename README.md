# PoC of GitHub Pages Branch-based

This is a proof of concept repository to demonstrate how GitHub Pages serves files based on the branch and file structure.

## GitHub Pages Branch-based

- Source: root or /docs folder of a selected branch.
- Pros: Simple for basic HTML/CSS projects without a build step.
- Cons: Limited customization, no build tools, and manual updates.

How to Enable:

1. Go to Settings > Pages.
2. Under Build and deployment > Source, select Deploy from a branch.
3. Choose your branch (e.g., `main` or `gh-pages`) and folder (`/root` or `/docs`).

## Example Structure and Behavior

### Case #1

- branch: main
- folder: /root

```
├── docs
│   ├── child
│   │   ├── index.html <-- docs/child homepage
│   │   └── other.html
│   ├── index.html <-- docs homepage
│   └── other.html
├── README.md
└── index.html <-- homepage
```

The priority of files for GitHub Pages is as follows:

1. index.html in the root folder
2. README.md in the root folder

Links to access the pages:

| File Path              | URL                                                                                                                                                                                                    |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| /index.html            | https://marykuo.github.io/poc-gh-pages-branch/ <br> https://marykuo.github.io/poc-gh-pages-branch/index <br> https://marykuo.github.io/poc-gh-pages-branch/index.html                                  |
| /other.html            | https://marykuo.github.io/poc-gh-pages-branch/other <br> https://marykuo.github.io/poc-gh-pages-branch/other.html                                                                                      |
| /docs/index.html       | https://marykuo.github.io/poc-gh-pages-branch/docs/ <br> https://marykuo.github.io/poc-gh-pages-branch/docs/index <br> https://marykuo.github.io/poc-gh-pages-branch/docs/index.html                   |
| /docs/other.html       | https://marykuo.github.io/poc-gh-pages-branch/docs/other <br> https://marykuo.github.io/poc-gh-pages-branch/docs/other.html                                                                            |
| /docs/child/index.html | https://marykuo.github.io/poc-gh-pages-branch/docs/child/ <br> https://marykuo.github.io/poc-gh-pages-branch/docs/child/index <br> https://marykuo.github.io/poc-gh-pages-branch/docs/child/index.html |
| /docs/child/other.html | https://marykuo.github.io/poc-gh-pages-branch/docs/child/other <br> https://marykuo.github.io/poc-gh-pages-branch/docs/child/other.html                                                                |

### Case #2 (current)

- branch: main
- folder: /docs

```
├── docs
│   ├── child
│   │   ├── index.html <-- docs/child homepage
│   │   └── other.html
│   ├── index.html <-- homepage
│   └── other.html
├── README.md
└── index.html <-- ignored because /docs is selected
```

The priority of files for GitHub Pages is as follows:

1. index.html in the /docs folder
2. README.md in the /docs folder

Links to access the pages:

| File Path              | URL                                                                                                                                                                                     |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /docs/index.html       | https://marykuo.github.io/poc-gh-pages-branch/ <br> https://marykuo.github.io/poc-gh-pages-branch/index <br> https://marykuo.github.io/poc-gh-pages-branch/index.html                   |
| /docs/other.html       | https://marykuo.github.io/poc-gh-pages-branch/other <br> https://marykuo.github.io/poc-gh-pages-branch/other.html                                                                       |
| /docs/child/index.html | https://marykuo.github.io/poc-gh-pages-branch/child/ <br> https://marykuo.github.io/poc-gh-pages-branch/child/index <br> https://marykuo.github.io/poc-gh-pages-branch/child/index.html |
| /docs/child/other.html | https://marykuo.github.io/poc-gh-pages-branch/child/other <br> https://marykuo.github.io/poc-gh-pages-branch/child/other.html                                                           |
