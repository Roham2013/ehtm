<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EHTM - Easy HyperText Markup Language</title>
</head>
<body>

    <h1>EHTM - Easy HyperText Markup Language</h1>

    <p><strong>A standalone executable compiler that transforms clean, indentation-based markup into standard HTML.</strong></p>

    <p>
        <strong>Quick Start</strong> &bull;
        <strong>Features</strong> &bull;
        <strong>Installation</strong> &bull;
        <strong>Documentation</strong> &bull;
        <strong>Examples</strong>
    </p>

    <p>
        <img src="https://img.shields.io/badge/version-3.0.0-blue.svg" alt="Version">
        <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg" alt="Platform">
        <img src="https://img.shields.io/badge/dependencies-none-brightgreen.svg" alt="Dependencies">
        <img src="https://img.shields.io/badge/license-MIT-yellow.svg" alt="License">
        <img src="https://img.shields.io/badge/build-standalone%20executable-orange.svg" alt="Build">
    </p>

    <hr>

    <h2>What is EHTM?</h2>

    <p><strong>EHTM</strong> (Easy HyperText Markup Language) is a lightweight markup language that compiles to standard HTML. It uses indentation-based syntax (like Python or Pug) to eliminate closing tags, making your code cleaner and development 50% faster.</p>

    <h3>HTML (Before)</h3>

    <pre><code>&lt;div id="main" class="container"&gt;
    &lt;h1&gt;Hello World&lt;/h1&gt;
    &lt;p&gt;This is a paragraph.&lt;/p&gt;
    &lt;ul&gt;
        &lt;li&gt;Item 1&lt;/li&gt;
        &lt;li&gt;Item 2&lt;/li&gt;
    &lt;/ul&gt;
&lt;/div&gt;</code></pre>

    <h3>EHTM (After)</h3>

    <pre><code>div#main.container
    h1 "Hello World"
    p "This is a paragraph."
    ul
        li "Item 1"
        li "Item 2"</code></pre>

    <hr>

    <h2>Features</h2>

    <ul>
        <li><strong>Standalone Executable</strong> - Single <code>ehtm.exe</code> file. No Python, no Node.js, no dependencies.</li>
        <li><strong>Indentation-Based Syntax</strong> - Structure your document with spaces, not closing tags.</li>
        <li><strong>CSS-Style Selectors</strong> - Use <code>#id</code> and <code>.class</code> directly on elements.</li>
        <li><strong>Variables</strong> - Define values once with <code>set</code> and reuse with <code>${variable}</code>.</li>
        <li><strong>Components</strong> - Include other files with <code>include "file.ehtm"</code>.</li>
        <li><strong>Three Output Modes</strong> - Pretty-printed, minified, or preserved formatting.</li>
        <li><strong>Watch Mode</strong> - Auto-recompile on file changes.</li>
        <li><strong>Cross-Platform</strong> - Runs on Windows, macOS, and Linux.</li>
        <li><strong>Zero Configuration</strong> - Download and run. No setup required.</li>
    </ul>

    <hr>

    <h2>Quick Start</h2>

    <h3>1. Download ehtm.exe</h3>

    <p><strong>IMPORTANT:</strong> Go to the <a href="https://github.com/yourusername/ehtm/releases">Releases page</a> and download <code>ehtm.exe</code> from the latest release. This is the only file you need.</p>

    <p>Place <code>ehtm.exe</code> in your project folder or anywhere in your system PATH.</p>

    <h3>2. Create Your First File</h3>

    <p>Create a new file called <code>hello.ehtm</code>:</p>

    <pre><code>html lang="en"
    head
        meta charset="UTF-8"
        title "My First Page"
    body
        h1 "Hello, World!"
        p "This was built with EHTM."</code></pre>

    <h3>3. Compile to HTML</h3>

    <p>Open a terminal and run:</p>

    <pre><code>ehtm hello.ehtm</code></pre>

    <p>This generates <code>hello.html</code>. Open it in any browser.</p>

    <h3>4. Production Build</h3>

    <pre><code>ehtm hello.ehtm -f minified -o dist/index.html</code></pre>

    <hr>

    <h2>Installation</h2>

    <h3>Download from Releases (Required)</h3>

    <ol>
        <li>Go to the <a href="https://github.com/yourusername/ehtm/releases">Releases page</a></li>
        <li>Download the latest <code>ehtm.exe</code></li>
        <li>Place it in your project folder</li>
        <li>Run it from the terminal</li>
    </ol>

    <h3>Optional: Add to System PATH (Windows)</h3>

    <pre><code># Move ehtm.exe to a permanent location
mkdir C:\tools
move ehtm.exe C:\tools\

# Add to PATH (run PowerShell as Administrator)
[Environment]::SetEnvironmentVariable("Path", $env:Path + ";C:\tools", "Machine")</code></pre>

    <p>After adding to PATH, you can run <code>ehtm</code> from any folder.</p>

    <h3>Verify Installation</h3>

    <pre><code>ehtm --version
# Output: EHTM Compiler v3.0.0</code></pre>

    <hr>

    <h2>Syntax Overview</h2>

    <h3>Basic Elements</h3>

    <pre><code>tagname                           # Basic element
tagname "text content"            # Element with text
tagname#idname                    # Element with ID
tagname.classname                 # Element with class
tagname#id.class1.class2          # Combined</code></pre>

    <h3>Nesting with Indentation</h3>

    <pre><code>body
    header
        nav
            a href="/" "Home"
            a href="/about" "About"
    main
        h1 "Welcome"
        p "Content here"
    footer
        p "Copyright 2024"</code></pre>

    <h3>Attributes (Two Ways)</h3>

    <p><strong>Space-separated:</strong></p>

    <pre><code>a href="https://example.com" target="_blank" "Visit Site"
input type="email" placeholder="Your email" required</code></pre>

    <p><strong>Inside parentheses (comma-separated):</strong></p>

    <pre><code>button (type="submit", class="btn btn-primary", disabled) "Submit"
img (src="photo.jpg", alt="A photo", loading="lazy")</code></pre>

    <h3>Variables</h3>

    <pre><code>set page_title = "My Website"
set year = "2024"

html
    head
        title "${page_title}"
    body
        h1 "Welcome to ${page_title}"
        footer
            p "&copy; ${year} All rights reserved."</code></pre>

    <h3>Components (Include)</h3>

    <p><strong>main.ehtm:</strong></p>

    <pre><code>html
    head
        include "components/head.ehtm"
    body
        include "components/header.ehtm"
        main
            h1 "Page Content"
        include "components/footer.ehtm"</code></pre>

    <p><strong>components/header.ehtm:</strong></p>

    <pre><code>header#site-header
    nav
        a href="/" "Home"
        a href="/about" "About"
        a href="/contact" "Contact"</code></pre>

    <h3>Comments</h3>

    <pre><code># This is a comment
# TODO: Add more sections

div.container
    # Main content area
    h1 "Title"
    p "Content"</code></pre>

    <h3>Self-Closing (Void) Elements</h3>

    <p>These tags close automatically: <code>br</code>, <code>hr</code>, <code>img</code>, <code>input</code>, <code>meta</code>, <code>link</code>, and others.</p>

    <pre><code>br
hr
img src="image.jpg" alt="Photo"
input type="text" name="username"</code></pre>

    <hr>

    <h2>CLI Commands</h2>

    <h3>Basic Commands</h3>

    <table border="1" cellpadding="8" cellspacing="0">
        <tr><th>Command</th><th>Description</th></tr>
        <tr><td><code>ehtm file.ehtm</code></td><td>Compile single file to HTML</td></tr>
        <tr><td><code>ehtm file.ehtm -o out.html</code></td><td>Specify output filename</td></tr>
        <tr><td><code>ehtm -d ./src -o ./dist</code></td><td>Compile entire directory</td></tr>
        <tr><td><code>ehtm -w ./templates</code></td><td>Watch directory and auto-recompile</td></tr>
        <tr><td><code>ehtm --create-sample</code></td><td>Generate sample EHTM file</td></tr>
        <tr><td><code>ehtm --version</code></td><td>Show version</td></tr>
        <tr><td><code>ehtm --help</code></td><td>Display help</td></tr>
    </table>

    <h3>Advanced Options</h3>

    <table border="1" cellpadding="8" cellspacing="0">
        <tr><th>Option</th><th>Description</th><th>Default</th></tr>
        <tr><td><code>-f, --format</code></td><td>pretty, minified, preserve</td><td>pretty</td></tr>
        <tr><td><code>-i, --indent</code></td><td>Indentation size in spaces</td><td>4</td></tr>
        <tr><td><code>-o, --output</code></td><td>Output path</td><td>Auto</td></tr>
        <tr><td><code>-d, --directory</code></td><td>Process directory</td><td>-</td></tr>
        <tr><td><code>-w, --watch</code></td><td>Watch for changes</td><td>-</td></tr>
        <tr><td><code>-e, --encoding</code></td><td>File encoding</td><td>utf-8</td></tr>
        <tr><td><code>--no-doctype</code></td><td>Omit DOCTYPE</td><td>-</td></tr>
        <tr><td><code>-v, --verbose</code></td><td>Verbose errors</td><td>-</td></tr>
    </table>

    <hr>

    <h2>Examples</h2>

    <h3>Simple Web Page</h3>

    <pre><code>html lang="en"
    head
        meta charset="UTF-8"
        meta name="viewport" content="width=device-width, initial-scale=1.0"
        title "My Website"
        link rel="stylesheet" href="style.css"
    body
        header#main-header
            h1 "Welcome"
        main
            section
                h2 "About"
                p "This is a simple page."
        footer
            p "&copy; 2024"</code></pre>

    <h3>Contact Form</h3>

    <pre><code>form (action="/submit", method="POST")
    div.form-group
        label for="name" "Full Name"
        input (type="text", id="name", name="name", required)
    div.form-group
        label for="email" "Email"
        input (type="email", id="email", name="email", required)
    div.form-group
        label for="message" "Message"
        textarea (id="message", name="message", rows="5") ""
    button (type="submit", class="btn") "Send"</code></pre>

    <h3>Blog Post with Variables</h3>

    <pre><code>set title = "Getting Started with EHTM"
set author = "John Doe"
set date = "2024-01-15"

article.blog-post
    header
        h1 "${title}"
        div.meta
            span "By ${author}"
            span "Published: ${date}"
    div.content
        p "EHTM makes web development faster..."</code></pre>

    <hr>

    <h2>Comparison with HTML and Pug</h2>

    <table border="1" cellpadding="8" cellspacing="0">
        <tr>
            <th>Feature</th>
            <th>HTML</th>
            <th>Pug</th>
            <th>EHTM</th>
        </tr>
        <tr>
            <td>No closing tags</td>
            <td>No</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Indentation-based</td>
            <td>No</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Standalone executable</td>
            <td>Yes</td>
            <td>No</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>No Node.js required</td>
            <td>Yes</td>
            <td>No</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>No Python required</td>
            <td>Yes</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Variables</td>
            <td>No</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Components/Includes</td>
            <td>No</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Minified output</td>
            <td>No</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Watch mode</td>
            <td>No</td>
            <td>Yes</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Zero dependencies</td>
            <td>Yes</td>
            <td>No</td>
            <td>Yes</td>
        </tr>
    </table>

    <hr>

    <h2>Full Documentation</h2>

    <p><strong>For complete documentation with detailed explanations, more examples, and interactive code samples, download the <code>doc.html</code> file from this repository and open it in your browser.</strong></p>

    <p>The documentation file (<code>doc.html</code>) includes:</p>

    <ul>
        <li>Complete syntax reference with examples</li>
        <li>All CLI commands and options explained</li>
        <li>Variable system guide</li>
        <li>Component architecture tutorial</li>
        <li>Output formatting options</li>
        <li>Error handling and troubleshooting</li>
        <li>Advanced code examples</li>
        <li>Frequently asked questions</li>
        <li>Interactive sidebar navigation</li>
        <li>Search functionality</li>
    </ul>

    <p><strong>How to get the documentation:</strong></p>

    <ol>
        <li>Download <code>doc.html</code> from this repository</li>
        <li>Open it in any web browser</li>
        <li>Use the sidebar to navigate between sections</li>
        <li>Use Ctrl+K to search within the documentation</li>
    </ol>

    <hr>

    <h2>Common Errors &amp; Solutions</h2>

    <table border="1" cellpadding="8" cellspacing="0">
        <tr><th>Error</th><th>Solution</th></tr>
        <tr><td><code>Undefined variable: 'x'</code></td><td>Add <code>set x = "value"</code> at the top of your file</td></tr>
        <tr><td><code>Inconsistent indentation level</code></td><td>Use consistent spaces (4 per level). Do not mix tabs and spaces.</td></tr>
        <tr><td><code>Included file not found</code></td><td>Check that the file path is correct and relative to your current file</td></tr>
        <tr><td><code>'ehtm' is not recognized</code></td><td>Add <code>ehtm.exe</code> to your system PATH or use the full path to the executable</td></tr>
        <tr><td><code>Cannot parse element</code></td><td>Check your syntax: elements must follow <code>tagname "text"</code> or <code>tagname#id.class</code> format</td></tr>
    </table>

    <hr>

    <h2>Contributing</h2>

    <p>Contributions are welcome! Here's how you can help:</p>

    <ul>
        <li><strong>Report bugs</strong> - Open an issue on GitHub</li>
        <li><strong>Suggest features</strong> - Open an issue with the enhancement label</li>
        <li><strong>Submit code</strong> - Fork the repository, make changes, and submit a pull request</li>
        <li><strong>Share examples</strong> - Submit your EHTM templates</li>
    </ul>

    <hr>

    <h2>License</h2>

    <p>MIT License - Copyright (c) 2024 EHTM Project</p>

    <p>See the <a href="LICENSE">LICENSE</a> file for full details.</p>

    <hr>

    <p><strong>Made for web developers who value simplicity.</strong></p>

    <p><sub>EHTM &copy; 2024 - Licensed under MIT</sub></p>

</body>
</html>
