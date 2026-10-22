# synth-data

Claude / Cursor plugin that fills design-workspace prototypes with synthetic data. Insights ships ready. Canvas, Parchment, and Mastery are empty slots.

The plugin never connects to live data. Fill reads only `plugin/catalogs/`.

This repo is the plugin only. It does not include prototypes.

## Install for a teammate

They need access to this private repo.

**Claude Code**

```
/plugin marketplace add StenSky/synth-data-plugin
/plugin install synth-data@synth-data-plugin
```

Restart the session. A new prototype that needs a table should trigger **fill**.

**Cursor**

Same marketplace add if they use Claude Code plugins in Cursor, or: Cursor Settings → Plugins → add this repo as a marketplace.

They do **not** need access to the Looker GitHub repo. The Insights snapshot is already in `plugin/catalogs/insights/`.
