Contributing to Toolbox2docker
==================================

Docker ToolBox was a part of the [Docker](https://www.docker.com) project, and follows
the [contributing guidelines](https://github.com/docker/docker/blob/master/CONTRIBUTING.md). If you're already familiar with the way
Docker does things, you'll feel right at home.

See [Ceasing Support and Development of Docker Toolbox #898](https://github.com/docker/toolbox/issues/898)

Any work to improve the Toolbox2docker code will continue under the same code license as Docker Toolbox.

Thanks for taking the time to improve the Toolbox2docker!

## License

By contributing your code, you agree to license your contribution under the [Apache license](https://github.com/docker/toolbox/blob/master/LICENSE/LICENSE).

## Diff scpt files

.gitattributes
```
*.scpt diff=scpt
```

.git/config
```
[diff "scpt"]
    textconv = osadecompile
    binary = true
```
