# My Omarchy themes

Personal [Omarchy](https://omarchy.org/) themes, kept here so a fresh install
can get them back in a minute.

| Theme | Based on | Notes |
|---|---|---|
| `night-islands` | Osaka Jade | Dark floating-pill bar (`#12151d` pills, off-white text), Osaka Jade colors and wallpapers |
| `progressing` | Night Islands | Work in progress: same pill bar; black, Zenitsu ×2, Levi, purple/3D bloom/metallic abstract wallpapers |

## Restore on a new machine

```bash
# Omarchy reads custom themes from this folder
rm -rf ~/.config/omarchy/themes   # only if it is empty / has nothing to keep
git clone https://github.com/abduvaliy-engineer/omarchy-themes.git ~/.config/omarchy/themes
omarchy theme set night-islands
```

Clone it (rather than `omarchy theme install`): theme install expects one
theme per repo and drops `*.lua`, terminal configs, and `vscode.json` from
cloned themes.

## Adding a theme

Each theme is its own folder (`colors.toml`, `backgrounds/`, optional
`shell.toml`, ...). Copy a stock one from `/usr/share/omarchy/themes/`, tweak
it, then commit:

```bash
cp -r /usr/share/omarchy/themes/<stock> ~/.config/omarchy/themes/<new-name>
cd ~/.config/omarchy/themes && git add -A && git commit -m "add <new-name>" && git push
```

## Note: the pill bar

Night Islands' `shell.toml` only sets the bar colors and size. The floating
pill shape comes from a cloned bar plugin (`~/.config/omarchy/plugins/compotuzb.bar`)
plus the widget layout in `~/.config/omarchy/shell.json`, which live outside
this folder.
