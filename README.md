# Send to Desktop

A small Linux file-manager integration that adds **Send to Desktop** to KDE Dolphin and Cinnamon's Nemo. It creates a desktop launcher for the selected local file or folder; it does not move the original item.

## Status

**Community prototype — not officially accepted or reviewed by Linux Mint, Ubuntu, or Debian.** It has not yet been tested on a clean range of supported desktop environments. Please test it before relying on it.

## Features

- Context-menu action for KDE Dolphin (KIO service menu).
- Context-menu action for Nemo (Nemo action).
- Supports selecting multiple files and folders.
- Copies existing `.desktop` launchers to the desktop and marks them executable.
- Creates launchers for other selected files and folders that open the target using `xdg-open`.
- Avoids overwriting an existing shortcut by adding a numbered suffix when necessary.

## Requirements

- Python 3
- `xdg-user-dir` (normally provided by `xdg-user-dirs`)
- `xdg-open`
- `gio` (normally provided by GLib/GIO utilities)
- Dolphin or Nemo, depending on your file manager

## Install a locally built Debian package

Once a package has been built:

```sh
sudo apt install ./send-to-desktop_1.1.1_all.deb
```

Restart the file manager if the context-menu action does not appear immediately.

## Build the Debian package

On a Debian/Ubuntu/Linux Mint build system with `dpkg-buildpackage` and `debhelper` installed:

```sh
sudo apt install build-essential debhelper dpkg-dev
dpkg-buildpackage -us -uc -b
```

Run the build command from the source tree. The resulting `.deb` is written to the parent directory.

## Manual test checklist

- [ ] Install on a clean Linux Mint system with Nemo.
- [ ] Install on a KDE Plasma system with Dolphin.
- [ ] Create shortcuts for files and folders whose names contain spaces.
- [ ] Select multiple items at once.
- [ ] Repeat the action for an item with an existing shortcut name and confirm no file is overwritten.
- [ ] Copy an existing `.desktop` launcher and confirm it remains executable.
- [ ] Test a non-default Desktop directory configured through `xdg-user-dir`.
- [ ] Test paths with non-ASCII characters and punctuation.
- [ ] Check behavior when `gio` is unavailable and when a selected path no longer exists.

## Security and limitations

This is a convenience tool, not a sandbox. Existing `.desktop` launchers can execute commands, so only copy launchers you trust. This prototype is intended for local filesystem paths passed by the file manager; remote URLs and unusual file-manager URI handling need further testing. Desktop-environment behavior for the GIO trusted metadata flag varies.

## Contributing

Bug reports and patches are welcome. Include your distribution/version, desktop environment, file manager, reproduction steps, and relevant terminal output.

## License

MIT. See [LICENSE](LICENSE).
