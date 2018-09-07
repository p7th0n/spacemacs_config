# Spacemacs on Windows 10

## Why

* [Org-mode](https://orgmode.org/)

> Org mode is for keeping notes, maintaining TODO lists, planning projects, and authoring documents with a fast and effective plain-text system.

    * Played with org-mode plugins for [Vim](https://github.com/jceb/vim-orgmode) and [VSCode](https://github.com/ajtoo/vscode-org-mode)
    * Using Markdown for most writing.  Similarities to Org-mode.
    * [Agenda](https://orgmode.org/guide/Agenda-Views.html)
* [Magit](https://magit.vc/)

> Magit is an interface to the version control system Git, implemented as an Emacs package. Magit aspires to be a complete Git porcelain. While we cannot (yet) claim that Magit wraps and improves upon each and every Git command, it is complete enough to allow even experienced Git users to perform almost all of their daily version control tasks directly from within Emacs. While many fine Git clients exist, only Magit and Git itself deserve to be called porcelains.

    * [What does the term “porcelain” mean in Git?](https://stackoverflow.com/questions/6976473/what-does-the-term-porcelain-mean-in-git)

> "Porcelain" is the material from which toilets are usually made (and sometimes other fixtures such as washbasins). This is distinct from "plumbing" (the actual pipes and drains), where the porcelain provides a more user-friendly interface to the plumbing.
>
> Git uses this terminology in analogy, to separate the low-level commands that users don't usually need to use directly (the "plumbing") from the more user-friendly high level commands (the "porcelain").
>

## Cloning Spacemacs

* See [Spacemacs -- Github](https://github.com/syl20bnr/spacemacs#install) for installation and other documentation.

```bash

git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d

```

## Installing Emacs

* C:\usr\local\emacs-26.1.xx
* ~\Appdata\roaming\emacs-26.1.xx -- [Guidelines for roaming app data](https://msdn.microsoft.com/en-us/library/windows/apps/hh465094.aspx)
* set user PATH=%PATH%;EMACS_BIN_DIR

## org-protocol

* TODO Registry
* Browser plugins
    * Quirks
    * New style protocol [Warning (emacs): Please update your org protocol handler to deal with new-style links. ](https://github.com/alphapapa/org-protocol-capture-html/issues/14), [org-protocol-capture...](https://github.com/alphapapa/org-protocol-capture-html)

[Version 9.0 notes](https://orgmode.org/Changes_old.html)

> New org-protocol key=value syntax
>
> Org-protocol can now handle query-style parameters such as:
>
> org-protocol://store-link?url=http:%2F%2Flocalhost%2Findex.html&title=The%20title
> org-protocol://capture?template=x&title=Hello&body=World&url=http:%2F%2Fexample.com
> Old-style links such as
>
> org-protocol://store-link:/http:%2F%2Flocalhost%2Findex.html/The%20title
>
> continue to be supported.
>
> If you have defined your own handler functions for org-protocol-protocol-alist, change them to accept either a property list (for new-style links) or a string (for old-style links). Use org-protocol-parse-parameters to convert old-style links into property lists.
>

* Capture templates

```lisp

(setq org-capture-templates '(

    ;; Web capture with selected text.
        ("w" "Web" entry (file+headline org-default-notes-file "web")
        "* %? [[%:link][%:description]]:WEB:\n:PROPERTIES:\n:SOURCE:[%:link] \n:CAPTURED_ON: %U\n:END:\n#+BEGIN_QUOTE\n%i\n#+END_QUOTE\n")

    ;; Web capture with URL and webpage title.
        ("L" "Link" entry (file+headline org-default-notes-file "link")
        "* %? [[%:link][%:description]]:LINK:\n:PROPERTIES:\n:CAPTURED_ON: %U\n:END:\n")

    ;; TODO entry
        ("t" "todo" entry (file+headline org-default-notes-file "task")
        "* TODO %?\n:PROPERTIES:\n%U\n%a\n:END:\n")

    ;; Meeting entry
        ("m" "meeting" entry (file+headline org-default-notes-file "meeting")
        "* MEETING with %? :MEETING:\n:PROPERTIES:\n%U\n:END:\n") 

    ;; Idea entry
        ("i" "idea" entry (file+headline org-default-notes-file "idea")
        "* %? :IDEA:\n:PROPERTIES:\n%U\n%a\n:END:\n") 

    ;; Note entry
        ("n" "note" entry (file+headline org-default-notes-file "note")
        "* %? :NOTE:\n:PROPERTIES:\n%U\n%a\n:END:\n")
))

```

## File locations

* TODO Why Dropbox

> Dropbox is available cross platform including Windows, Mac, Linux, iOS and Android. Because Org files are plain text, the files open with any available text editor. There are also mobile apps to manage Org files.
* Webdav

## Web browser extensions

* [Org Capture Extension - Github](https://github.com/sprig/org-capture-extension)
* [Org Capture - Chrome](https://chrome.google.com/webstore/detail/org-capture/kkkjlfejijcjgjllecmnejhogpbcigdc)
* [Org Captrue - Firefox](https://addons.mozilla.org/en-US/firefox/addon/org-capture/)

## Mobile

* [Beorg](https://beorgapp.com/)

> beorg works with org files which were designed for the amazingly powerful Org mode. Here is an example of a file created by beorg:

```lisp
* IN-PROGRESS Move my task management over to beorg and plain text
** DONE Check out beorg website
SCHEDULED: <2018-06-18>
https://beorgapp.com
** TODO Download beorg from the App Store
SCHEDULED: <2018-06-19>
** TODO Get an Org plugin for my favourite editor
SCHEDULED: <2018-06-20>
```

* [MobileOrg](https://mobileorg.github.io/)

> MobileOrg uses a WebDAV server or Dropbox to interact with your Org files. It downloads Org files from the server and uploads captured notes to a mobileorg.org file on the same server. The documentation below covers how to get started using Dropbox or set up a WebDAV account (using free services or your own server), how to download and finally browse Org files stored on your device.