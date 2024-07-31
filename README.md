# Add useful tags to Silverstripe Raygun logs

This is a purpose-built extension that adds several useful tags to error messages that are published to Raygun via the [silverstripe/silverstripe-raygun](https://github.com/silverstripe/silverstripe-raygun) extension.

The following tags are added:

- `env:live` (or `env:dev` / `env:test`)
- `php:8.2.x`
- `host:example.com`
- `framework:5.0.x`
- `ajax:false` (true if this is an AJAX request)
- `cli:false` (true if being run via the CLI)

The logging level is set to WARNING and above (debug & info is ignored, see [configuration](#configuration)).


## Requirements

- Silverstripe ^5.0
- A Raygun application and API key (see [configuration](#configuration))


## Usage

Simply install the module: `composer require springtimesoft/silverstripe-raygun-tags`


## Configuration

Add the `SS_RAYGUN_APP_KEY="xxxxxxxxx"` environment variable to your `.env` file.

Please refer to the original silverstripe/silverstripe-raygun [README](https://github.com/silverstripe/silverstripe-raygun) for further information on customising the Raygun extension.

To change the logging level of your application you can overrule the module's defaults by adding a custom yaml file like:

```yaml
---
Name: custom-raygun
After:
  - '#raygun-log-level'
Only:
  envorconstant: 'SS_RAYGUN_APP_KEY'
---

# Prevent Raygun from logging debug/info messages, which aren't considered errors
SilverStripe\Core\Injector\Injector:
  SilverStripe\Raygun\RaygunHandler:
    constructor:
      level: 100 # Monolog\Level::Debug
```

## Installation

```shell
composer require springtimesoft/silverstripe-raygun-tags
```
