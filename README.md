# Tokyo Nightlife

![GitHub package.json version](https://img.shields.io/github/package-json/v/mambroz27/tokyo-nightlife/main?style=flat)
![GitHub License](https://img.shields.io/github/license/mambroz27/tokyo-nightlife?style=flat)

A dark theme for Visual Studio Code inspired by [Tokyo Night](https://github.com/tokyo-night/tokyo-night-vscode-theme), built around readability.

> **Note:** Tokyo Nightlife is an independent theme inspired by the look of Tokyo Night. It is not a fork of, and is not affiliated with or endorsed by, the original Tokyo Night project.

## Features

- Full [semantic highlighting](https://code.visualstudio.com/api/language-extensions/semantic-highlight-guide) support, with dedicated colors for default-library symbols where the language grammar supports it
- No token is ever colored using the error color, so errors are always unambiguous
- A deliberately smaller, shared color set (rather than one color per token type) to keep code visually calm and reduce eye fatigue
- Tuned indent guides, bracket-pair colors, and diff/git colors to match the rest of the palette
- Recommended pairing with [JetBrains Mono](https://www.jetbrains.com/lp/mono/)

## Screenshots

**Tokyo Nightlife**
![Screenshot of Tokyo Nightlife theme](https://raw.githubusercontent.com/mambroz27/tokyo-nightlife/main/assets/tokyo-nightlife-sample.png)

_Note: [JetBrains Mono](https://www.jetbrains.com/lp/mono/) is the font used in these screenshots._

## Installation

**From the Marketplace:**

1. Open the Extensions view in VS Code (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Search for `Tokyo Nightlife`
3. Click **Install**, then select it from the Color Theme picker (`Ctrl+K Ctrl+T` / `Cmd+K Cmd+T`)

**From the command line:**

```
code --install-extension mambroz27.tokyo-nightlife
```

## Customization

### Disable Italics

Tokyo Nightlife uses italics for comments. If you prefer to disable italics, you can add this snippet to your [`settings.json`](https://code.visualstudio.com/docs/getstarted/settings#_settings-file-locations).

```jsonc
"editor.tokenColorCustomizations": {
    "[Tokyo Nightlife]": {
        "textMateRules": [{
            "scope": [
                "comment",
                "punctuation.definition.comment"
            ],
            "settings": {
                "fontStyle": ""
            }
        }]
    }
}
```

### Enable JSDoc Highlighting

To enable JSDoc highlighting, you can add this snippet to your [`settings.json`](https://code.visualstudio.com/docs/getstarted/settings#_settings-file-locations).

The colors used for JSDoc highlighting are mixed with the default comment colors, this keeps the highlighting consistent with the theme's color palette but mutes the colors slightly to avoid being too jarring within the context of a comment. These accent colors (`#A394DE`, `#78BAC3`, `#B9A188`) are only used here - they're muted variants layered on top of the base comment color and don't appear in the core palette below.

```jsonc
"editor.tokenColorCustomizations": {
    "[Tokyo Nightlife]": {
        "textMateRules": [
            {
                "scope": [
                    "comment keyword.codetag.notation",
                    "comment.block.documentation keyword",
                    "comment.block.documentation storage.type.class"
                ],
                "settings": {
                    "foreground": "#a394de"
                }
            },
            {
                "scope": ["comment.block.documentation entity.name.type.instance"],
                "settings": {
                    "foreground": "#78bac3",
                    "fontStyle": "italic"
                }
            },
            {
                "scope": [
                    "comment.block.documentation entity.name.type punctuation.definition.bracket"
                ],
                "settings": {
                    "foreground": "#a394de"
                }
            },
            {
                "scope": ["comment.block.documentation variable"],
                "settings": {
                    "foreground": "#b9a188",
                    "fontStyle": "italic"
                }
            }
        ]
    }
}
```

## The Color Palette

The palette was chosen to balance contrast and readability. Two principles guided it in particular:

- **Error Clarity**: No tokens reuse the error color (<img valign='middle' alt='#F7768E' src='https://readme-swatches.vercel.app/F7768E?style=round&size=12'/> #F7768E) so errors are always clear and easy to identify.
- **Shared Colors**: Some tokens share colors (e.g. <img valign='middle' alt='#BB9AF7' src='https://readme-swatches.vercel.app/BB9AF7?style=round&size=12'/> #BB9AF7 for keywords _and_ primitive types _and_ storage modifiers) for a less fragmented palette that prevents "jumbled" colors and reduces fatigue.
- **Leverage Semantic Highlighting**: When possible, semantic-highlighting-aware languages (e.g. TypeScript, Rust, etc.) can take advantage of colors defined only in `semanticTokenColors` (e.g. <img valign='middle' alt='#2AC3DE' src='https://readme-swatches.vercel.app/2AC3DE?style=round&size=12'/> #2AC3DE for default-library symbols).

### Editor & UI Surfaces

|                                              Swatch                                              |   Hex   | Usage                                   |
| :----------------------------------------------------------------------------------------------: | :-----: | :-------------------------------------- |
| <img valign='middle' alt='#1A1B26' src='https://readme-swatches.vercel.app/1A1B26?style=round'/> | #1A1B26 | Editor background                       |
| <img valign='middle' alt='#16161E' src='https://readme-swatches.vercel.app/16161E?style=round'/> | #16161E | Sidebar, panel, activity bar background |
| <img valign='middle' alt='#1E202E' src='https://readme-swatches.vercel.app/1E202E?style=round'/> | #1E202E | Line highlight, drop background         |

### Syntax & Token Colors

|                                              Swatch                                              |   Hex   | Usage                                                                                                                                                                                         |
| :----------------------------------------------------------------------------------------------: | :-----: | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img valign='middle' alt='#C8D3F5' src='https://readme-swatches.vercel.app/C8D3F5?style=round'/> | #C8D3F5 | Default editor foreground / plain text, embedded code, Java import identifiers, operators, template expressions                                                                               |
| <img valign='middle' alt='#C0CAF5' src='https://readme-swatches.vercel.app/C0CAF5?style=round'/> | #C0CAF5 | Variables, semantic variable & customLiteral tokens                                                                                                                                           |
| <img valign='middle' alt='#6C7599' src='https://readme-swatches.vercel.app/6C7599?style=round'/> | #6C7599 | Comments (italic)                                                                                                                                                                             |
| <img valign='middle' alt='#7F8BB8' src='https://readme-swatches.vercel.app/7F8BB8?style=round'/> | #7F8BB8 | Docblock/JSDoc comment content                                                                                                                                                                |
| <img valign='middle' alt='#BB9AF7' src='https://readme-swatches.vercel.app/BB9AF7?style=round'/> | #BB9AF7 | Keywords, storage/storage.type/modifier, language constants (true/false/null/this), primitive types, SCSS at-rules, preprocessor directives, deprecated markup, semantic variable.declaration |
| <img valign='middle' alt='#7AA2F7' src='https://readme-swatches.vercel.app/7AA2F7?style=round'/> | #7AA2F7 | Function & method names, decorators, HTML tags, markdown H3 heading, generic markup bold/heading, diff headers, ENV values, JSON key (level 0)                                                |
| <img valign='middle' alt='#73DACA' src='https://readme-swatches.vercel.app/73DACA?style=round'/> | #73DACA | Types, classes, interfaces, namespaces; markdown links; JSON key (level 1)                                                                                                                    |
| <img valign='middle' alt='#7DCFFF' src='https://readme-swatches.vercel.app/7DCFFF?style=round'/> | #7DCFFF | Attribute names, object/property keys, CSS custom properties, regexp constants, Python dict keys, markdown H1 heading, semantic property, JSON key (level 2)                                  |
| <img valign='middle' alt='#89DDFF' src='https://readme-swatches.vercel.app/89DDFF?style=round'/> | #89DDFF | Import/export/module keywords, SQL keywords, template string interpolation punctuation, fenced code blocks, semantic newOperator                                                              |
| <img valign='middle' alt='#E0AF68' src='https://readme-swatches.vercel.app/E0AF68?style=round'/> | #E0AF68 | Function parameters, CSS tag/class/id/pseudo selectors, semantic parameter                                                                                                                    |
| <img valign='middle' alt='#9ABDF5' src='https://readme-swatches.vercel.app/9ABDF5?style=round'/> | #9ABDF5 | General punctuation, braces, brackets                                                                                                                                                         |
| <img valign='middle' alt='#9ECE6A' src='https://readme-swatches.vercel.app/9ECE6A?style=round'/> | #9ECE6A | Strings, inline code/raw markup, inserted (diff), semantic stringLiteral                                                                                                                      |
| <img valign='middle' alt='#B4F9F8' src='https://readme-swatches.vercel.app/B4F9F8?style=round'/> | #B4F9F8 | String regexp content                                                                                                                                                                         |
| <img valign='middle' alt='#FF9E64' src='https://readme-swatches.vercel.app/FF9E64?style=round'/> | #FF9E64 | Numeric constants, other constants, CSS property values, unit keywords, semantic numberLiteral                                                                                                |
| <img valign='middle' alt='#2AC3DE' src='https://readme-swatches.vercel.app/2AC3DE?style=round'/> | #2AC3DE | Default-library symbols (semantic token)                                                                                                                                                      |
| <img valign='middle' alt='#61BDF2' src='https://readme-swatches.vercel.app/61BDF2?style=round'/> | #61BDF2 | Markdown H2 heading                                                                                                                                                                           |
| <img valign='middle' alt='#8EA0D0' src='https://readme-swatches.vercel.app/8EA0D0?style=round'/> | #8EA0D0 | Markdown H4-H6 headings                                                                                                                                                                       |
| <img valign='middle' alt='#F7768E' src='https://readme-swatches.vercel.app/F7768E?style=round'/> | #F7768E | Errors / invalid tokens only (reserved - never used for regular syntax)                                                                                                                       |

## Contributing

Issues and pull requests are welcome - see the [issue tracker](https://github.com/mambroz27/tokyo-nightlife/issues) to report a scope that renders incorrectly or looks off, or to suggest a new language/plugin scope to support.

## License

Released under the [MIT License](LICENSE).
