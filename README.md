# hexo-symbols-count-time-2

> This a fork of [hexo-symbols-count-time](https://github.com/theme-next/hexo-symbols-count-time)

[![lic-image]](LICENSE)
[![Coverage Status](https://coveralls.io/repos/github/uiolee/hexo-symbols-count-time-2/badge.svg?branch=main)](https://coveralls.io/github/uiolee/hexo-symbols-count-time-2?branch=main)
[![test](https://github.com/uiolee/hexo-symbols-count-time-2/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/uiolee/hexo-symbols-count-time-2/actions/workflows/ci.yml)

Symbols count and time to read for articles in Hexo blog.

Better than [`hexo-reading-time`](https://github.com/ierhyna/hexo-reading-time) and faster than [`hexo-wordcount`](https://github.com/willin/hexo-wordcount). No external dependencies.

## Installation

[![npm-image]][npm-url]
[![size-image]][npm-url]
[![dm-image]][npm-url]
[![dt-image]][npm-url]

```sh
pnpm add hexo-symbols-count-time-2
```

or

```sh
npm i hexo-symbols-count-time-2
```

## Usage

You can set options of hexo-symbols-count-time-2 in the **Hexo's `_config.yml`** (which locates in the root dir of your blog):

```yml
symbols_count_time:
  symbols: true
  time: true
  total_symbols: true
  total_time: true
  exclude_codeblock: false
  awl: 4
  wpm: 275
  suffix: "mins."
```

If `symbols_count_time` option is not specified, the default parameters will be used.

### Parameters

- `awl` – Average Word Length (chars count in word). Default: `4`. You can check this [here](https://charactercounttool.com).
  - CN &asymp; `2`
  - EN &asymp; `5`
  - RU &asymp; `6`
- `wpm` – Words Per Minute. Default: `275`. You can check this [here](https://wordcounter.net).
  - Slow &asymp; `200`
  - Normal &asymp; `275`
  - Fast &asymp; `350`
- `suffix` – If time to read less then 60 minutes, added suffix as string parameter.\
  If not defined, `mins.` will be used as default.
- `exclude_codeblock` – Allow to exclude all content inside code blocks for more accurate words counting.\
  If not defined, `false` will be used as default.

**Note for Chinese users:** because in Chinese language average word length about `~1.5` and if you at most cases write posts in Chinese (without mixed English), recommended to set `awl` to `2` and `wpm` to `300`.\
But if you usualy mix your posts with English, `awl` to `4` and `wpm` to `275` will be nice.

### NexT theme

This plugin integrated in «NexT» and after plugin enabled in main Hexo config, you may adjust options in NexT config:

```yml
symbols_count_time:
  separated_meta: true
  item_text_post: true
  item_text_total: false
```

### Templates

#### Symbols Count

```js
{
  {
    symbolsCount(post);
  }
}
```

#### Symbols Time

```js
{
  {
    symbolsTime(post);
  }
}
```

Or with predefined parameters:

```js
{
  {
    symbolsTime(post, awl, wpm, suffix);
  }
}
```

#### Symbols Count Total

```js
{
  {
    symbolsCountTotal(site);
  }
}
```

#### Symbols Time Total

```js
{
  {
    symbolsTimeTotal(site);
  }
}
```

Or with predefined parameters:

```js
{
  {
    symbolsTimeTotal(site, awl, wpm, suffix);
  }
}
```

#### Renderers syntax

SWIG / Nunjucks: `{{` `template` `}}`\
EJS: `<%-` `template` `%>`\
Jade: `span=` `template`

[npm-image]: https://img.shields.io/npm/v/hexo-symbols-count-time-2?style=flat-square
[hexo-image]: https://img.shields.io/badge/hexo-%3E%3D%206.0-blue?style=flat-square
[node-image]: https://img.shields.io/node/v/hexo-symbols-count-time-2?style=flat-square
[cover-image]: https://img.shields.io/coveralls/uiolee/hexo-symbols-count-time-2/main?style=flat-square
[lic-image]: https://img.shields.io/npm/l/hexo-symbols-count-time-2?style=flat-square
[size-image]: https://img.shields.io/github/languages/code-size/uiolee/hexo-symbols-count-time-2?style=flat-square
[dm-image]: https://img.shields.io/npm/dm/hexo-symbols-count-time-2?style=flat-square
[dt-image]: https://img.shields.io/npm/dt/hexo-symbols-count-time-2?style=flat-square
[npm-url]: https://www.npmjs.com/package/hexo-symbols-count-time-2
[node-url]: https://nodejs.org/en/download/releases
[hexo-url]: https://hexo.io
[cover-url]: https://coveralls.io/github/uiolee/hexo-symbols-count-time-2?branch=main "Coverage of Tests"
