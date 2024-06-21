# Cross-Origin Headers

Adds an `Access-Control-Allow-Origin` header to any request made to a template that includes this tag.

## Requirements

- ExpressionEngine 2

## Installation

Install as a composer package:

```composer require ggc/cross-origin-headers="^1.1.0"```

## Usage

### `{exp:casey_cross_origin_headers}`

#### Example Usage

The Cross-Origin Headers plugin is a single tag that you can put anywhere in your template. It might be best to put it near the top, or at least in your template comments so it's clear to anyone reading your template for the first time what's going on.

```
{exp:casey_cross_origin_headers}
```

#### Parameters

##### domain= (default: `*`)

A specific domain to allow cross-origin access. The default `*` will allow the request to come from any source, essentially making this a public resource.

```
{exp:casey_cross_origin_headers domain='http://example.com|https://example2.com'}
```

Due to a practical restriction in implementation of the [Access-Control-Allow-Origin standard](https://www.w3.org/TR/cors/#access-control-allow-origin-response-header), you can only specify a single origin. Therefore this plugin works when you want a fully public resource, or restricted to a single origin. If you need endpoints to be available from multiple domains, but not be public, then you will need to handle that in your server configuration. See the article [Cross-Origin Resource Sharing](https://expressionengine.com/learn/cross-origin-resource-sharing-cors) for potential options.

**Note:** You must specify the protocol (`http://`, `https://`) with the domain, as each are treated as separate origins.

## Change Log

### 1.0.0

- Initial release. Boom!

### 1.1.0

- Added the ability to specify multiple domains to allow cross-origin access.

## Additional Files

You may be wondering what the rest of the files in this package are for. They are solely for development, so if you are forking the GitHub repo, they can be helpful. If you are just using the add-on in your ExpressionEngine installation, you can ignore all of these files.

- **.editorconfig**: [EditorConfig](http://editorconfig.org) helps developers maintain consistent coding styles across files and text editors.
- **.gitignore:** [.gitignore](https://git-scm.com/docs/gitignore) lets you specify files in your working environment that you do not want under source control.
- **.composer.json:** A [Composer project setup file](https://getcomposer.org/doc/01-basic-usage.md) that manages development dependencies.

## License

Copyright (C) 2016 EllisLab, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL ELLISLAB, INC. BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Except as contained in this notice, the name of EllisLab, Inc. shall not be used in advertising or otherwise to promote the sale, use or other dealings in this Software without prior written authorization from EllisLab, Inc.
