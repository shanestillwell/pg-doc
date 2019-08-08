# pg-doc

Produce **markdown** schema documentation for your **Postgres** database.

# Installation
```
npm i pg-doc
```
or globally:

```
npm i -g pg-doc
```

# Usage

```
Usage: pg-doc [options]

Options:
  --version               Show version number                          [boolean]
  --connection, --db      Database Connection URL                       [string]
  --out, -o               The file name of the output                   [string]
  --title, -t             The title of the document                     [string]
  --excluded, --ex        Tables to be excluded                          [array]
  --toc                   Add a table of contents (TOC) section
                                                       [boolean] [default: true]
  --split-by-initial, -s  Split TOC by initial letter [boolean] [default: false]
  --split-limit, --sl     Split TOC only if number of tables is greater that
                          this limit                      [number] [default: 20]
  --help                  Show help                                    [boolean]
```

# Configuration
  
There are 3 different ways to pass configuration options

## Options file
You can put your options in a `.pg-doc.json` file in your project:

```
{
    "connection": <postgres connection url>,
    "excluded": <string array>,
    "toc": <boolean>,
    "splitByInitial": <boolean>,
    "splitLimit": <number>,
    "title": <string>,
    "out": <filename>
}
```

## Environment variables
Use the following variables to pass options to `pg-doc`:
```
PGDOC_CONNECTION=<postgres connection url> 
PGDOC_OUT=<filename>
PGDOC_TITLE=<string>
PGDOC_EXCLUDED=<comma separated strings>
PGDOC_SPLIT_LIMIT=<number>
PGDOC_SPLIT_BY_INITIAL=<boolean>
```
## Precedence
Configuration options are applied in the following order (from lowest to highest precedence):

`.pg-doc.json --> env variables --> command line options`

