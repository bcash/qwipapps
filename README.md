# qwipapps

Official Apps Directory for QWIP framework.  The directory is a set of JSON files that live in a set of 
categorizing folders.

The last folder in a tree will contain the project JSON file.  The app file format is inspired by the 
composer json format.  The base name of the file is not important, but the file must have a .json extension.

## Properties

### name

The name of the app. It consists of vendor name and app name, separated by /.

Examples:

bcash/template
alpine/events

Required for published apps.

### description

A short description of the app. Usually this is just one line long.

Required for published apps.

### version

The version of the app. In most cases this is not required and should
be omitted (see below).

This must follow the format of `X.Y.Z` or `vX.Y.Z` with an optional suffix
of `-dev`, `-patch`, `-alpha`, `-beta` or `-RC`. The patch, alpha, beta and
RC suffixes can also be followed by a number.

Examples:

    1.0.0
    1.0.2
    1.1.0
    0.2.5
    1.0.0-dev
    1.0.0-alpha3
    1.0.0-beta2
    1.0.0-RC5

Optional if the app repository can infer the version from somewhere, such
as the VCS tag name in the VCS repository. In that case it is also recommended
to omit it.

> **Note:** Packagist uses VCS repositories, so the statement above is very
> much true for Packagist as well. Specifying the version yourself will
> most likely end up creating problems at some point due to human error.

### keywords

An array of keywords that the package is related to. These can be used for
searching and filtering.

Examples:

    logging
    events
    database
    redis
    templating

Optional.

### homepage

An URL to the website of the project.

Optional.

### time

Release date of the version.

Must be in `YYYY-MM-DD` or `YYYY-MM-DD HH:MM:SS` format.

Optional.

### license

The license of the app. This can be either a string or an array of strings.

The recommended notation for the most common licenses is (alphabetical):

    Apache-2.0
    BSD-2-Clause
    BSD-3-Clause
    BSD-4-Clause
    GPL-2.0
    GPL-2.0+
    GPL-3.0
    GPL-3.0+
    LGPL-2.1
    LGPL-2.1+
    LGPL-3.0
    LGPL-3.0+
    MIT

Optional, but it is highly recommended to supply this. More identifiers are
listed at the [SPDX Open Source License Registry](http://www.spdx.org/licenses/).

For closed-source software, you may use `"proprietary"` as the license identifier.

An Example:

    {
        "license": "MIT"
    }


For a app, when there is a choice between licenses ("disjunctive license"),
multiple can be specified as array.

An Example for disjunctive licenses:

    {
        "license": [
           "LGPL-2.1",
           "GPL-3.0+"
        ]
    }

Alternatively they can be separated with "or" and enclosed in parenthesis;

    {
        "license": "(LGPL-2.1 or GPL-3.0+)"
    }

Similarly when multiple licenses need to be applied ("conjunctive license"),
they should be separated with "and" and enclosed in parenthesis.

### authors

The authors of the app. This is an array of objects.

Each author object can have following properties:

* **name:** The author's name. Usually his real name.
* **email:** The author's email address.
* **homepage:** An URL to the author's website.
* **role:** The authors' role in the project (e.g. developer or translator)

An example:

    {
        "authors": [
            {
                "name": "Nils Adermann",
                "email": "naderman@naderman.de",
                "homepage": "http://www.naderman.de",
                "role": "Developer"
            },
            {
                "name": "Jordi Boggiano",
                "email": "j.boggiano@seld.be",
                "homepage": "http://seld.be",
                "role": "Developer"
            }
        ]
    }

Optional, but highly recommended.

### support

Various information to get support about the project.

Support information includes the following:

* **email:** Email address for support.
* **issues:** URL to the Issue Tracker.
* **forum:** URL to the Forum.
* **wiki:** URL to the Wiki.
* **irc:** IRC channel for support, as irc://server/channel.
* **source:** URL to browse or download the sources.

An example:

    {
        "support": {
            "email": "support@example.org",
            "irc": "irc://irc.freenode.org/composer"
        }
    }

Optional.

#### require

Lists apps required by this app. The app will not be installed
unless those requirements can be met.
