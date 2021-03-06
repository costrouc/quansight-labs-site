# Quansight Labs Site

## Build information

- Built with [Lektor](https://www.getlektor.com)
- Theme based on https://github.com/Andrew-Shay/lektor-theme-simple-strap
- For blog posts from Jupyter notebooks: https://github.com/baldwint/lektor-jupyter

Lektor installs its own Python, pip and all its dependencies in a virtualenv in
a non-standard location:
```
$ cat `which lektor`
#!/usr/local/lib/lektor/bin/python
...
```

So to install dependencies that are needed, such as `nbconvert`, use
`/usr/local/lib/lektor/bin/python -m pip`.

For a local build:
```
$ curl -sf https://www.getlektor.com/install.sh | sh
$ git clone https://github.com/Quansight-Labs/quansight-labs-site.git
$ cd quansight-labs-site
$ git submodule init
$ git submodule update
$ lektor server  # serves site on localhost:5000
```

Lektor is also available on PyPI as `Lektor` and on conda-forge as `lektor`,  so the
first line above can also be replaced by either of the following lines. This is useful
if you prefer to separate your environments, or prefer the usual Python package install
methods:

```
$ conda install -c conda-forge lektor
$ pip install Lektor
```

## Deployment

`lektor build && lektor deploy` will push the static site to the `gh-pages` branch
of https://github.com/Quansight-Labs/quansight-labs-site. Note, this requires
Lektor to be installed.  **TODO**: hook this up to TravisCI, so a commit to master
deploys a new version automatically.
