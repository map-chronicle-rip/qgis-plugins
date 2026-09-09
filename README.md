# Chronicle Workbench — QGIS plugin

The install channel for **Chronicle Workbench**, the QGIS plugin Chronicle's
mapping team uses. Nothing is developed here: this repository holds an index and
the built ZIPs, and the source lives with the rest of Chronicle.

**This is an internal tool, not a general-purpose QGIS plugin.** It reads and
writes Chronicle's own databases and is of no use without them. It is not on
[plugins.qgis.org](https://plugins.qgis.org) and is not offered to QGIS users at
large — the address below is for the team.

The builds here are **tester builds**. They are marked experimental on purpose,
and QGIS hides experimental plugins until you say otherwise.

## Adding it to QGIS, once

1. **Plugins ▸ Manage and Install Plugins… ▸ Settings**
2. Turn on the option to show experimental plugins. These builds are marked
   experimental, and QGIS hides them until you do.
3. Under **Plugin Repositories**, press **Add…**. The dialog asks for two
   things, and **OK stays greyed out until both are filled in**:

   | Field | What to put |
   |---|---|
   | **Name** | `Chronicle` |
   | **URL** | `https://map-chronicle-rip.github.io/qgis-plugins/plugins.xml` |

   The URL box starts out holding `http://`. Select what is there and replace
   it — pasting after it gives you `http://https://…`, and the repository then
   fails to load.

4. Press **OK**. The repository should say *connected*.
5. Go to **All** or **Not installed**, and install **Chronicle Workbench**

From then on QGIS offers upgrades the way it does for any other plugin — the
**Upgradeable** tab, and **Upgrade All**.

## Setting it up

The Workbench stands on its own: the MySQL driver, the SSH tunnel and the saved
connections are all inside it. Add the databases it should reach under
**Settings ▸ Connections**.

A machine upgrading from a version that borrowed those connections from the
Chronicle MySQL plugin keeps what was saved there — they are copied across the
first time this version starts, passwords included, because QGIS's
authentication database belongs to the application rather than to a plugin.

## What is not here

**Chronicle MySQL**, the sibling plugin that adds a MySQL entry to the Browser
panel, is not published to this repository. The Workbench does not need it, so
it is not something a mapper has to install. Anyone who wants its read-only
layers builds a ZIP from the source and installs that.

## Versions

`0.1.0.N` — the release is still `0.1.0`, and `N` counts the changes that went
into the plugin. The build number is part of the version rather than a suffix
after a hyphen, because QGIS compares a hyphen suffix as text: it would read
`0.1.0-build.10` as older than `0.1.0-build.9` and stop offering upgrades.

## Something went wrong

Use **Report a problem…** in the plugin's own menu. It gathers the recorded
failures, their codes and the versions involved into one file, with anything
that looks like a sign-in taken out first. Send that to the team.
