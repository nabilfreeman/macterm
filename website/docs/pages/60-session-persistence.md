<!-- page:
slug: session-persistence
title: Session persistence
nav: Session persistence
group: Projects & sessions
description: Terminal sessions survive quitting Macterm via a bundled zmx session.
-->

# Session persistence

Terminal sessions survive quitting the app. Each pane's shell runs under a bundled `zmx` session, so quitting Macterm detaches — no confirmation dialog — and relaunching reattaches the current project's panes with their scrollback and running processes intact. Other projects reattach when you select them.

To reconnect everything immediately, enable **Settings → General → Session Persistence → Restore every project on launch**. Macterm starts the restored panes in a staggered background batch, without switching projects. This can open many shells or SSH connections at once, so it is off by default.

Closing a pane, tab, or project is what actually ends its shell (you'll be asked first if something is running). List live sessions from any pane:

```sh
zmx ls
```

> Local sessions don't survive a reboot (the daemon dies with the OS); panes respawn in their last working directory. Sessions in [remote projects](/docs/remote-projects) live on the host, so they *do* survive your Mac rebooting.
