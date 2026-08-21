# VS 2017 Dark

A Zed theme inspired by the Visual Studio 2017 Dark theme.

## Installation

### Development installation

1. Open Zed's command palette.
2. Run `zed: install dev extension`.
3. Select this repository's root directory.
4. Open the theme selector and choose **VS 2017 Dark**.

## C/C++ semantic highlighting

Zed disables semantic tokens by default. Enable combined semantic highlighting so
clangd can distinguish enum members, classes, types, and other C/C++ symbols.

Open your Zed `settings.json` and add:

```jsonc
{
  "semantic_tokens": "combined"
}
```

If enum members still do not use the intended color, add the following semantic
token rules as well. Merge these properties into your existing settings rather
than replacing the entire file.

```jsonc
{
  "semantic_tokens": "combined",

  "global_lsp_settings": {
    "semantic_token_rules": [
      {
        "token_type": "enumMember",
        "style": ["enum.member", "variant"]
      },
      {
        "token_type": "enumConstant",
        "style": ["enum.member", "variant"]
      }
    ]
  }
}
```

After changing this setting, run `editor: restart language server` or restart
Zed. Theme extensions cannot modify user settings automatically, so this step
must be completed manually.

## Attribution

This project is not affiliated with or endorsed by Microsoft.

The color palette and syntax highlighting are based on Microsoft's
[`2017 Dark (Visual Studio - C/C++)`](https://github.com/microsoft/vscode-cpptools/blob/main/Themes/themes/cpptools_dark_vs.json)
theme.

Microsoft's copyright notice and the applicable MIT license are reproduced in
[`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md).

## Feedback

Please report issues and suggestions through
[GitHub Issues](https://github.com/exelsior87/zed-vs-2017-dark-theme/issues).
