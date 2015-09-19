# Quickstart

## Installation

You'll need Python 2.7, and the tools [Virtualenv][venv] and [Pip][pip] are
highly recommended.

[venv]: http://www.virtualenv.org/en/latest/
[pip]: https://pypi.python.org/pypi/pip

Once you've got that set up, you should create a virtualenv to work in,
and activate it. This keeps Hamper's libraries isolated from the rest of
your system, which helps avoid version conflicts. Run these commands in
the git repo you cloned.

```bash
$ virtualenv venv
$ source venv/bin/activate
```

> Note that on systems like Arch Linux, where Python 3 is the default, you will
> have to specificy that you want to use Python 2. In particular, you should
> use the command `virtualenv2` instead of `virtualenv`. This will create a
> Python 2 virtualenv, so you would have to worry about it for the rest of this
> guide.

To install the requirements, run

```bash
$ pip install -r requirements.txt
```

## Tests

A good way to make sure you have all the requirements is by running the tests. The tests don't rely on any configuration, so you can run them now. To run the tests run the command

```bashs
$ trial hamper
```

If you get "command not found" you may have to give a better path to trial. Try

```bash
$ venv/bin/trial hamper
```

## Configuration

You'll need to configure hamper so that your instance of Hamper is a
unique snow flake (like all the rest). Configuration is stored in a file
named `hamper.conf`. You'll notice it doesn't exist yet, but there is a
template, `hamper.conf.dist`. Copy that file, name the copy
`hamper.conf`, and edit it to reflect your desired set up.

In particular, you problably want to change the `nickname`, `server`,
`port`, `channels`, and `plugins`. These should be pretty straight
forward, but if you want more details, read
[the configuration docs][config].

[config]: config.md

## Running

The main entry point for Hamper is the command `hamper` which starts the bot.

```bash
$ hamper
```

If all you configured the bot correctly, it should start up, load any
listed plugins, connect to the IRC server, and join the specified
channels, where you can start interacting with it. Yay!

For more information about where to go from here, see the docs about
[adminstration][admin] or [plugin development][plugindev], or if you
want to deploy Hamper in a little more permanent way, check out the
deployment docs for [Heroku][heroku] or [Docker][docker]

[admin]: admin.md
[plugindev]: plugindev.md
[heroku]: heroku.md
[docker]: docker.md
