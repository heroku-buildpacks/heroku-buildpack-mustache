Heroku Buildpack to Render {{ Mustaches }}
==========================================

Render environment variables into files **at runtime** 🚀

Super handy to generate configuration files in the [12-factor](https://12factor.net/config) style.

Utilizes [Mo](https://github.com/tests-always-included/mo): [Mustache templates](http://mustache.github.io) in pure bash.

Usage
------

Add this buildpack to your app:

```bash
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-mustache.git
```

Create the file `mustache_templates.conf` in your repo. Each line is the path/name of a file (relative to the repo root) that will be rendered with [Mustache replacements](http://mustache.github.io/mustache.5.html):

```
build/index.html
conf/application.properties
```

Each template will be rendered to itself, a file of the same name. A `.mustache` suffixed file containing the original content will be leftover. This file-replacement trick supports inserting environment variables into files that are otherwise untouchable.
