# Feed Validator

This is a command-line focused fork for of the W3C's [Feed Validator](https://validator.w3.org/feed/) for validating RSS and and Atom feeds.

This validator is written in Python 2 and runs using Docker.

## Building

To build:

```sh
docker build -t feedvalidator .
```

## Validating a URL

To validate a remote URL, provide it as an argument to the image:

```sh
docker run --rm feedvalidator https://www.example.net/rss.xml
```

## Validating a local file

To validate a local file, mount the file as a volume and use that file path:

```sh
docker run --rm --read-only -v $(pwd):/dat feedvalidator /dat/atom.xml
```

## Configuring validation levels

The validtor supports basic, strict and experimental validation determined by the second argument:

| Argument     | Meaning |
| ------------ | ------- |
| A            | The most basic level |
| AA (default) | Mimics online validator |
| AAA          | Experimental; these rules WILL change or disappear in future versions |

## Caveat

This a quick-and-dirty fork; there's probably plenty in this repo that doesn't need to be here.