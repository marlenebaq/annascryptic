# Cryptic Puzzle

A single-file web app for sharing a cryptic crossword clue with a friend.

---

## How to update the puzzle

Open `index.html` in any text editor (TextEdit, VS Code, etc.) and find this block near the top of the `<script>` tag:

```js
const PUZZLE = {
  clue: "Sold latticed pie past its expiration date? (7)",
  answer: "EXPIRED",          // UPPERCASE, no spaces
  date: "22 September, 2026",
  author: "By Member: Drew B",
  par: 3,                     // expected attempts for a good solver
  hints: [
    { label: "Wordplay", text: "Anagram of something..." },
    { label: "Definition", text: "The definition is the last word" },
  ],
  winMessage: "Well done! Cryptic clues are tricky.",
};
```

Change whatever you like and save the file. That's it — no build step.

**Multi-word answers:** put a space in the answer string, e.g. `"TWO WORDS"`. The boxes will render with a gap between the words.

**No hints:** set `hints: []` and the Hints button disappears automatically.

> **Note on spoilers:** the answer lives in plain JS in the file, so a determined friend could find it in the browser's dev tools. For casual use this is fine.

---

## Serving it locally (to share on your network)

You need Python 3, which comes pre-installed on every Mac.

1. Open Terminal.
2. `cd` into this folder:
   ```
   cd ~/Documents/cryptic-puzzle
   ```
3. Start the server:
   ```
   python3 -m http.server 8080
   ```
4. Your friend needs to be on the **same Wi-Fi network**. Find your Mac's local IP:
   ```
   ipconfig getifaddr en0
   ```
   Share this URL with them: `http://<your-ip>:8080`
   
   Example: `http://192.168.1.42:8080`

5. Press `Ctrl+C` in Terminal when you're done.

---

## Serving it from the same machine (just for yourself)

```
python3 -m http.server 8080
```

Then open `http://localhost:8080` in your browser.

---

## Need to share it over the internet?

The above only works on a local network. To share with someone outside your network, ask the engineering team in **#claude on Slack** for the approved internal hosting option before setting anything up.
# annascryptic.github.io
