---
title: RL10N hits its first milestone
author: B Preston
date: '2016-11-22'
categories:
  - Blog
slug: rl10n-hits-its-first-milestone
---

by Richard Cotton and Thomas Leeper

![richie_logo](https://www.r-consortium.org/wp-content/uploads/sites/13/2016/11/Richie_logo-232x300.png)

R is gradually taking over the world (of data analysis).  However, proficiency in English remains a prerequisite for effectively working with R.  While R has a system for translating messages, warnings, and error messages into other languages, very few packages take advantage of this functionality.

Part of the problem is that it currently takes a lot of effort to create translations.  There are a few issues that the RL10N project aims to address. Firstly, the functionality contained in the tools package isn't particularly easy to work with. Secondly, finding translators can be difficult. RL10N aims to solve both of these problems.

The project has reached its first milestone, having released the **[ poio](https://cran.r-project.org/web/packages/poio/index.html)** package to CRAN. Translations of messages are stored in .pot master translation and .po language-specific translation files that are understood by the GNU gettext utility. **poio** provides functionality to read and write this file format.

### Setting up Translations

The workflow to create translation infrastructure for a package is now reasonably straightforward.

First, a .pot master translation file is created using the xgettext2pot from the **tools** package. The .pot file contains a few lines of metadata, consisting of name-value pairs.
`
"Project-Id-Version: R 3.3.1\n"
"Report-Msgid-Bugs-To: bugs.r-project.org\n"
"POT-Creation-Date: 2016-11-06 17:19\n"
...
`
After this, it contains message ID lines, along with blank message translation lines.
`
msgid "This is a message!"
msgstr ""
`
The second step is to read this file into R, using poio's read_po function.  (The same function reads both .po and .pot files, automatically detecting which is which.)
`
pot <- read_po(pot_file)`
The file created by x has some incorrect metadata values.  These can be fixed by calling fix_metadata.
`
pot_fixed <- fix_metadata(pot)`
Next, you need to choose some languages to translate your messages into.  You need to specify the languages as a two- or three-letter ISO 639 code.  These include "fr" for French, "zn" for Chinese, and country-specific variations like "pt_BR" for Brazilian Portuguese.  The language_codes dataset shows all the available language and country codes.

For each language, you must generate a language-specific po object from the master translation, using generate_po_from_pot, then write it to a .po file using write_po.
`
for(lang in c("de", "fr_BE"))
{
po <- generate_po_from_pot(pot, lang)
write_po(po)
}
`
That's it! You are now ready to translate.

### Next Steps

The **msgtools** package is currently under development, and has higher level tools for managing and updating translations, and integrating translations into packages.  The immediate next step is to integrate **poio** with **msgtools** and release the latter package to CRAN.

Beyond this, the RL10N project has a plan to tackle the second problem: finding translators.  This will involve integrating automated translation functionality from Google Translate and Microsoft Translator into **msgtools**, as well as providing assistance with getting human translators.
