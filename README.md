<h1 align="center">EHTM - Easy HyperText Markup Language</h1>

<p align="center">
  <strong>A standalone compiler that transforms clean, indentation-based markup into standard HTML.</strong>
</p>

<p align="center">
  <a href="#-quick-start"><strong>Quick Start</strong></a> &bull;
  <a href="#-features"><strong>Features</strong></a> &bull;
  <a href="#-installation"><strong>Installation</strong></a> &bull;
  <a href="#-documentation"><strong>Documentation</strong></a> &bull;
  <a href="#-examples"><strong>Examples</strong></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-3.0.0-blue.svg" alt="Version">
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg" alt="Platform">
  <img src="https://img.shields.io/badge/dependencies-none-brightgreen.svg" alt="Dependencies">
  <img src="https://img.shields.io/badge/license-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/badge/build-standalone%20executable-orange.svg" alt="Build">
</p>

---

## What is EHTM?

**EHTM** (Easy HyperText Markup Language) is a lightweight markup language that compiles to standard HTML. It uses **indentation-based syntax** (like Python or Pug) to eliminate the need for closing tags, making your code cleaner and development significantly faster.

### The Problem with HTML
```html
<div id="main" class="container">
    <h1>Hello World</h1>
    <p>This is a paragraph with <strong>bold text</strong>.</p>
    <ul>
        <li>Item 1</li>
        <li>Item 2</li>
    </ul>
</div>
