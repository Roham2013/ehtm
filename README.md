<pre>
# EHTM - Easy HyperText Markup Language

A standalone executable compiler that transforms clean, indentation-based
markup into standard HTML. No dependencies required.


## What is EHTM?

EHTM uses indentation instead of closing tags. Write 50% less code.

HTML (Before):
    &lt;div id="main" class="container"&gt;
        &lt;h1&gt;Hello World&lt;/h1&gt;
        &lt;p&gt;This is a paragraph.&lt;/p&gt;
    &lt;/div&gt;

EHTM (After):
    div#main.container
        h1 "Hello World"
        p "This is a paragraph."


## Features

- Single ehtm.exe file, no Python, no Node.js, no dependencies
- Indentation-based syntax, no closing tags
- CSS-style selectors: #id and .class
- Variables with set and ${variable}
- Components with include "file.ehtm"
- Three output modes: pretty, minified, preserve
- Watch mode for auto-recompile
- Cross-platform: Windows, macOS, Linux
- Zero configuration, just download and run


## Quick Start

1. DOWNLOAD: Get ehtm.exe from the Releases page:
   https://github.com/yourusername/ehtm/releases

2. CREATE a file called hello.ehtm:

    html lang="en"
        head
            meta charset="UTF-8"
            title "My First Page"
        body
            h1 "Hello, World!"
            p "Built with EHTM."

3. COMPILE to HTML:

    ehtm hello.ehtm

    This creates hello.html - open it in any browser.

4. PRODUCTION build:

    ehtm hello.ehtm -f minified -o dist/index.html


## Installation

Download ehtm.exe from the Releases page (REQUIRED):

    1. Go to: https://github.com/yourusername/ehtm/releases
    2. Download ehtm.exe
    3. Place it in your project folder
    4. Run it from terminal

Optional - Add to PATH (Windows):

    mkdir C:\tools
    move ehtm.exe C:\tools\
    # Run PowerShell as Administrator:
    [Environment]::SetEnvironmentVariable("Path", $env:Path + ";C:\tools", "Machine")

Verify:

    ehtm --version
    # Output: EHTM Compiler v3.0.0


## Syntax

Basic Elements:
    tagname                     # Basic element
    tagname "text"              # With text
    tagname#id                  # With ID
    tagname.class               # With class
    tagname#id.class1.class2    # Combined

Nesting (use spaces, not tabs):
    body
        header
            nav
                a href="/" "Home"
        main
            h1 "Welcome"

Attributes - Space separated:
    a href="/link" target="_blank" "Click"
    input type="text" placeholder="Name" required

Attributes - Parentheses:
    button (type="submit", class="btn", disabled) "Send"
    img (src="pic.jpg", alt="Photo", loading="lazy")

Variables:
    set title = "My Site"
    set year = "2024"

    html
        head
            title "${title}"
        body
            h1 "Welcome to ${title}"
            footer
                p "Copyright ${year}"

Components:
    main.ehtm:
        html
            head
                include "components/head.ehtm"
            body
                include "components/header.ehtm"
                main
                    h1 "Content"
                include "components/footer.ehtm"

    components/header.ehtm:
        header#site-header
            nav
                a href="/" "Home"
                a href="/about" "About"

Comments:
    # This is a comment
    div.container
        # Main section
        h1 "Title"

Self-closing tags (automatic):
    br, hr, img, input, meta, link, source, track, wbr

    br
    hr
    img src="photo.jpg" alt="Image"
    input type="text" name="user"


## CLI Commands

Basic:
    ehtm file.ehtm                  Compile file to HTML
    ehtm file.ehtm -o out.html      Custom output name
    ehtm -d ./src -o ./dist         Compile directory
    ehtm -w ./templates             Watch and auto-recompile
    ehtm --create-sample            Create sample file
    ehtm --version                  Show version
    ehtm --help                     Show help

Options:
    -f, --format    pretty | minified | preserve    [default: pretty]
    -i, --indent    Spaces per level                [default: 4]
    -o, --output    Output path                     [auto]
    -d, --directory Process directory               [off]
    -w, --watch     Watch for changes               [off]
    -e, --encoding  File encoding                   [utf-8]
    --no-doctype    Remove DOCTYPE                  [off]
    -v, --verbose   Show detailed errors            [off]


## Examples

Simple page:
    html lang="en"
        head
            meta charset="UTF-8"
            title "My Site"
            link rel="stylesheet" href="style.css"
        body
            header
                h1 "Welcome"
            main
                p "Hello World"
            footer
                p "Copyright 2024"

Contact form:
    form (action="/submit", method="POST")
        div.form-group
            label for="name" "Name"
            input (type="text", id="name", required)
        div.form-group
            label for="email" "Email"
            input (type="email", id="email", required)
        button (type="submit") "Send"

Blog post with variables:
    set title = "My Blog Post"
    set author = "John"
    set date = "2024-01-15"

    article
        header
            h1 "${title}"
            p "By ${author} on ${date}"
        div.content
            p "Post content here..."


## Comparison

    Feature              HTML     Pug     EHTM
    ─────────────────────────────────────────
    No closing tags       No      Yes     Yes
    Indentation syntax    No      Yes     Yes
    Standalone exe        Yes     No      Yes
    No Node.js needed     Yes     No      Yes
    No Python needed      Yes     Yes     Yes
    Variables             No      Yes     Yes
    Components            No      Yes     Yes
    Minified output       No      Yes     Yes
    Watch mode            No      Yes     Yes
    Zero dependencies     Yes     No      Yes


## Full Documentation

For complete documentation, download doc.html from this repository
and open it in your browser.

The documentation includes:
    - Complete syntax reference
    - All CLI commands explained
    - Variable system guide
    - Component architecture
    - Output formatting options
    - Error troubleshooting
    - Advanced examples
    - FAQ
    - Search functionality

Get doc.html from the repository and open it in any browser.
Use the sidebar to navigate and Ctrl+K to search.


## Common Errors

Error: Undefined variable: 'x'
Fix:   Add 'set x = "value"' at top of file

Error: Inconsistent indentation level
Fix:   Use consistent spaces, no tabs

Error: Included file not found
Fix:   Check the path is correct

Error: 'ehtm' is not recognized
Fix:   Add ehtm.exe to PATH or use full path

Error: Cannot parse element
Fix:   Check syntax: tagname "text" or tagname#id.class


## Contributing

- Report bugs on GitHub Issues
- Suggest features on GitHub Issues
- Submit pull requests
- Share your EHTM templates


## License

MIT License - Copyright (c) 2024 EHTM Project


Made for developers who value simplicity.
EHTM Copyright 2024 - MIT License
</pre>
