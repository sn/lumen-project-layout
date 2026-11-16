# Projects & Tasks for Lumen

Open a project's tabs, splits and dev environment, and run its tasks. A
plugin for the [Lumen](https://github.com/lumenshell/lumen) terminal.

- **Open Project** (Ctrl+Shift+L, ⌘⇧L) finds `.lumen-layout.toml` in the
  pane's folder or above and opens its tabs and splits. Every command is shown
  to you before it first runs, and again whenever the file changes. Then it
  starts the project's dev environment in a new tab, each task in its own
  labelled split. The tab shows how many are running, how many failed, or that
  they're all done.
- With no dev environment yet, it lists what the project can run (compose
  services, package.json and composer scripts, make and just targets,
  Procfile entries, Cargo) and saves what you tick to the file. **Edit Dev
  Environment** changes that choice.
- **Run Task** (Ctrl+Shift+K, ⌘⇧K) runs one task in a split beside the pane.
  **Restart Task** (Ctrl+Alt+R, ⌘⌥R) stops the task in the focused split and
  runs it again.
- **Run Command…** runs a command you type in a split, **Save as Task** keeps
  it, and **Add Task** saves one directly.

A task saved in the file or found in a Procfile is shown to you in full, with
its folder, and confirmed before Run Task first runs it. The file's format is
described at the top of [`main.py`](main.py).

It needs Lumen's [shell integration](https://github.com/lumenshell/lumen/blob/main/docs/shell-integration.md)
to know the pane's folder.

## Install

Open **Plugins** in Lumen's palette, find it under Browse and press `i`, or:

```sh
lumen plugins install sn/project-layout
```

It asks for `panes`, to open tabs and splits, and `input`, to run commands in
them.

## Development

```sh
PYTHONPATH="$(lumen python-path)" python3 -m unittest discover -s tests
lumen plugins check .
```

It used to come with Lumen as the built-in `project-layout`. A `config.toml`
that still lists `project-layout` means this plugin, and the commands you've
already approved carry over.

## License

MIT
