[![Build Status](https://travis-ci.org/woodyrew/metalsmith-data-files.svg?branch=master)](https://travis-ci.org/woodyrew/metalsmith-data-files)

# Metalsmith JSON and/or YAML to files
Creates files from supplied JSON

A [Metalsmith](https://github.com/segmentio/metalsmith) plugin that lets you generate files from `JSON`.

## Features
- `JSON` or `YAML` is accepted
- Many files can be processed in parallel
- Filename is configurable and generated from source file
- Permalink style filenames make for pretty URLs
- Configurable with `JSON`, `YAML` or JavaScript Objects

## Expectations
- `JSON` or `YAML` to be an array of objects. Each object will result in a file.

## Installation
```bash
$ npm install metalsmith-data-files
```

## Usage

### Example usage
```js
var json_to_files = require('metalsmith-data-files');

metalsmith.use(data_files('data_files_conf.yaml')),
// or
metalsmith.use(data_files([
    {
        source_file: './path/to/yaml_data.yaml',
        filename_pattern: ':date-:slug'
    },
    {
        source_file: './path/to/json_data.json',
        filename_pattern: 'posts/:date-:slug',
        as_permalink: true, // optional
        transformations: function (data) { return data }, // optional
        // Any extra properties will be passed to the frontmatter as is.
        layout: 'post.hbs'
    }
]));
```

## Examples

## Testing
`npm test` will run through the test suite.

For development:
`npm run dev-test` will use nodemon to watch for changes and run the test suite.

## License
GPL-2.0
