---
title: Best Practices for Using R Securely
author: R Consortium
date: '2015-08-17'
categories:
  - Blog
slug: best-practices-for-using-r-securely
---

[vc_row type="in_container" full_screen_row_position="middle" scene_position="center" text_color="dark" text_align="left" overlay_strength="0.3"][vc_column column_padding="no-extra-padding" column_padding_position="all" background_color_opacity="1" background_hover_color_opacity="1" width="1/1" tablet_text_alignment="default" phone_text_alignment="default"][vc_column_text]The R Consortium was formed to serve the interests of the R user community, and to that end the members of the R Consortium would like to share some best practices for using R securely and safely. These recommendations are not unique to R: you should follow similar practices for any software you download from the Internet.

If you download R (or R packages) using an unencrypted Internet connection, there is a possibility that a malicious actor could modify the code in transit (or substitute their own file), if they have access to the connection linking you and the CRAN server delivering the code. (This is possible, for example, when you download R using an unsecured Wi-Fi network.) This could potentially give an attacker the same rights you have to execute code on your system.

To eliminate the possibility of such an attack, the R Consortium recommends all R users to always download R and R packages using an encrypted HTTPS connection from a secure server. This document describes steps you can take to configure your existing or new R installations to adhere to best practices for secure R use.

**1. Always download R installers from a CRAN server using HTTPS**

Every time you download R, make sure you are connected to the download site using a secure HTTPS connection. Check that the URL of the web page you are using to download R begins with "https://" (_not_ "http://") and that your browser reports the site to be secure. (Here are some ways you can check: <http://info.ssl.com/article.aspx?id=10068>.)

If you are downloading R from CRAN, the following CRAN mirrors support HTTPS and we recommend using one of them:

  * CRAN master (Austria): <https://cran.r-project.org/>

  * RStudio (USA): <https://cran.rstudio.com/>

  * Revolution Analytics (USA): <https://cran.revolutionanalytics.com/>

  * China (Beijing) : <https://mirrors.tuna.tsinghua.edu.cn/CRAN/>

  * China (Hefei) : <https://mirrors.ustc.edu.cn/CRAN/>

  * Columbia (Cali) : <https://www.icesi.edu.co/CRAN/>

  * France: <https://mirror.ibcp.fr/pub/CRAN/>

  * Russia: <https://cran.gis-lab.info/>

  * Switzerland: <https://stat.ethz.ch/CRAN/>

  * UK (Bristol): <https://www.stats.bris.ac.uk/R/>

  * UK (EMBL-EBI): <https://mirrors.ebi.ac.uk/CRAN/>

  * USA (Berkeley): [https://cran.cnr.Berkeley.edu/](https://cran.cnr.berkeley.edu/)

  * USA (KS): <https://rweb.quant.ku.edu/cran/>

  * USA (MI): <https://cran.mtu.edu/>

  * USA (TN): <https://mirrors.nics.utk.edu/cran/>

  * USA (WA): <https://cran.fhcrc.org/>

The above list is complete as of August 12, 2015. Check the [list of CRAN Mirrors](https://cran.r-project.org/mirrors.html) for other HTTPS mirrors added since then.

**2. Check the MD5 checksums of R before you begin the installation.**

When you download R, the same webpage should also provide the "md5 checksum" for the installation. (It will be a long string of letters and digits. Here's an example — but remember, it will be different for every version of R: 9578948a99ee6b74ff10b71b0891b94c.) After you download the file to install R, you should generate another md5 checksum for the file you downloaded, and make sure it matches the checksum provided on the download site. (Here are instructions for doing so on [Windows](http://support.microsoft.com/kb/889768), [Linux](http://askubuntu.com/questions/61826/how-do-i-check-the-sha1-hash-of-a-file), and [Mac OS X](https://support.apple.com/en-us/HT201259)). If the checksums do not match, do not install R using that file.

**3. Configure R for secure file downloads**

When downloading files over the Internet (including R packages), R must be configured such that a secure, HTTPS-enabled web server may be used.  To configure R appropriately, add code to your .Rprofile or Rprofile.site file. The instructions vary depending on the version of R and operating system you use. Note that this is the default configuration for R 3.2.2, so **you do not need to take any action for R 3.2.2 or any later version of R**.

**R 3.2.0 and R 3.2.1**

_Windows_:

options(download.file.method = "wininet")

_OS X and Linux_:

options(download.file.method = "libcurl")

**R 3.1 and earlier**

_Windows_:

utils::setInternet2(TRUE)

options(download.file.method = "internal")

_OS X_:

options(download.file.method = "curl")

_Linux_:

options(download.file.method = "wget")

**4. Always download CRAN packages from a secure mirror**

The same cautions apply to R packages. Always make sure you are using a CRAN mirror that supports HTTPS, such as one from the list given in point 1 above.

To configure R to automatically use a secure mirror, add the following code to your .Rprofile or Rprofile.site file, using the mirror of your choice (beginning with "https://") in the first line.

securemirror <- "<https://cran.r-project.org/>"

local({

r <- getOption("repos");

r["CRAN"] <- securemirror

options(repos=r)

})

Note that you do not need to check md5 sums for packages: R automatically checks md5 checksums before it installs any package.

**Summary**

With these simple steps, you can eliminate one vector of attack for a malicious actor who can intercept your communications. The R Consortium recommends all R users follow this practice.[/vc_column_text][/vc_column][/vc_row]
