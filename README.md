# MDViewer

A fast, native macOS app for reading and editing the files that live in a project folder. It was built for working alongside AI coding agents: open a folder, and everything the agent writes shows up rendered, and updates live when the file changes on disk.

Documents stay on your machine. The app works fully offline; the only thing it ever contacts is GitHub, once a day, to see whether a newer version exists (you can turn that off).

## What it does

Open a folder and browse it in a file tree that shows git status. Each file opens in a tab, and the right view is picked from its type:

- **Markdown**: GitHub-style rendering with tables, task lists and footnotes, syntax-highlighted code, Mermaid diagrams, KaTeX math and an outline panel. Switch between Preview, Edit and a side-by-side Split. Export to HTML or PDF.
- **draw.io** (`.drawio`, `.dio`): diagrams drawn as draw.io draws them, as a tab or embedded in markdown with `![](diagram.drawio)`. Zoom, pan, pages and layers.
- **JSON and XML**: a tree you can browse, with collapsible nodes, a filter that finds nodes by key, value, tag or attribute, and the path of the selected node. It copes with comments and trailing commas, and shows parse errors with a jump to the line.
- **CSV**: a sortable, filterable table. Long values wrap inside their cells, and you can drag the column widths.
- **HTML**: shown as the page it is, with its own stylesheets, images and scripts from the folder. It runs in a sandbox with no network access. Links to other files open in a tab; web links open in your browser.
- **PDF, Word (`.docx`), Excel (`.xlsx`) and RTF**: native previews you can zoom.
- **Code and everything else**: syntax-highlighted, with images shown as images.

On top of that:

- **Find in the document** with ⌘F in any kind of tab, and **find in files** with ⇧⌘F.
- **Select and copy** text in any tab, including Word, Excel and PDF pages.
- **Live reload**: a file that changes on disk (say, because an agent rewrote it) refreshes in place.
- **Quick open** with ⌘P to jump to any file in the folder.
- Light and dark mode, and an `mdv` command to open a folder from the terminal.

## Install

Download `MDViewer.dmg` from the [latest release](https://github.com/redemiguel/mdviewer-releases/releases/latest) and drag the app to Applications. It needs macOS 15 or later on a Mac with Apple silicon.

The app is signed ad hoc rather than with a paid developer certificate. If macOS blocks the first launch, open System Settings → Privacy & Security and click **Open Anyway**, or run:

```sh
xattr -dr com.apple.quarantine /Applications/MDViewer.app
```

## Updates

Choose **MDViewer ▸ Check for Updates…** to see whether a newer version exists. It shows what changed and, if you agree, downloads the update, checks it against the checksum GitHub publishes for it, replaces the app and relaunches it. The app also looks once a day by itself; turn that off with **MDViewer ▸ Check for Updates Automatically**.

New versions are published on this page. Versions up to 0.4.11 cannot update themselves, so install 0.4.12 or later by hand once.

Copyright © 2026 Renato de Miguel.
