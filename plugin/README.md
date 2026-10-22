# synth-data

Claude / Cursor plugin that fills design-workspace prototypes with synthetic data from a sealed domain catalog. Insights ships ready. Canvas, Parchment, and Mastery are named empty slots.

The plugin never connects to live data. Fill reads only `catalogs/`.

## Install for a teammate (testing)

This repo is a one-plugin marketplace.

**Claude Code**

```
/plugin marketplace add StenSky/synth-data-plugin
/plugin install synth-data@synth-data-plugin
```

Restart the session. A new prototype that needs a table should trigger **fill**.

**Cursor**

Same marketplace add if they use Claude Code plugins in Cursor, or: Cursor Settings → Plugins → add this repo as a marketplace.

They do **not** need GitHub access to the Looker repo. The Insights snapshot is already in `plugin/catalogs/insights/`.
