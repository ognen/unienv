# unienv

The aim of this project is to simplify the development environment setup for projects that span across multiple
development environemnts (ruby, android, ios, etc...). The typical case for such projects are mobile hybrid projects
thta span accross JS, iOS, android SDKs.

`unienv` doesn't replace existing *env developer environment managers but rather it delegates to them and uses 
their configuration files (.ruby-version, etc.). The task of `unienv` is to insulate a developer from 
the intricacies of all the development environments involved in a source tree and letting them focus only on the 
issues they are an expert on.

# Deveolpment Environment Initialization

A developer using `unienv` has only to:

    $ # install unienv by downloading & executing a script 
    $ git clone http://example.com/project.git
    $ unienv

To get this environment ready. This will, for example:

* if there's a `.ruby-version` file:
  * setup `rbenv` if not already present
  * install the correct ruby version if not present 
* if there's a `Gemfile` file:
  * install bundler if not present
  * run `bundle`
* ...
* same for Java using `jenv`
* same for Node using `nenv`
* same for Python using `pyenv` 
* same for Andorid using the andoid tools sdk
* same for iOS using `carthage` and `cocoapods`
 
# Typical Project Source Tree

A typical project source tree doesn't exibit any trait of using `unienv`. Intead it hosts files that target the
various platforms:

```
 app/
 native/ios
 native/android
 doc/
 .ruby-version                                    # because of cocoapods
 .java-version                                    # android
 .android-level                                   # android API level
 .node-version                                    # for JS
 ```
