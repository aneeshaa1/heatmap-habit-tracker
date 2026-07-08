# Habit Heatmap

A GitHub-contribution-style yearly heatmap for tracking habits, built as a single
self-contained HTML file and designed to be embedded in Notion as a widget.

**Live widget:** https://aneeshaa1.github.io/heatmap-habit-tracker/heatmap.html

## Features

- **GitHub-style grid** — weeks as columns, days as rows, month/day labels, and a color legend.
- **Multiple habits**, each with its own heatmap card.
- **Two tracking modes per habit:**
  - **Graded** — log a numeric value per day; color intensity reflects the value.
  - **Yes / No** — simple done/not-done toggle.
- **Custom color schemes** — choose how many levels, which colors, and which values map
  to which color. One-click auto-gradient.
- **Click to log** — click any day to enter a value (graded) or toggle it (yes/no).
- **Syncs across devices** — data lives in [Supabase](https://supabase.com), not the browser.

## Embedding in Notion

1. Copy the widget URL:
   ```
   https://aneeshaa1.github.io/heatmap-habit-tracker/heatmap.html
   ```
2. In Notion, type `/embed` on any page and choose **Embed**.
3. Paste the URL and click **Embed link**.
4. Drag the handles on the edges of the embed block to resize it. The bar on the
   bottom edge adjusts height — make it tall enough that the heatmaps fit without
   scrolling.

Clicking days, editing settings, and adding habits all work directly inside the embed.

### Embedding a single habit

With several habits, one embed gets tall and scrolly. Instead, give each habit its own
embed using the `habit` URL parameter:

```
https://aneeshaa1.github.io/heatmap-habit-tracker/heatmap.html?habit=Steps
```

This shows only that habit, so each embed is just one heatmap tall. Matching is
case-insensitive (`?habit=steps` finds "Steps"), and habit names with spaces work
as-is — the browser encodes them automatically.

### Embedding multiple habits in one embed

List names separated by commas:

```
https://aneeshaa1.github.io/heatmap-habit-tracker/heatmap.html?habit=Steps,Reading
```

Only the listed habits appear, in their normal order.

### Notes on filtered embeds

- The **+ Add habit** button is hidden in filtered embeds (a new habit wouldn't match
  the filter). Keep one unfiltered embed — or a browser bookmark of the plain URL —
  for adding habits.
- The filter matches by **name**: if you rename a habit, update the URL in its
  Notion embed or it will show an empty widget.
