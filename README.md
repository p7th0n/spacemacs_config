# Spacemacs on Windows 10

## Why

* Org-mode
    * Played with org-mode plugins for Vim and VSCode
    * Using Markdown for most writing.  Similarities to Org-mode.
    * Agenda
* Magit

## Cloning Spacemacs

## Installing Emacs

* C:\usr\local\emacs-26.1.xx
* ~\Appdata\roaming\emacs-26.1.xx
* set user PATH=%PATH%;EMACS_BIN_DIR

## org-protocol

* TODO Registry
* Browser plugins
    * Quirks
    * New style protocol [Warning (emacs): Please update your org protocol handler to deal with new-style links. ](https://github.com/alphapapa/org-protocol-capture-html/issues/14), [org-protocol-capture...](https://github.com/alphapapa/org-protocol-capture-html)

[Version 9.0 notes](https://orgmode.org/Changes_old.html)
```

New org-protocol key=value syntax

Org-protocol can now handle query-style parameters such as:

org-protocol://store-link?url=http:%2F%2Flocalhost%2Findex.html&title=The%20title
org-protocol://capture?template=x&title=Hello&body=World&url=http:%2F%2Fexample.com
Old-style links such as

org-protocol://store-link:/http:%2F%2Flocalhost%2Findex.html/The%20title

continue to be supported.

If you have defined your own handler functions for org-protocol-protocol-alist, change them to accept either a property list (for new-style links) or a string (for old-style links). Use org-protocol-parse-parameters to convert old-style links into property lists.

```

* Capture templates

## File locations

* TODO Why Dropbox
* Webdav

## Mobile

* Beorg
* MobileOrg