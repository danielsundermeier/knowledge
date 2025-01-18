# Git

## Workflow

- A branch must do one useful thing
- Every commit must be independent
    + Every commit must include its own tests
    + Every commit must pass all tests
- Draft commits are fine
- It's okay to discard commits completely

### Links

- [Git is my buddy: Effective Git as a solo developer](https://mikkel.ca/blog/git-is-my-buddy-effective-solo-developer/)

## Links

- [Getting The Most Out Of Git](https://www.smashingmagazine.com/2021/02/getting-the-most-out-of-git/)
- [Commitizen](https://github.com/commitizen-tools/commitizen) - define a standard way of committing rules and communicating it
- [Advanced Git Features You Didn’t Know You Needed](https://martinheinz.dev/blog/43)
- [What is Git? A Beginner's Guide to Git Version Control](https://www.freecodecamp.org/news/what-is-git-learn-git-version-control/)
- [Introduction to Git In 16 Minutes](https://vickyikechukwu.hashnode.dev/introduction-to-git-in-16-minutes?utm_source=tldrnewsletter)
- [Flight rules for Git](https://github.com/k88hudson/git-flight-rules)
- [Git from the inside out](https://maryrosecook.com/blog/post/git-from-the-inside-out)
- [Idiot proof git](https://softwaredoug.com/blog/2022/11/09/idiot-proof-git-aliases.html)

## Renaming (casesensitive)

```
git mv Foobar temp
git mv temp FooBar

git mv foo.php Foo.php
```

## Pull

```sh
git reset --hard
git clean -df
git pull
```