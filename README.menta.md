# pkg-rojo (Menta Linux)

Debian packaging of rojo (MATE color management / Night Light daemon),
upstream https://github.com/KeremSoke/rojo. Upstream has no releases, so the
version pins a commit: `0.1.0+git20261022.30cc46f-1menta1` = commit `30cc46f`.
CI clones that exact commit and builds an orig tarball with `git archive`.

- Daemon installed as `/usr/bin/rojo` (`-Dlibexecdir=bin`; the D-Bus service and
  autostart entry follow, both `Exec=/usr/bin/rojo`).
- Built with X11 (RandR) and Wayland (wlr-gamma-control) backends, GeoClue config
  and MATE autostart entry.

To package a newer commit: update the changelog version (`dch -v`) with the new
date and short hash.

CI builds on push to `master`; tag `menta/<version>` publishes the .debs as a release.
