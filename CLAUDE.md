# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file browser game: `tictactoe.html`. No build tools, no dependencies, no server — open directly in a browser.

## Architecture

Everything lives in `tictactoe.html` as a single self-contained file with three sections:

- **CSS** (inline `<style>`) — dark theme using a 3-color palette: red (`#e94560`), blue-grey (`#a8dadc`), dark navy background
- **HTML** — static 3×3 grid of `.cell` divs with `data-i` attributes (0–8), a score display, and a status line
- **JavaScript** (inline `<script>`) — all game logic; no frameworks

### Game Logic

- `board` — flat 9-element array of `''`, `'X'`, or `'O'`
- `WINS` — hardcoded array of the 8 winning index triples
- `checkWinner()` — iterates `WINS`, returns `{ winner, line }` or `{ winner: 'D' }` for draw, or `null`
- `scores` — object `{ X, O, D }` persisted in memory (resets on page reload)
- Cell clicks update `board`, add CSS classes (`x`/`o`/`taken`/`win`), and call `checkWinner()`

## Git & GitHub

- Repo: https://github.com/Steve-Premier/claudecode-test
- Branch: `main`

**Commit and push frequently.** After every meaningful unit of work — adding a feature, fixing a bug, updating a file — stage the relevant files, write a clean descriptive commit message, and push to GitHub. Never leave completed work uncommitted. This ensures we can always revert to any previous state and nothing is ever lost.
