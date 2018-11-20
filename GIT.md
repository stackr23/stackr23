# GIT

## declarative commit msg

* < 50 chars  
* be specific
* target tasks, not files
* use action keywords: add, change, move to, ...
    * CC keywords

### conventional commits
> https://www.conventionalcommits.org

__prefix__  
* __fix__ - patches a bug in your codebase (this correlates with PATCH in semantic versioning)  
* __feat__ -  introduces a new feature to the codebase (this correlates with MINOR in semantic versioning)  
* __BREAKING__ - introduces a breaking API change (correlating with MAJOR in semantic versioning)
    - can be part of commits of any type

__other keywords__ (angular specification)  
style, perf, chore, ci, refactor, test, docs

__for example__
`feat(semantic-release): add CI publishing + CHANGELOG generator`  
`fix(deps): remove "obsolet-package"`  
`docs: remove TOC`
`style(header): add gradient fallback for IE`  
```
feat(build): add npm scripts "build" and "test"
BREAKING CHANGE: index now default exports /dist (.default for ES usage)
```

### abss style - TBD
feat, fix, style, refactor, ???

use (only) in PR/merge commits  


### tools

__commit msg__  
gitmoji, commitizien, commitlint

__conventional commits__  
semantic-release, conventional-changelog, ...

## branching
> tip: show branch in console to prevent mistakes

__merge/squash/rebase__  
=> merge is declarative  
=> squash good for encapsulated module code  
=> rebase is cleaner, can cause a lot of troubles

### feature branches
tasks bündeln -> sammeltask = feature < milestones  
__feature/header:__ fix menu toggle, fix slider in IE, style buttons, ...  

#### merge workflow

branch from stage - if task is in actual milestone  
branch from master - only if task is hotfix  

git checkout -b feature/headerHero  
... do work ...  
git checkout development // dev server  
git merge feature/headerHero // merge feature into dev  
=> testing phase  
PM gibt OK  
git checkout stage // stage server  
git merge feature/headerHero // merge feature into stage  
=> milestone wird abgeliefert & kunde gibt feedback  
// on stage   
git checkout -b feedback/feature/headerHero  
...  
git checkout dev  
git merge feedback/feature/headerHero  
=> test  
...  
