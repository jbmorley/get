Get
===

Description
-----------

Get is a simple script for fetching and updating a collection of git repositories and adding them to your path. It is intended for use in build scripts to ensure you always have the latest version of your toolchain when running builds.

Get should work equally well on Linux and OS X systems but has only been tested on OS X.

Usage
-----

Using get is simply a matter of adding something like the following line to the beginning of your build script.

    $( curl https://raw.github.com/jbmorley/get/master/get-min | python - <profile> )

Profiles specify the repositories to add to your path. They can be provided inline, or as a local or remote path (see below).

If you plan to use get as part of a Hudson or Jenkins build system, don't forget to explicitly source your .bash_profile (or equivalent) to ensure all your other tools are on the path.

    source ~/.bash_profile
    $( curl https://raw.github.com/jbmorley/get/master/get-min | python - <profile> )

Profiles
--------

Profiles are specified as a JSON mapping of repository name to path:

    {
      "neko": "git@github.com:jbmorley/neko.git",
      "mnfy": "git@github.com:brettcannon/mnfy.git"
    }

Get supports inline, local and remote paths for profiles.

### Inline

    $( curl https://raw.github.com/jbmorley/get/master/get-min | python - '{ "neko": "git@github.com:jbmorley/neko.git" }' )

### Local

    $( curl https://raw.github.com/jbmorley/get/master/get-min | python - profile.json )

### Remote