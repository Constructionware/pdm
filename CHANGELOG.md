Release v0.8.6 (2020-07-09)
---------------------------

### Bug Fixes

- Fix a bug that extra sources are not respected when fetching distributions. [#127](https://github.com/frostming/pdm/issues/127)


Release v0.8.5 (2020-06-24)
---------------------------

### Bug Fixes

- Fix a bug that `pdm export` fails when the project doesn't have `name` property. [#126](https://github.com/frostming/pdm/issues/126)

### Dependencies

- Upgrade dependency `pip` to `20.1`. [#125](https://github.com/frostming/pdm/issues/125)


Release v0.8.4 (2020-05-21)
---------------------------

### Features & Improvements

- Add a new command `export` to export to alternative formats. [#117](https://github.com/frostming/pdm/issues/117)

### Miscellany

- Add Dockerfile and pushed to Docker Hub. [#122](https://github.com/frostming/pdm/issues/122)


Release v0.8.3 (2020-05-15)
---------------------------

### Bug Fixes

- Fix the version constraint parsing of wheel metadata. [#120](https://github.com/frostming/pdm/issues/120)


Release v0.8.2 (2020-05-03)
---------------------------

### Bug Fixes

- Update resolvers to `resolvelib` 0.4.0. [#118](https://github.com/frostming/pdm/issues/118)


Release v0.8.1 (2020-04-22)
---------------------------

### Dependencies

- Switch to upstream `resolvelib 0.3.0`. [#116](https://github.com/frostming/pdm/issues/116)


Release v0.8.0 (2020-04-20)
---------------------------

### Features & Improvements

- Add a new command to search for packages [#111](https://github.com/frostming/pdm/issues/111)
- Add `show` command to show package metadata. [#114](https://github.com/frostming/pdm/issues/114)

### Bug Fixes

- Fix a bug that environment markers cannot be evaluated correctly if extra's are connected with "or". [#107](https://github.com/frostming/pdm/issues/107)
- Don't consult PyPI JSON API by default for package metadata. [#112](https://github.com/frostming/pdm/issues/112)
- Elimate backslashes in markers for TOML documents. [#115](https://github.com/frostming/pdm/issues/115)


Release v0.7.1 (2020-04-13)
---------------------------

### Bug Fixes

- Editable packages requires `setuptools` to be installed in the isolated environment.

Release v0.7.0 (2020-04-12)
---------------------------

### Features & Improvements

- Disable loading of site-packages under PEP 582 mode. [#100](https://github.com/frostming/pdm/issues/100)

### Bug Fixes

- Fix a bug that TOML parsing error is not correctly captured. [#101](https://github.com/frostming/pdm/issues/101)
- Fix a bug of building wheels with C extensions that the platform in file name is incorrect. [#99](https://github.com/frostming/pdm/issues/99)


Release v0.6.5 (2020-04-07)
---------------------------

### Bug Fixes

- Unix style executable script suffix is missing.


Release v0.6.4 (2020-04-07)
---------------------------

### Features & Improvements

- Update shebang lines in the exetuable scripts when doing `pdm use`. [#96](https://github.com/frostming/pdm/issues/96)
- Auto detect commonly used venv directories. [#97](https://github.com/frostming/pdm/issues/97)


Release v0.6.3 (2020-03-30)
---------------------------

### Bug Fixes

- Fix a bug of moving files across different file system. [#95](https://github.com/frostming/pdm/issues/95)


Release v0.6.2 (2020-03-29)
---------------------------

### Bug Fixes

- Validate user input for `python_requires` when initializing project. [#89](https://github.com/frostming/pdm/issues/89)
- Ensure `wheel` package is available before building packages. [#90](https://github.com/frostming/pdm/issues/90)
- Fix an issue of remove command that will unexpectedly uninstall packages in default section. [#92](https://github.com/frostming/pdm/issues/92)

### Dependencies

- Update dependencies `pythonfinder`, `python-cfonts`, `pip-shims` and many others.
  Drop dependency `vistir`. [#89](https://github.com/frostming/pdm/issues/89)


Release v0.6.1 (2020-03-25)
---------------------------

### Features & Improvements

- Redirect output messages to log file for installation and locking. [#84](https://github.com/frostming/pdm/issues/84)

### Bug Fixes

- Fix a bug that parallel installation fails due to setuptools reinstalling. [#83](https://github.com/frostming/pdm/issues/83)


Release v0.6.0 (2020-03-20)
---------------------------

### Features & Improvements

- Support specifying build script for C extensions. [#23](https://github.com/frostming/pdm/issues/23)
- Add test cases for `pdm build`. [#81](https://github.com/frostming/pdm/issues/81)
- Make it configurable whether to consult PyPI JSON API since it may be not trustable.
- Support parallel installation.
- Add new command `pmd import` to import project metadata from `Pipfile`, `poetry`, `flit`, `requirements.txt`.
  [#79](https://github.com/frostming/pdm/issues/79)
- `pdm init` and `pdm install` will auto-detect possibile files that can be imported.

### Bug Fixes

- Fix wheel builds when `package_dir` is mapped. [#81](https://github.com/frostming/pdm/issues/81)
- `pdm init` will use the current directory rather than finding the parents when
global project is not activated.


Release v0.5.0 (2020-03-14)
---------------------------

### Features & Improvements

- Introduce a super easy-to-extend plug-in system to PDM. [#75](https://github.com/frostming/pdm/issues/75)

### Improved Documentation

- Documentation on how to write a plugin. [#75](https://github.com/frostming/pdm/issues/75)

### Bug Fixes

- Fix a typo in metadata parsing from `plugins` to `entry_points`


Release v0.4.2 (2020-03-13)
---------------------------

### Features & Improvements

- Refactor the CLI part, switch from `click` to `argparse`, for better extensibility. [#73](https://github.com/frostming/pdm/issues/73)
- Allow users to configure to install packages into venv when it is activated. [#74](https://github.com/frostming/pdm/issues/74)


Release v0.4.1 (2020-03-11)
---------------------------

### Features & Improvements

- Add a minimal dependency set for global project. [#72](https://github.com/frostming/pdm/issues/72)


Release v0.4.0 (2020-03-10)
---------------------------

### Features & Improvements

- Global project support
  - Add a new option `-g/--global` to manage global project. The default location is at `~/.pdm/global-project`.
  - Use the virtualenv interpreter when detected inside an activated venv.
  - Add a new option `-p/--project` to select project root other than the default one. [#30](https://github.com/frostming/pdm/issues/30)
- Add a new command `pdm config del` to delete an existing config item. [#71](https://github.com/frostming/pdm/issues/71)

### Bug Fixes

- Fix a URL parsing issue that username will be dropped in the SSH URL. [#68](https://github.com/frostming/pdm/issues/68)

### Improved Documentation

- Add docs for global project and selecting project path. [#30](https://github.com/frostming/pdm/issues/30)


Release v0.3.2 (2020-03-08)
---------------------------

### Features & Improvements

- Display all available Python interpreters if users don't give one in `pdm init`. [#67](https://github.com/frostming/pdm/issues/67)

### Bug Fixes

- Regard `4.0` as infinite upper bound when checking subsetting. [#66](https://github.com/frostming/pdm/issues/66)


Release v0.3.1 (2020-03-07)
---------------------------

### Bug Fixes

- Fix a bug that `ImpossiblePySpec`'s hash clashes with normal one.


Release v0.3.0 (2020-02-28)
---------------------------

### Features & Improvements

- Add a new command `pdm config` to inspect configurations. [#26](https://github.com/frostming/pdm/issues/26)
- Add a new command `pdm cache clear` to clean caches. [#63](https://github.com/frostming/pdm/issues/63)

### Bug Fixes

- Correctly show dependency graph when circular dependencies exist. [#62](https://github.com/frostming/pdm/issues/62)

### Improved Documentation

- Write the initial documentation for PDM. [#14](https://github.com/frostming/pdm/issues/14)


Release v0.2.6 (2020-02-25)
---------------------------

### Features & Improvements

- Improve the user interface of selecting Python interpreter. [#54](https://github.com/frostming/pdm/issues/54)

### Bug Fixes

- Fix the wheel installer to correctly unparse the flags of console scripts. [#56](https://github.com/frostming/pdm/issues/56)
- Fix a bug that OS-dependent hashes are not saved. [#57](https://github.com/frostming/pdm/issues/57)


Release v0.2.5 (2020-02-22)
---------------------------

### Features & Improvements

- Allow specifying Python interpreter via `--python` option in `pdm init`. [#49](https://github.com/frostming/pdm/issues/49)
- Set `python_requires` when initializing and defaults to `>={current_version}`. [#50](https://github.com/frostming/pdm/issues/50)

### Bug Fixes

- Always consider wheels before tarballs; correctly merge markers from different parents. [#47](https://github.com/frostming/pdm/issues/47)
- Filter out incompatible wheels when installing. [#48](https://github.com/frostming/pdm/issues/48)


Release v0.2.4 (2020-02-21)
---------------------------

### Bug Fixes

- Use the project local interpreter to build wheels. [#43](https://github.com/frostming/pdm/issues/43)
- Correctly merge Python specifiers when possible. [#4](https://github.com/frostming/pdm/issues/4)


Release v0.2.3 (2020-02-21)
---------------------------

### Bug Fixes

- Fix a bug that editable build generates a malformed `setup.py`.


Release v0.2.2 (2020-02-20)
---------------------------

### Features & Improvements

- Add a fancy greeting banner when user types `pdm --help`. [#42](https://github.com/frostming/pdm/issues/42)

### Bug Fixes

- Fix the RECORD file in built wheel. [#41](https://github.com/frostming/pdm/issues/41)

### Dependencies

- Add dependency `python-cfonts` to display banner. [#42](https://github.com/frostming/pdm/issues/42)


Release v0.2.1 (2020-02-18)
---------------------------

### Bug Fixes

- Fix a bug that short python_version markers can't be parsed correctly. [#38](https://github.com/frostming/pdm/issues/38)
- Make `_editable_intall.py` compatible with Py2.


Release v0.2.0 (2020-02-14)
---------------------------

### Features & Improvements

- New option: `pdm list --graph` to show a dependency graph of the working set. [#10](https://github.com/frostming/pdm/issues/10)
- New option: `pdm update --unconstrained` to ignore the version constraint of given packages. [#13](https://github.com/frostming/pdm/issues/13)
- Improve the error message when project is not initialized before running comands. [#19](https://github.com/frostming/pdm/issues/19)
- Pinned candidates in lock file are reused when relocking during `pdm install`. [#33](https://github.com/frostming/pdm/issues/33)
- Use the pyenv interperter value if pyenv is installed. [#36](https://github.com/frostming/pdm/issues/36)
- Introduce a new command `pdm info` to show project environment information. [#9](https://github.com/frostming/pdm/issues/9)

### Bug Fixes

- Fix a bug that candidate hashes will be lost when reused. [#11](https://github.com/frostming/pdm/issues/11)

### Dependencies

- Update `pip` to `20.0`, update `pip_shims` to `0.5.0`. [#28](https://github.com/frostming/pdm/issues/28)

### Miscellany

- Add a script named `setup_dev.py` for the convenience to setup pdm for development. [#29](https://github.com/frostming/pdm/issues/29)


Release v0.1.2 (2020-02-09)
---------------------------

### Features

- New command pdm use to switch python versions. [#8](https://github.com/frostming/pdm/issues/8)
- New option pdm list --graph to show a dependency graph. [#10](https://github.com/frostming/pdm/issues/10)
- Read metadata from lockfile when pinned candidate is reused.

Release v0.1.1 (2020-02-07)
---------------------------

### Features

- Get version from the specified file. [#6](https://github.com/frostming/pdm/issues/6)
- Add column header to pdm list output.

Release v0.1.0 (2020-02-07)
---------------------------

### Bugfixes

- Pass exit code to parent process in pdm run.
- Fix error handling for CLI. [#19](https://github.com/frostming/pdm/issues/19)

### Miscellany

- Refactor the installer mocking for tests.

Release v0.0.5 (2020-01-22)
---------------------------

### Improvements

- Ensure pypi index url is fetched in addition to the source settings. [#3](https://github.com/frostming/pdm/issues/3)

### Bugfixes

- Fix an issue that leading "c"s are mistakenly stripped. [#5](https://github.com/frostming/pdm/issues/5)
- Fix an error with PEP 517 building.

Release v0.0.4 (2020-01-22)
---------------------------

### Improvements

- Fix editable installation, now editable scripts can also be executed from outside!
- Content hash is calculated based on dependencies and sources, not other metadata.

### Bugfixes

- Fix an issue that editable distributions can not be removed.

Release v0.0.3 (2020-01-22)
---------------------------

### Features

- Add `pdm init` to bootstrap a project.

Release v0.0.2 (2020-01-22)
---------------------------

### Features

- A complete functioning PEP 517 build backend.
- `pdm builld` command.

### Miscellany

- Add a Chinese REAME

### Features

- Add `pdm init` to bootstrap a project.

Release v0.0.1 (2020-01-20)
---------------------------

### Features

- A dependency resolver that just works.
- A PEP 582 installer.
- PEP 440 version specifiers.
- PEP 508 environment markers.
- Running scripts with PEP 582 local packages.
- Console scripts are injected with local paths.
- A neet CLI.
- add, lock, list, update, remove commands.
- PEP 517 build backends.
- Continuous Integration.
