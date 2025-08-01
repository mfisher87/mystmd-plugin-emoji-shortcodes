A [MySTMD](https://github.com/jupyter-book/mystmd) plugin adding support for
transforming emoji shortcodes (`:smile:`) to unicode (😊) at build-time.


## Installation

List this plugin as a
[plugin](https://mystmd.org/guide/plugins#plugins-use)
in your `myst.yml`:

```yaml
# ...
project:
  # ...
  plugins:
    - "..."
# ...
```


## Limitations

This plugin includes a static export of
[GitHub emoji](https://github.com/github/gemoji)
([source data](https://raw.githubusercontent.com/github/gemoji/master/db/emoji.json)),
mapping all possible shortcodes to the corresponding emoji characters in a JavaScript
object.

Other emoji sets aren't supported. This decision was made to making this plugin
dependency-free, simplifying install for users.


### Re-generating the mapping

Run `generate-github-emoji-mapping.js`, then copy the mapping to the `emojiMap` variable
in the plugin file `emoji-shortcodes.mjs`.


## Troubleshooting

### Some emojis don't render as expected

If some emojis are rendering all weird, it could be because the font you're using
doesn't include those emojis.
