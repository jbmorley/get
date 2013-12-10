Get
===

Description
-----------

Get is a simple script for fetching and updating a collection of git repositories and adding them to your path. It is intended for use in build scripts to ensure you always have the latest version of your toolchain when running builds.

Get should work equally well on Linux and OS X systems but has only been tested on OS X.

Usage
-----

Using get is simply a matter of adding the following line to 

    $( curl -fsSL http://projects.jbmorley.co.uk/toolchain/get | python )

If you plan to use get as part of a Hudson or Jenkins build system, don't forget to explicitly source your .bash_profile (or equivalent) to ensure all your other tools are on the path. e.g.

    source ~/.bash_profile
    $( curl -fsSL http://projects.jbmorley.co.uk/toolchain/get | python )

Specifications
--------------

