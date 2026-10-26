# Linux Mint package proposal — draft

**Subject:** Package proposal: Send to Desktop context-menu action for Nemo and Dolphin

Hello Linux Mint team,

I would like to propose a small utility called **Send to Desktop** for consideration by the Linux Mint community.

The utility adds a right-click action to the Nemo and KDE Dolphin file managers. When selected, it creates a desktop launcher for the selected local file or folder without moving the original item. It supports multiple selections and avoids overwriting an existing shortcut by choosing a numbered filename.

The project is currently a community prototype. The source code, Debian packaging, documentation, and test checklist are available for review. It still needs testing and review before it could be considered for an official repository.

Project source: https://github.com/shortcircuit-design/send-to-desktop

Tested distributions and versions: Not yet tested on clean installations.
Known limitations: remote paths and behavior across different desktop environments still need testing.

Could you please advise whether this utility would be suitable for a community package, and which contribution or packaging process you recommend?

Thank you for your time.

Kind regards,
shortcircuit-design
