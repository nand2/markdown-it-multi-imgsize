# markdown-it-multi-imgsize

Forked from [the original markdown-it-obsidian-imgsize](https://github.com/uuanqin/markdown-it-obsidian-imgsize), it adds support for width percentage. It transforms

```markdown
![A cat|40%](cat.jpg)
```
to
```html
<p><img src="cat.jpg" alt="A cat" width="40%"></p>
```

## Original documentation

language: English | [中文](./README_zh.md)

A markdown-it plugin, adding width (and height) attributes to image elements.

According to [the syntax of external images in Obsidian](https://help.obsidian.md/Editing+and+formatting/Basic+formatting+syntax#External+images)
, it transforms
```markdown
![A cat|100](cat.jpg)
![A cat|100x200](cat.jpg)
```
to
```html
<p><img src="cat.jpg" alt="A cat" width="100px"></p>
<p><img src="cat.jpg" alt="A cat" width="100px" height="200px"></p>
```

More cases are in [examples.md](./test/examples.md). Different from [markdown-it-renderer-image](https://www.npmjs.com/package/@peaceroad/markdown-it-renderer-image), 
this plugin does not use the Internet when processing online images.

## Install

```bash
npm i markdown-it-multi-imgsize --save
```

## Use

```js
const md = require('markdown-it')();
const mdImgSizePlg = require('markdown-it-multi-imgsize');
md.use(mdImgSizePlg);

const content = '![A cat|100](cat.jpg)';
console.log(md.render(content));
// <p><img src="cat.jpg" alt="A cat" width="100px"></p>
// See './test/examples.md' for more examples
```

## Related Plugins

[markdown-it-renderer-image](https://www.npmjs.com/package/@peaceroad/markdown-it-renderer-image)

[markdown-it-obsidian-images](https://www.npmjs.com/package/markdown-it-obsidian-images)

## License
MIT



