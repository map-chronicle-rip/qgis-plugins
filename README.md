# Chronicle QGIS plugins

The install channel for Chronicle's two QGIS plugins. Nothing is developed here —
this repository holds an index and the built ZIPs, and the source lives with the
rest of Chronicle.

These are **tester builds**. They are marked experimental on purpose, and QGIS
hides experimental plugins until you say otherwise.

## Adding it to QGIS, once

1. **Plugins ▸ Manage and Install Plugins… ▸ Settings**
2. Tick **Show also experimental plugins**
3. Under **Plugin Repositories**, press **Add…** and paste:

   ```
   https://map-chronicle-rip.github.io/qgis-plugins/plugins.xml
   ```

4. Go to **All** or **Not installed**, and install **Chronicle Workbench**

From then on QGIS offers upgrades the way it does for any other plugin — the
**Upgradeable** tab, and **Upgrade All**.

## The two plugins

| Plugin | What it is for |
|---|---|
| **Chronicle Workbench** | The mapping workflow: sync, upload, convert, preview, edit and deploy cemetery data. Stands on its own. |
| **Chronicle MySQL** | A MySQL entry in the Browser panel, for reading a cemetery's layers. Read-only, and optional. |

The Workbench no longer needs the MySQL plugin: it carries its own driver, its
own SSH tunnel and its own saved connections, under **Settings ▸ Connections**.
Install the MySQL plugin only if you want to browse a database as layers.

## Versions

`0.1.0.N` — the release is still `0.1.0`, and `N` counts the changes that went
into that plugin. The build number is part of the version rather than a suffix
after a hyphen, because QGIS compares a hyphen suffix as text: it would read
`0.1.0-build.10` as older than `0.1.0-build.9` and stop offering upgrades.

## Something went wrong

Report it with **Report a problem…** in the plugin's own menu. It gathers the
recorded failures, their codes and the versions involved into one file, with
anything that looks like a sign-in taken out first.
