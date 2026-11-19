# ふりがな · notes

A single-page Japanese notepad that adds furigana (reading aids) above kanji automatically, lets you click any kanji to look it up, and keeps a list of the kanji you've saved.

Everything lives in one `index.html` file: no build step, no server, no account.

## What it does

- **Write or paste Japanese text.** The editor saves your text in the browser as you type, so it's still there when you come back.
- **Turn on furigana.** Use the ふりがな toggle or press <kbd>⌘/Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd>. The text is split into words with [kuromoji.js](https://github.com/takuyaa/kuromoji.js), and each word's reading appears above its kanji as `<ruby>` text. Okurigana (kana endings such as the しい in 新しい) is kept out of the reading, so furigana only sits over the kanji.
- **Click a kanji to look it up.** A card shows:
  - the kanji's English meanings
  - its on'yomi (音) and kun'yomi (訓) readings
  - its JLPT level, school grade and stroke count
  - the dictionary entry for the word you clicked it in, when one is found (for example 勉強 when you click 勉)

  This works in reading mode and also in the editor, where it looks up the kanji next to the cursor. Data comes from [kanjiapi.dev](https://kanjiapi.dev), and results are cached for the session.
- **Save kanji to study later.** Press ☆ Save kanji on the card. Saved kanji are underlined in your text, counted in the ★ button, and listed in a side drawer with their meanings, readings and example word. Click one in the drawer to open its card again, or ✕ to remove it.
- **Light and dark mode** follow your system setting.

## Running it

Open `index.html` in any modern browser, or serve the folder with any static host (GitHub Pages works as-is).

It needs an internet connection: the dictionary for word splitting (about 17 MB, loaded once from jsDelivr and preloaded in the background) and kanji lookups both come from online services. Your notes and saved kanji are stored in your browser's `localStorage` and never leave your device.

## Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| <kbd>⌘/Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>F</kbd> | Turn furigana on or off |
| <kbd>Esc</kbd> | Close the kanji card or the saved-kanji drawer |

## Credits

- Word splitting and readings: [kuromoji.js](https://github.com/takuyaa/kuromoji.js) (IPADIC dictionary)
- Kanji and word data: [kanjiapi.dev](https://kanjiapi.dev), built on KANJIDIC and JMdict from the [EDRDG](https://www.edrdg.org/)
- Font: [Noto Sans JP](https://fonts.google.com/noto/specimen/Noto+Sans+JP)
