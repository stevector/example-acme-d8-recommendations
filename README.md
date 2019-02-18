# Example Agency Drupal Recommendations

This repo is an example of how a web development agency (or any team managing many Drupal websites) can use a stand-alone Composer package containing just a `composer.json` to list all of the modules (and themes and other packages) that they want to use on all D8 projects.

The Composer file in this project contains this section:

```json
    "require": {
        "drupal/field_group": "^1.0@RC",
        "drupal/pathauto": "^1.0"
    }
    "repositories": [
        {
            "type": "composer",
            "url": "https://packages.drupal.org/8"
        }
    ],
```

This layer of abstraction allows the list of default modules to be maintained in one place. Instead of all of your projects having a (nearly) identical list of dozens of modules you will be able to more easily distinguish modules added because they are always used against modules added for site-specific needs.

This technique does not have as much complexity and mental load as a [Drupal Installation Profile/Distribution](https://www.drupal.org/docs/8/creating-distributions) or [Pantheon's Custom Upstreams](https://pantheon.io/upstreams). Those abstractions will bring more or different baggage and implications for how you manage configuration and git. This technique is simply a way of reducing the number of root requirements listed in a site-specific `composer.json`.

## Using a package like this one in your real projects

To use this idea in for your real projects with your real agency, make a copy of this repo and set the `require` section of `composer.json` to include the modules you actually want.
