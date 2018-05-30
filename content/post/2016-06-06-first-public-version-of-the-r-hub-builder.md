---
title: First Public Version of the r-hub Builder
author: R Consortium
date: '2016-06-06'
categories:
  - Blog
slug: first-public-version-of-the-r-hub-builder
---

[vc_row type="in_container" full_screen_row_position="middle" scene_position="center" text_color="dark" text_align="left" overlay_strength="0.3"][vc_column column_padding="no-extra-padding" column_padding_position="all" background_color_opacity="1" background_hover_color_opacity="1" width="1/1" tablet_text_alignment="default" phone_text_alignment="default"][vc_column_text]

The r-hub builder is the first major project of the [R consortium](https://www.r-consortium.org/). It is an R package build and continuous integration service, open to all members of the R community.

Goals for R-Hub include:

  * simplify the R package development process: creating a package, building binaries and continuous integration, publishing, distributing and maintaining it;

  * encourage community contributions; and

  * pre-test CRAN package submissions to ease burden on CRAN maintainers.

### What's available

  * Linux builders for uploaded R source packages. You can watch the package check process in real time. Currently Debian and Fedora builders are available. Builds are performed in Docker containers, and new builders can be added easily.

  * Automatic detection of system requirements. We built a system requirements database that allows us to automatically install system software needed for R packages. Note that the database needs constant improvements, and if it fails for your R package, please let us know. See below.

  * Flexible package dependencies. You don't need to have all your package dependencies on CRAN in order to use r-hub. We support `devtools`-style`Remotes` fields in `DESCRIPTION`, so you can depend on GitHub, BitBucket, etc. packages. See more about this at <https://cran.r-project.org/web/packages/devtools/vignettes/dependencies.html>

Go to <https://builder.r-hub.io> to try the r-hub builder!

### What's coming?

Mostly everything else that was promised in the [proposal](https://github.com/r-hub/proposal#readme) The two major features that are coming soon are

  * Windows builds, and

  * The r-hub CI. You'll be able to trigger builds from your GitHub repositories.

### You can help

  * Please try and run the builder on your R package, and report failures at <https://github.com/r-hub/feedback/issues> or by emailing `support@r-hub.io`.

  * If your package does not build because of a non-detected system requirement, please let us know at <https://github.com/r-hub/sysreqsdb/issues>

  * The code for r-hub itself is open source and available at [GitHub](https://github.com/r-hub). Your contributions are welcome!

## About the author of this post

## Gábor Csárdi

Gábor Csárdi, Ph.D., is Principal Consultant at Mango Solutions, and has been an R programmer for 14 years. He enjoys solving mathematical and programming problems and building systems and services.

![](https://www.r-consortium.org/sites/cpstandard/files/styles/thumbnail/public/authors/gabor-csardi.jpg?itok=ziKd7Vtx)

[/vc_column_text][/vc_column][/vc_row]
