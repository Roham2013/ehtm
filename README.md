<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EHTM - Easy HyperText Markup Language</title>
    <style>
        /* ============================================
           GitHub-like README Styles
           ============================================ */
        :root {
            --bg: #ffffff;
            --text: #1f2328;
            --text-secondary: #656d76;
            --border: #d0d7de;
            --link: #0969da;
            --code-bg: #f6f8fa;
            --code-text: #1f2328;
            --blockquote-bg: #f6f8fa;
            --blockquote-border: #d0d7de;
            --table-stripe: #f6f8fa;
            --badge-bg: #f3f4f6;
            --badge-text: #4b5563;
            --heading-border: #d0d7de;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            background: #ffffff;
            color: var(--text);
            line-height: 1.6;
            font-size: 16px;
            max-width: 900px;
            margin: 0 auto;
            padding: 32px 24px 80px;
        }

        /* ============================================
           Headings
           ============================================ */
        h1, h2, h3, h4, h5, h6 {
            margin-top: 24px;
            margin-bottom: 16px;
            font-weight: 600;
            line-height: 1.25;
            color: var(--text);
        }

        h1 {
            font-size: 2em;
            padding-bottom: 0.3em;
            border-bottom: 1px solid var(--heading-border);
        }

        h2 {
            font-size: 1.5em;
            padding-bottom: 0.3em;
            border-bottom: 1px solid var(--heading-border);
        }

        h3 {
            font-size: 1.25em;
        }

        h4 {
            font-size: 1em;
        }

        /* ============================================
           Paragraphs & Links
           ============================================ */
        p {
            margin-bottom: 16px;
        }

        a {
            color: var(--link);
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        /* ============================================
           Horizontal Rules
           ============================================ */
        hr {
            border: none;
            border-top: 1px solid var(--border);
            margin: 24px 0;
        }

        /* ============================================
           Code
           ============================================ */
        code {
            background: var(--code-bg);
            padding: 0.2em 0.4em;
            border-radius: 6px;
            font-family: 'SFMono-Regular', 'Consolas', 'Liberation Mono', 'Menlo', 'Courier', monospace;
            font-size: 85%;
            color: var(--code-text);
        }

        pre {
            background: var(--code-bg);
            padding: 16px;
            border-radius: 6px;
            overflow-x: auto;
            margin-bottom: 16px;
            line-height: 1.45;
        }

        pre code {
            background: none;
            padding: 0;
            font-size: 85%;
            border-radius: 0;
        }

        /* ============================================
           Blockquotes
           ============================================ */
        blockquote {
            padding: 0 1em;
            color: var(--text-secondary);
            border-left: 0.25em solid var(--blockquote-border);
            margin: 0 0 16px;
            background: var(--blockquote-bg);
            border-radius: 0 6px 6px 0;
            padding: 12px 16px;
        }

        blockquote p:last-child {
            margin-bottom: 0;
        }

        /* ============================================
           Tables
           ============================================ */
        table {
            border-collapse: collapse;
            width: 100%;
            margin-bottom: 16px;
            display: block;
            overflow-x: auto;
        }

        table th, table td {
            padding: 6px 13px;
            border: 1px solid var(--border);
            text-align: left;
        }

        table th {
            font-weight: 600;
            background: var(--table-stripe);
        }

        table tr:nth-child(even) td {
            background: var(--table-stripe);
        }

        /* ============================================
           Lists
           ============================================ */
        ul, ol {
            padding-left: 2em;
            margin-bottom: 16px;
        }

        li {
            margin-bottom: 4px;
        }

        li > ul, li > ol {
            margin-top: 4px;
            margin-bottom: 0;
        }

        /* ============================================
           Images
           ============================================ */
        img {
            max-width: 100%;
            height: auto;
        }

        /* ============================================
           Badges
           ============================================ */
        .badges {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 24px;
        }

        .badges img {
            display: inline-block;
        }

        /* ============================================
           Center align utility
           ============================================ */
        .text-center {
            text-align: center;
        }

        /* ============================================
           Navigation links
           ============================================ */
        .nav-links {
            text-align: center;
            margin-bottom: 32px;
            font-size: 15px;
        }

        .nav-links a {
            margin: 0 8px;
            font-weight: 500;
        }

        .nav-links .separator {
            color: var(--text-secondary);
            margin: 0 4px;
        }

        /* ============================================
           Feature comparison checkmarks
           ============================================ */
        .check {
            color: #1a7f37;
            font-weight: bold;
        }

        .cross {
            color: #cf222e;
            font-weight: bold;
        }

        /* ============================================
           Syntax highlighting
           ============================================ */
        .hljs-keyword { color: #cf222e; }
        .hljs-string { color: #0a3069; }
        .hljs-comment { color: #6e7781; font-style: italic; }
        .hljs-tag { color: #116329; }
        .hljs-attr { color: #8250df; }
        .hljs-variable { color: #953800; }
        .hljs-meta { color: #0969da; }

        /* ============================================
           Responsive
           ============================================ */
        @media (max-width: 768px) {
            body {
                padding: 16px 16px 60px;
                font-size: 15px;
            }
            h1 { font-size: 1.6em; }
            h2 { font-size: 1.3em; }
            h3 { font-size: 1.1em; }
        }

        /* ============================================
           Print
           ============================================ */
        @media print {
            body {
                max-width: 100%;
                padding: 0;
            }
            pre, blockquote {
                break-inside: avoid;
            }
        }
    </style>
</head>
<body>

    <p class="text-center">
        <img src="https://raw.githubusercontent.com/yourusername/ehtm/main/assets/ehtm-logo.svg" alt="EHTM Logo" width="200">
    </p>

    <h1 class="text-center">EHTM - Easy HyperText Markup Language</h1>

    <p class="text-center">
        <strong>A standalone compiler that transforms clean, indentation-based markup into standard HTML.</strong>
    </p>

    <p class="nav-links">
        <a href="#-quick-start"><strong>Quick Start</strong></a>
        <span class="separator">&bull;</span>
        <a href="#-features"><strong>Features</strong></a>
        <span class="separator">&bull;</span>
        <a href="#-installation"><strong>Installation</strong></a>
        <span class="separator">&bull;</span>
        <a href="#-documentation"><strong>Documentation</strong></a>
        <span class="separator">&bull;</span>
        <a href="#-examples"><strong>Examples</strong></a>
    </p>

    <p class="text-center badges">
        <img src="https://img.shields.io/badge/version-3.0.0-blue.svg" alt="Version">
        <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg" alt="Platform">
        <img src="https://img.shields.io/badge/dependencies-none-brightgreen.svg" alt="Dependencies">
        <img src="https://img.shields.io/badge/license-MIT-yellow.svg" alt="License">
        <img src="https://img.shields.io/badge/build-standalone%20executable-orange.svg" alt="Build">
    </p>

    <hr>

    <h2>What is EHTM?</h2>

    <p>
        <strong>EHTM</strong> (Easy HyperText Markup Language) is a lightweight markup language that compiles to standard HTML. It uses <strong>indentation-based syntax</strong> (like Python or Pug) to eliminate the need for closing tags, making your code cleaner and development significantly faster.
    </p>

    <h3>The Problem with HTML</h3>

    <pre><code><span class="hljs-tag">&lt;div</span> <span class="hljs-attr">id=</span><span class="hljs-string">"main"</span> <span class="hljs-attr">class=</span><span class="hljs-string">"container"</span><span class="hljs-tag">&gt;</span>
    <span class="hljs-tag">&lt;h1&gt;</span>Hello World<span class="hljs-tag">&lt;/h1&gt;</span>
    <span class="hljs-tag">&lt;p&gt;</span>This is a paragraph with <span class="hljs-tag">&lt;strong&gt;</span>bold text<span class="hljs-tag">&lt;/strong&gt;</span>.<span class="hljs-tag">&lt;/p&gt;</span>
    <span class="hljs-tag">&lt;ul&gt;</span>
        <span class="hljs-tag">&lt;li&gt;</span>Item 1<span class="hljs-tag">&lt;/li&gt;</span>
        <span class="hljs-tag">&lt;li&gt;</span>Item 2<span class="hljs-tag">&lt;/li&gt;</span>
    <span class="hljs-tag">&lt;/ul&gt;</span>
<span class="hljs-tag">&lt;/div&gt;</span></code></pre>

    <h3>The EHTM Solution</h3>

    <pre><code><span class="hljs-tag">div</span><span class="hljs-attr">#main</span>.<span class="hljs-attr">container</span>
    <span class="hljs-tag">h1</span> <span class="hljs-string">"Hello World"</span>
    <span class="hljs-tag">p</span> <span class="hljs-string">"This is a paragraph with &lt;strong&gt;bold text&lt;/strong&gt;."</span>
    <span class="hljs-tag">ul</span>
        <span class="hljs-tag">li</span> <span class="hljs-string">"Item 1"</span>
        <span class="hljs-tag">li</span> <span class="hljs-string">"Item 2"</span></code></pre>

    <p><strong>That's up to 50% less typing.</strong> No closing tags. Clean structure. Pure HTML output.</p>

    <hr>

    <h2 id="-features">Features</h2>

    <ul>
        <li><strong>Standalone Executable</strong> - Single <code>.exe</code> file. No Python, no Node.js, no dependencies.</li>
        <li><strong>Indentation-Based Syntax</strong> - Structure your document with spaces, not closing tags.</li>
        <li><strong>CSS-Style Selectors</strong> - Use <code>#id</code> and <code>.class</code> directly on elements.</li>
        <li><strong>Variables</strong> - Define values once with <code>set</code> and reuse with <code>${variable}</code>.</li>
        <li><strong>Component System</strong> - Include other files with <code>include "file.ehtm"</code>.</li>
        <li><strong>Three Output Modes</strong> - Pretty-printed, minified, or preserved formatting.</li>
        <li><strong>Watch Mode</strong> - Auto-recompile on file changes during development.</li>
        <li><strong>Cross-Platform</strong> - Runs on Windows, macOS, and Linux.</li>
        <li><strong>Zero Configuration</strong> - Download and run. No setup required.</li>
        <li><strong>English Error Messages</strong> - Clear, descriptive errors with line and column numbers.</li>
    </ul>

    <hr>

    <h2 id="-quick-start">Quick Start</h2>

    <h3>1. Download</h3>

    <p>Download the latest <code>ehtm.exe</code> from the <a href="https://github.com/yourusername/ehtm/releases">Releases page</a>.</p>

    <h3>2. Create Your First File</h3>

    <p>Create <code>hello.ehtm</code>:</p>

    <pre><code><span class="hljs-tag">html</span> <span class="hljs-attr">lang=</span><span class="hljs-string">"en"</span>
    <span class="hljs-tag">head</span>
        <span class="hljs-tag">meta</span> <span class="hljs-attr">charset=</span><span class="hljs-string">"UTF-8"</span>
        <span class="hljs-tag">title</span> <span class="hljs-string">"My First EHTM Page"</span>
    <span class="hljs-tag">body</span>
        <span class="hljs-tag">h1</span> <span class="hljs-string">"Hello, World!"</span>
        <span class="hljs-tag">p</span> <span class="hljs-string">"This was built with EHTM."</span></code></pre>

    <h3>3. Compile</h3>

    <p>Open a terminal and run:</p>

    <pre><code><span class="hljs-meta">ehtm</span> hello.ehtm</code></pre>

    <p>This generates <code>hello.html</code> -- open it in any browser.</p>

    <h3>4. Production Build</h3>

    <pre><code><span class="hljs-meta">ehtm</span> hello.ehtm -f minified -o dist/index.html</code></pre>

    <hr>

    <h2 id="-installation">Installation</h2>

    <h3>Option 1: Download Executable (Recommended)</h3>

    <ol>
        <li>Go to <a href="https://github.com/yourusername/ehtm/releases">Releases</a></li>
        <li>Download <code>ehtm.exe</code> (Windows), <code>ehtm</code> (macOS), or <code>ehtm</code> (Linux)</li>
        <li>Place it in your project folder or add it to your system PATH</li>
    </ol>

    <h3>Option 2: Add to PATH (Windows)</h3>

    <pre><code><span class="hljs-comment"># Move ehtm.exe to a permanent location</span>
<span class="hljs-meta">mkdir</span> C:\tools
<span class="hljs-meta">move</span> ehtm.exe C:\tools\

<span class="hljs-comment"># Add to PATH (run as Administrator)</span>
[Environment]::SetEnvironmentVariable(<span class="hljs-string">"Path"</span>, $env:Path + <span class="hljs-string">";C:\tools"</span>, <span class="hljs-string">"Machine"</span>)</code></pre>

    <h3>Option 3: Build from Source</h3>

    <pre><code><span class="hljs-meta">git clone</span> https://github.com/yourusername/ehtm.git
<span class="hljs-meta">cd</span> ehtm

<span class="hljs-comment"># Install PyInstaller</span>
<span class="hljs-meta">pip install</span> pyinstaller

<span class="hljs-comment"># Build executable</span>
<span class="hljs-meta">pyinstaller</span> --onefile --name ehtm ehtm3.py

<span class="hljs-comment"># Output: dist/ehtm.exe</span></code></pre>

    <h3>Verify Installation</h3>

    <pre><code><span class="hljs-meta">ehtm</span> --version
<span class="hljs-comment"># Output: EHTM Compiler v3.0.0</span></code></pre>

    <hr>

    <h2>Syntax Overview</h2>

    <h3>Basic Elements</h3>

    <pre><code><span class="hljs-tag">tagname</span>                           <span class="hljs-comment"># Basic element</span>
<span class="hljs-tag">tagname</span> <span class="hljs-string">"text content"</span>            <span class="hljs-comment"># Element with text</span>
<span class="hljs-tag">tagname</span><span class="hljs-attr">#idname</span>                    <span class="hljs-comment"># Element with ID</span>
<span class="hljs-tag">tagname</span>.<span class="hljs-attr">classname</span>                 <span class="hljs-comment"># Element with class</span>
<span class="hljs-tag">tagname</span><span class="hljs-attr">#id</span>.<span class="hljs-attr">class1</span>.<span class="hljs-attr">class2</span>          <span class="hljs-comment"># Combined</span></code></pre>

    <h3>Nesting (Indentation)</h3>

    <pre><code><span class="hljs-tag">body</span>
    <span class="hljs-tag">header</span>
        <span class="hljs-tag">nav</span>
            <span class="hljs-tag">a</span> <span class="hljs-attr">href=</span><span class="hljs-string">"/"</span> <span class="hljs-string">"Home"</span>
            <span class="hljs-tag">a</span> <span class="hljs-attr">href=</span><span class="hljs-string">"/about"</span> <span class="hljs-string">"About"</span>
    <span class="hljs-tag">main</span>
        <span class="hljs-tag">h1</span> <span class="hljs-string">"Welcome"</span>
        <span class="hljs-tag">p</span> <span class="hljs-string">"Content here"</span>
    <span class="hljs-tag">footer</span>
        <span class="hljs-tag">p</span> <span class="hljs-string">"Copyright 2024"</span></code></pre>

    <h3>Attributes</h3>

    <p><strong>Space-separated:</strong></p>

    <pre><code><span class="hljs-tag">a</span> <span class="hljs-attr">href=</span><span class="hljs-string">"https://example.com"</span> <span class="hljs-attr">target=</span><span class="hljs-string">"_blank"</span> <span class="hljs-string">"Visit Site"</span>
<span class="hljs-tag">input</span> <span class="hljs-attr">type=</span><span class="hljs-string">"email"</span> <span class="hljs-attr">placeholder=</span><span class="hljs-string">"Your email"</span> <span class="hljs-attr">required</span></code></pre>

    <p><strong>Parenthesized (comma-separated):</strong></p>

    <pre><code><span class="hljs-tag">button</span> (<span class="hljs-attr">type=</span><span class="hljs-string">"submit"</span>, <span class="hljs-attr">class=</span><span class="hljs-string">"btn btn-primary"</span>, <span class="hljs-attr">disabled</span>) <span class="hljs-string">"Submit"</span>
<span class="hljs-tag">img</span> (<span class="hljs-attr">src=</span><span class="hljs-string">"photo.jpg"</span>, <span class="hljs-attr">alt=</span><span class="hljs-string">"A photo"</span>, <span class="hljs-attr">loading=</span><span class="hljs-string">"lazy"</span>)</code></pre>

    <h3>Variables</h3>

    <pre><code><span class="hljs-keyword">set</span> <span class="hljs-variable">page_title</span> = <span class="hljs-string">"My Website"</span>
<span class="hljs-keyword">set</span> <span class="hljs-variable">year</span> = <span class="hljs-string">"2024"</span>

<span class="hljs-tag">html</span>
    <span class="hljs-tag">head</span>
        <span class="hljs-tag">title</span> <span class="hljs-string">"<span class="hljs-variable">${page_title}</span>"</span>
    <span class="hljs-tag">body</span>
        <span class="hljs-tag">h1</span> <span class="hljs-string">"Welcome to <span class="hljs-variable">${page_title}</span>"</span>
        <span class="hljs-tag">footer</span>
            <span class="hljs-tag">p</span> <span class="hljs-string">"&amp;copy; <span class="hljs-variable">${year}</span> All rights reserved."</span></code></pre>

    <h3>Components (Include)</h3>

    <p><strong>main.ehtm:</strong></p>

    <pre><code><span class="hljs-tag">html</span>
    <span class="hljs-tag">head</span>
        <span class="hljs-keyword">include</span> <span class="hljs-string">"components/head.ehtm"</span>
    <span class="hljs-tag">body</span>
        <span class="hljs-keyword">include</span> <span class="hljs-string">"components/header.ehtm"</span>
        <span class="hljs-tag">main</span>
            <span class="hljs-tag">h1</span> <span class="hljs-string">"Page Content"</span>
        <span class="hljs-keyword">include</span> <span class="hljs-string">"components/footer.ehtm"</span></code></pre>

    <p><strong>components/header.ehtm:</strong></p>

    <pre><code><span class="hljs-tag">header</span><span class="hljs-attr">#site-header</span>
    <span class="hljs-tag">nav</span>
        <span class="hljs-tag">a</span> <span class="hljs-attr">href=</span><span class="hljs-string">"/"</span> <span class="hljs-string">"Home"</span>
        <span class="hljs-tag">a</span> <span class="hljs-attr">href=</span><span class="hljs-string">"/about"</span> <span class="hljs-string">"About"</span>
        <span class="hljs-tag">a</span> <span class="hljs-attr">href=</span><span class="hljs-string">"/contact"</span> <span class="hljs-string">"Contact"</span></code></pre>

    <h3>Comments</h3>

    <pre><code><span class="hljs-comment"># This is a comment</span>
<span class="hljs-comment"># TODO: Add more sections</span>

<span class="hljs-tag">div</span>.<span class="hljs-attr">container</span>
    <span class="hljs-comment"># This is the main content area</span>
    <span class="hljs-tag">h1</span> <span class="hljs-string">"Title"</span>
    <span class="hljs-tag">p</span> <span class="hljs-string">"Content"</span></code></pre>

    <h3>Void (Self-Closing) Elements</h3>

    <p>These elements are automatically detected and rendered without closing tags:</p>

    <p><code>area</code>, <code>base</code>, <code>br</code>, <code>col</code>, <code>embed</code>, <code>hr</code>, <code>img</code>, <code>input</code>, <code>link</code>, <code>meta</code>, <code>param</code>, <code>source</code>, <code>track</code>, <code>wbr</code></p>

    <pre><code><span class="hljs-tag">br</span>
<span class="hljs-tag">hr</span>
<span class="hljs-tag">img</span> <span class="hljs-attr">src=</span><span class="hljs-string">"image.jpg"</span> <span class="hljs-attr">alt=</span><span class="hljs-string">"Photo"</span>
<span class="hljs-tag">input</span> <span class="hljs-attr">type=</span><span class="hljs-string">"text"</span> <span class="hljs-attr">name=</span><span class="hljs-string">"username"</span></code></pre>

    <hr>

    <h2>CLI Commands</h2>

    <h3>Basic Commands</h3>

    <table>
        <thead>
            <tr><th>Command</th><th>Description</th></tr>
        </thead>
        <tbody>
            <tr><td><code>ehtm file.ehtm</code></td><td>Compile single file to HTML</td></tr>
            <tr><td><code>ehtm file.ehtm -o out.html</code></td><td>Specify output filename</td></tr>
            <tr><td><code>ehtm -d ./src -o ./dist</code></td><td>Compile entire directory</td></tr>
            <tr><td><code>ehtm --create-sample</code></td><td>Generate sample EHTM file</td></tr>
            <tr><td><code>ehtm --test</code></td><td>Run internal tests</td></tr>
            <tr><td><code>ehtm --version</code></td><td>Show version</td></tr>
            <tr><td><code>ehtm --help</code></td><td>Display help</td></tr>
        </tbody>
    </table>

    <h3>Advanced Options</h3>

    <table>
        <thead>
            <tr><th>Option</th><th>Description</th><th>Default</th></tr>
        </thead>
        <tbody>
            <tr><td><code>-f, --format</code></td><td>Output: <code>pretty</code>, <code>minified</code>, <code>preserve</code></td><td><code>pretty</code></td></tr>
            <tr><td><code>-i, --indent</code></td><td>Indentation size in spaces</td><td><code>4</code></td></tr>
            <tr><td><code>-o, --output</code></td><td>Output file/directory path</td><td>Auto</td></tr>
            <tr><td><code>-d, --directory</code></td><td>Process directory mode</td><td>-</td></tr>
            <tr><td><code>-w, --watch</code></td><td>Watch for file changes</td><td>-</td></tr>
            <tr><td><code>-e, --encoding</code></td><td>File encoding</td><td><code>utf-8</code></td></tr>
            <tr><td><code>--no-doctype</code></td><td>Omit DOCTYPE declaration</td><td>-</td></tr>
            <tr><td><code>-v, --verbose</code></td><td>Verbose error output</td><td>-</td></tr>
        </tbody>
    </table>

    <h3>Watch Mode</h3>

    <pre><code><span class="hljs-comment"># Monitor directory and auto-recompile</span>
<span class="hljs-meta">ehtm</span> -w ./templates

<span class="hljs-comment"># With custom format</span>
<span class="hljs-meta">ehtm</span> -w ./src -f pretty -i 2

<span class="hljs-comment"># Press Ctrl+C to stop</span></code></pre>

    <hr>

    <h2 id="-examples">Examples</h2>

    <h3>Simple Web Page</h3>

    <pre><code><span class="hljs-tag">html</span> <span class="hljs-attr">lang=</span><span class="hljs-string">"en"</span>
    <span class="hljs-tag">head</span>
        <span class="hljs-tag">meta</span> <span class="hljs-attr">charset=</span><span class="hljs-string">"UTF-8"</span>
        <span class="hljs-tag">meta</span> <span class="hljs-attr">name=</span><span class="hljs-string">"viewport"</span> <span class="hljs-attr">content=</span><span class="hljs-string">"width=device-width, initial-scale=1.0"</span>
        <span class="hljs-tag">title</span> <span class="hljs-string">"My Website"</span>
        <span class="hljs-tag">link</span> <span class="hljs-attr">rel=</span><span class="hljs-string">"stylesheet"</span> <span class="hljs-attr">href=</span><span class="hljs-string">"style.css"</span>
    <span class="hljs-tag">body</span>
        <span class="hljs-tag">header</span><span class="hljs-attr">#main-header</span>
            <span class="hljs-tag">h1</span> <span class="hljs-string">"Welcome"</span>
        <span class="hljs-tag">main</span>
            <span class="hljs-tag">section</span>
                <span class="hljs-tag">h2</span> <span class="hljs-string">"About"</span>
                <span class="hljs-tag">p</span> <span class="hljs-string">"This is a simple page."</span>
        <span class="hljs-tag">footer</span>
            <span class="hljs-tag">p</span> <span class="hljs-string">"&amp;copy; 2024"</span></code></pre>

    <h3>Contact Form</h3>

    <pre><code><span class="hljs-tag">form</span> (<span class="hljs-attr">action=</span><span class="hljs-string">"/submit"</span>, <span class="hljs-attr">method=</span><span class="hljs-string">"POST"</span>)
    <span class="hljs-tag">div</span>.<span class="hljs-attr">form-group</span>
        <span class="hljs-tag">label</span> <span class="hljs-attr">for=</span><span class="hljs-string">"name"</span> <span class="hljs-string">"Full Name"</span>
        <span class="hljs-tag">input</span> (<span class="hljs-attr">type=</span><span class="hljs-string">"text"</span>, <span class="hljs-attr">id=</span><span class="hljs-string">"name"</span>, <span class="hljs-attr">name=</span><span class="hljs-string">"name"</span>, <span class="hljs-attr">required</span>)
    <span class="hljs-tag">div</span>.<span class="hljs-attr">form-group</span>
        <span class="hljs-tag">label</span> <span class="hljs-attr">for=</span><span class="hljs-string">"email"</span> <span class="hljs-string">"Email"</span>
        <span class="hljs-tag">input</span> (<span class="hljs-attr">type=</span><span class="hljs-string">"email"</span>, <span class="hljs-attr">id=</span><span class="hljs-string">"email"</span>, <span class="hljs-attr">name=</span><span class="hljs-string">"email"</span>, <span class="hljs-attr">required</span>)
    <span class="hljs-tag">div</span>.<span class="hljs-attr">form-group</span>
        <span class="hljs-tag">label</span> <span class="hljs-attr">for=</span><span class="hljs-string">"message"</span> <span class="hljs-string">"Message"</span>
        <span class="hljs-tag">textarea</span> (<span class="hljs-attr">id=</span><span class="hljs-string">"message"</span>, <span class="hljs-attr">name=</span><span class="hljs-string">"message"</span>, <span class="hljs-attr">rows=</span><span class="hljs-string">"5"</span>) <span class="hljs-string">""</span>
    <span class="hljs-tag">button</span> (<span class="hljs-attr">type=</span><span class="hljs-string">"submit"</span>, <span class="hljs-attr">class=</span><span class="hljs-string">"btn"</span>) <span class="hljs-string">"Send"</span></code></pre>

    <h3>Blog Post with Variables</h3>

    <pre><code><span class="hljs-keyword">set</span> <span class="hljs-variable">title</span> = <span class="hljs-string">"Getting Started with EHTM"</span>
<span class="hljs-keyword">set</span> <span class="hljs-variable">author</span> = <span class="hljs-string">"John Doe"</span>
<span class="hljs-keyword">set</span> <span class="hljs-variable">date</span> = <span class="hljs-string">"2024-01-15"</span>

<span class="hljs-tag">article</span>.<span class="hljs-attr">blog-post</span>
    <span class="hljs-tag">header</span>
        <span class="hljs-tag">h1</span> <span class="hljs-string">"<span class="hljs-variable">${title}</span>"</span>
        <span class="hljs-tag">div</span>.<span class="hljs-attr">meta</span>
            <span class="hljs-tag">span</span> <span class="hljs-string">"By <span class="hljs-variable">${author}</span>"</span>
            <span class="hljs-tag">span</span> <span class="hljs-string">"Published: <span class="hljs-variable">${date}</span>"</span>
    <span class="hljs-tag">div</span>.<span class="hljs-attr">content</span>
        <span class="hljs-tag">p</span> <span class="hljs-string">"EHTM makes web development faster..."</span></code></pre>

    <hr>

    <h2>Comparison</h2>

    <table>
        <thead>
            <tr>
                <th>Feature</th>
                <th>HTML</th>
                <th>Pug</th>
                <th>EHTM</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>No closing tags</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Indentation-based</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Standalone executable</td>
                <td class="check">&check;</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>No Node.js required</td>
                <td class="check">&check;</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>No Python required</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Variables</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Components/Includes</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Minified output</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Watch mode</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
                <td class="check">&check;</td>
            </tr>
            <tr>
                <td>Zero dependencies</td>
                <td class="check">&check;</td>
                <td class="cross">&times;</td>
                <td class="check">&check;</td>
            </tr>
        </tbody>
    </table>

    <hr>

    <h2 id="-documentation">Documentation</h2>

    <p>Full documentation is available at <a href="https://ehtm.dev/docs">ehtm.dev/docs</a> or open <code>docs/index.html</code> from this repository.</p>

    <p>The documentation covers:</p>

    <ul>
        <li>Complete syntax reference</li>
        <li>All CLI commands and options</li>
        <li>Variable system</li>
        <li>Component architecture</li>
        <li>Output formatting</li>
        <li>Error handling guide</li>
        <li>Code examples</li>
        <li>FAQ</li>
    </ul>

    <hr>

    <h2>Common Errors &amp; Solutions</h2>

    <table>
        <thead>
            <tr><th>Error</th><th>Solution</th></tr>
        </thead>
        <tbody>
            <tr><td><code>Undefined variable: 'x'</code></td><td>Add <code>set x = "value"</code> at the top</td></tr>
            <tr><td><code>Inconsistent indentation level</code></td><td>Use uniform spaces (4 per level), no tabs</td></tr>
            <tr><td><code>Included file not found: 'x'</code></td><td>Check the file path is correct</td></tr>
            <tr><td><code>'ehtm' is not recognized</code></td><td>Add ehtm.exe to PATH or use full path</td></tr>
            <tr><td><code>Cannot parse element</code></td><td>Check syntax: <code>tagname "text"</code> or <code>tagname#id.class</code></td></tr>
        </tbody>
    </table>

    <hr>

    <h2>Roadmap</h2>

    <ul>
        <li><input type="checkbox" disabled> Loops and conditionals (<code>for</code>, <code>if/else</code>)</li>
        <li><input type="checkbox" disabled> Filters and built-in functions</li>
        <li><input type="checkbox" disabled> Markdown content blocks</li>
        <li><input type="checkbox" disabled> Live preview server</li>
        <li><input type="checkbox" disabled> VS Code extension with syntax highlighting</li>
        <li><input type="checkbox" disabled> CSS preprocessor integration</li>
        <li><input type="checkbox" disabled> Template inheritance (<code>extends</code>)</li>
        <li><input type="checkbox" disabled> JSON data binding</li>
    </ul>

    <hr>

    <h2>Contributing</h2>

    <p>Contributions are welcome! Here's how you can help:</p>

    <ol>
        <li><strong>Report bugs</strong> - Open an issue with the bug label</li>
        <li><strong>Suggest features</strong> - Open an issue with the enhancement label</li>
        <li><strong>Submit PRs</strong> - Fork the repo, make changes, submit a pull request</li>
        <li><strong>Improve docs</strong> - Help make documentation clearer and more complete</li>
        <li><strong>Share examples</strong> - Submit your EHTM templates to the examples folder</li>
    </ol>

    <h3>Development Setup</h3>

    <pre><code><span class="hljs-comment"># Clone the repository</span>
<span class="hljs-meta">git clone</span> https://github.com/yourusername/ehtm.git
<span class="hljs-meta">cd</span> ehtm

<span class="hljs-comment"># The main compiler is a single Python file</span>
<span class="hljs-comment"># No virtual environment needed for development</span>

<span class="hljs-comment"># Run tests</span>
<span class="hljs-meta">python</span> ehtm3.py --test

<span class="hljs-comment"># Build executable</span>
<span class="hljs-meta">pip install</span> pyinstaller
<span class="hljs-meta">pyinstaller</span> --onefile --name ehtm ehtm3.py</code></pre>

    <hr>

    <h2>License</h2>

    <p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>

    <pre><code>MIT License

Copyright (c) 2024 EHTM Project

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.</code></pre>

    <hr>

    <h2>Acknowledgments</h2>

    <ul>
        <li>Inspired by <a href="https://pugjs.org/">Pug</a> (formerly Jade) for its clean syntax</li>
        <li>Built with Python and compiled with <a href="https://pyinstaller.org/">PyInstaller</a></li>
        <li>Syntax highlighting theme inspired by GitHub's design</li>
    </ul>

    <hr>

    <h2>Support</h2>

    <ul>
        <li><strong>Documentation:</strong> <a href="https://ehtm.dev/docs">ehtm.dev/docs</a></li>
        <li><strong>Issues:</strong> <a href="https://github.com/yourusername/ehtm/issues">GitHub Issues</a></li>
        <li><strong>Discussions:</strong> <a href="https://github.com/yourusername/ehtm/discussions">GitHub Discussions</a></li>
        <li><strong>Email:</strong> support@ehtm.dev</li>
    </ul>

    <hr>

    <p class="text-center">
        <strong>Made with love for web developers who value simplicity.</strong>
    </p>

    <p class="text-center">
        <sub>EHTM &copy; 2024 - Licensed under MIT</sub>
    </p>

</body>
</html>
