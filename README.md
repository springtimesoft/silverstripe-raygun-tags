# Add useful tags to Silverstripe Raygun logs

This is a purpose-built extension that adds several useful tags to error messages that are published to Raygun via the [silverstripe/silverstripe-raygun](https://github.com/silverstripe/silverstripe-raygun) extension.

The following tags are added:

- `env:live` (or `env:dev` / `env:test`)
- `php:8.2.x`
- `host:example.com`
- `framework:5.0.x`
- `ajax:false` (true if this is an AJAX request)
- `cli:false` (true if being run via the CLI)


## Requirements

- Silverstripe ^4.0 || ^5.0
- A Raygun application and API key (see [configuration](#configuration))


## Usage

Simply install the module: `composer require axllent/silverstripe-raygun-tags`


## Configuration

Add the `SS_RAYGUN_APP_KEY="xxxxxxxxx"` environment variable to your `.env` file.

Please refer to the original silverstripe/silverstripe-raygun [README](https://github.com/silverstripe/silverstripe-raygun) for further information on customising the Raygun extension.


## Installation

```shell
composer require axllent/silverstripe-raygun-tags
```
