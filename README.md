# 🧮 3D Scientific Calculator Pro

A visually stunning, feature-rich scientific and coding calculator built with pure HTML, CSS, and JavaScript. Features a real 3D perspective design, multi-language voice input, full scientific functions, bitwise/logic operators, and calculation history — all in a single self-contained file.

---

## ✨ Features

### 🎨 3D Visual Design
- Realistic 3D calculator body using CSS `perspective` and `transform-style: preserve-3d`
- Dynamic mouse-tracking tilt effect on desktop
- Depth-shaded button categories with hover lift and press animations
- Glowing display with animated cursor and result pop effects

### 🔬 Scientific Mode
- Standard arithmetic: `+`, `−`, `×`, `÷`, `%`
- Trigonometry: `sin`, `cos`, `tan`
- Logarithms: `log` (base-10), `ln` (natural)
- Square root `√`, power `x^y`, factorial `n!`
- Constants: `π`
- Parentheses grouping
- Decimal and negative number support

### 💻 Coding Mode
- Bitwise operators: `AND (&)`, `OR (|)`, `XOR`, `NOT (~)`
- Bit shift: `<<`, `>>`
- Integer power `**`, floor division `//`
- Logical operators: `&&`, `||`
- Boolean literals: `true`, `false`
- Comparison operators: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Boolean result display with color-coded TRUE ✓ / FALSE ✗ indicator

### 🧠 Memory System
- `M+` — Add current value to memory
- `M−` — Subtract current value from memory
- `MR` — Recall memory value into input
- `MC` — Clear memory

### ⌨️ Cursor Navigation
- Left / Right arrow keys to move within the expression
- Up / Down to jump between operators
- Home (⏮) / End (⏭) to jump to start or end
- Forward delete (DEL) and backspace (⌫)
- Full keyboard support (see Keyboard Shortcuts below)

### 🎤 Voice Input (Multi-Language)
Supports natural spoken math in 4 languages:

| Language | Code | Example |
|----------|------|---------|
| తెలుగు (Telugu) | `te-IN` | "పది కి ఐదు కలిపితే" → `10+5` |
| हिंदी (Hindi) | `hi-IN` | "बीस में से पांच निकालो" → `20-5` |
| اردو (Urdu) | `ur-PK` | "دس جمع پانچ" → `10+5` |
| English | `en-US` | "twenty plus five" → `20+5` |

- Converts spoken number words to digits automatically
- Strips filler words and grammar to extract the math expression
- Shows live preview while speaking
- Auto-stops after detecting a complete expression
- Click 🌐 to cycle languages; click 🎤 to start/stop

### 📜 Calculation History
- Stores up to 50 recent calculations
- Click 📜 to show/hide the history panel
- Tap any history entry to reload its expression
- Timestamped entries
- Clear all history with one button

### ⚡ Live Calculation
Results update instantly as you type — no need to press `=` to see a preview.

---

## 🚀 Getting Started

No installation required. Just open the file in any modern browser.

```bash
# Option 1: Open directly
open index.html

# Option 2: Serve locally
npx serve .
# or
python -m http.server 8080
```

Then visit `http://localhost:8080` in your browser.

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `0–9`, `.` | Input digits / decimal |
| `+`, `-`, `*`, `/` | Arithmetic operators |
| `%`, `^`, `&`, `\|` | Modulo, power, bitwise AND/OR |
| `<`, `>` | Comparison / bit-shift |
| `(`, `)` | Parentheses |
| `Enter` or `=` | Calculate |
| `Backspace` | Delete character before cursor |
| `Delete` | Delete character after cursor |
| `Escape` | Clear all (AC) |
| `Arrow Left / Right` | Move cursor |
| `Arrow Up / Down` | Jump to previous / next operator |
| `Home` / `End` | Jump to start / end of expression |
| `s` | Insert `sin(` |
| `c` | Insert `cos(` |
| `t` | Insert `tan(` |
| `l` | Insert `log(` |
| `n` | Insert `ln(` |
| `r` | Insert `√(` |
| `!` | Insert `fact(` |
| `p` | Insert `π` |

---

## 🗂️ Project Structure

```
index.html          ← Single self-contained file (HTML + CSS + JS)
README.md           ← This file
```

All styles, logic, and markup live in `index.html`. There are no external dependencies beyond Tailwind CSS (loaded via CDN).

---

## 🌐 Browser Compatibility

| Browser | Voice Input | Calculator |
|---------|------------|------------|
| Chrome (desktop/Android) | ✅ Full support | ✅ |
| Edge | ✅ Full support | ✅ |
| Safari (iOS/macOS) | ✅ Full support | ✅ |
| Firefox | ❌ No voice | ✅ |

Voice recognition uses the Web Speech API (`webkitSpeechRecognition`). All other features work in every modern browser.

---

## 🔧 Dependencies

| Dependency | Source | Purpose |
|------------|--------|---------|
| Tailwind CSS v4 | CDN (`cdn.jsdelivr.net`) | Utility classes for layout |
| Web Speech API | Browser built-in | Voice recognition |

No npm packages, no build step, no framework.

---

## 🔒 Privacy

- Voice processing is handled entirely by your browser's built-in Speech Recognition API
- No audio data is sent to any external server by this application
- Calculation history is stored only in memory (lost on page refresh)

---

## 📐 Architecture Notes

### Expression Evaluation
Expressions are evaluated using JavaScript's `Function` constructor (sandboxed, no `eval`). The input string is preprocessed to convert display symbols (`×`, `÷`, `π`, `√`) into valid JS math before execution.

### Voice Processing Pipeline
```
Raw speech → Strip "equals" commands
           → Convert phrases (e.g. "take away" → -)
           → Convert number words → digits
           → Strip filler/grammar words
           → Extract valid math characters only
           → Live preview → Auto-calculate
```

### Boolean Results
When an expression contains comparison or logical operators, the result is evaluated as a boolean and displayed with colour-coded `TRUE ✓` / `FALSE ✗` styling.

---

## 🤝 Contributing

1. Fork the repository
2. Make your changes in `index.html`
3. Test across Chrome, Edge, and Safari
4. Submit a pull request with a description of your changes

---

## 📄 License

This project is open source. Feel free to use, modify, and distribute.

---

## 🙏 Credits

Built with ❤️ using vanilla HTML, CSS, and JavaScript. Voice recognition powered by the Web Speech API.
