# 4️⃣ Information-Dense Design Philosophy

Information density in WezTerm usually means:

### Status bar shows:

* workspace
* hostname
* cwd
* git branch
* time
* zoom state
* battery

### Tabs show:

* index
* cwd basename
* zoom flag
* pane count

### Panes are:

* split fast
* navigated fast
* zoomable

### Keyboard is primary

Mouse is secondary.

---

## ✅ Example information payload

Instead of:

```
tab1
```

You get:

```
[1] api-server ~/proj/main  feature/login Z
```

And status bar:

```
WS:dev | host:macbook | ~/proj |  main | 14:22
```

That’s information density.
