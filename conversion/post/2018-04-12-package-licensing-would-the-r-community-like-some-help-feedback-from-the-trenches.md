---
title: 'Package Licensing: Would the R Community like some help? Feedback from the
  trenches'
author: John Mertic
date: '2018-04-12'
categories:
  - Blog
  - R Consortium Project
slug: package-licensing-would-the-r-community-like-some-help-feedback-from-the-trenches
---

_Editor's Note: This post comes from [Mark Hornick](https://twitter.com/@MarkHornick), who leads the [Code Coverage WG](https://wiki.r-consortium.org/view/Code_Coverage_Tool_for_R) and serves on the [Board of Directors](https://www.r-consortium.org/about/governance). _

In the Fall of 2017, the R Consortium surveyed the R Community to understand opportunities, concerns, and issues facing the community. Taking into account that feedback, the R Consortium recently surveyed package authors and maintainers on a number of topics surrounding R package licensing. Questions revolved around motivations for choice of license, comfort level in understanding license meaning and implications, importance of corporate adoption of R, and whether guidance on licensing from the R Consortium would be valuable.

While there are a significant number of people in the R community who respond they understand and intentionally choose the license(s) they apply to their package software, a much larger group are unclear about which license to choose and what the implications of that choice are. These implications affect not only the individual package, but the R Community and corporate, government, and academic users of those packages as well.  Of roughly 7400 invitations to complete the survey, the R Consortium received more than 1100 responses – a response rate over 14%.

In this blog post, we summarize that feedback and offer next steps that the R Consortium and R Community may take based on this feedback.

**Who responded to the survey**

Of respondents, 42% are relatively new to R package development with 3 or fewer years of experience, 31% have 4-6 years, and 27% have more than 7 years of experience. As the following table shows, the majority of package authors have been working with R for less than 6 years and writing up to 5 packages.

![](https://www.r-consortium.org/wp-content/uploads/sites/13/2018/04/Picture1.png)

The largest subgroup of responders (44%) have produced one package over their career. However, 39% of responders have not pushed a package to CRAN over the past year.

![](https://www.r-consortium.org/wp-content/uploads/sites/13/2018/04/Picture2.png)

The most popular license used among respondents is 'GPL-3' at 35% with 'GPL-2 | GPL-3' a close second at 34%, 'GPL-2' next at 24%, and 'MIT' at 21%. However, there are a mix of other licenses cited, including LGPL, BSD, Apache2, and Creative Commons, among others.

**What do I want others to be able to do with my package?**

When it comes to open source software, there are many ways to think about how software could be used. For example, you may want everyone to be able to freely use your software by its API, but have concerns about what happens if the underlying code is modified – _derivative works_. On the other hand, you may want to impose licensing requirements on the software that uses your software as well, e.g., software that uses my package must be licensed in the same way as my package. The license choice can significantly affect how and whether a given package can be used in corporate, academic, or government environments.

From the survey, 60% of respondents want other software developers to be able to use their package(s) without imposing license requirements on the software that uses their package (via API), with only 15% disagreeing.

The majority of respondents were neutral as to whether they wanted to ensure that software using their package(s) must apply the same license that they chose, with 29% agreeing and 19% disagreeing.

As expected, respondents want to ensure that derivative works of their package(s) remain open source, with 74% agreeing. However, only 25% agree that derivative works should require the same license as the package used.

**How do you choose a license for your package?**

In the survey, we asked which factors contribute to the choice of package license.  Sixteen percent of respondents indicated license choice defaulted to the license of dependent packages, whether used exclusively through their API or if they borrowed code or header definitions. A sizeable 65% indicate that it is a conscious choice based on their understanding of open source and other license terms. But this is tempered by responses described in the next section regarding comfort level with understanding open source licenses.

The open comments section for this question revealed more details, e.g., some respondents consult websites, blogs, and books for license recommendations, or get advice from package reviewers. Some respondents admit they haven't thought deeply about the choice of license and don't understand the differences between licenses since the choices and legalese can be overwhelming. Some use what other respected package authors have used (without necessarily understanding why a given license was chosen for such a package) or as determined by corporate or government dictates or requirements. Yet other respondents indicated making an arbitrary or random choice since R package submission requires that some license must be chosen.

The open comments also highlighted some potential misconceptions, such as if a package author chooses GPL-2 for their package, they are unable to change that to a more permissive license later. The ability to change a license depends on multiple factors, e.g., licenses of dependent packages or lifted code, whether all authors give their consent, etc. Some respondents state they want licensing that enables more users of their code rather than fewer. Others see GPL as a way to ensure commercial usage of their packages occurs fairly. Some respondents choose BSD as it provides most freedom to package users.

**Open Source License knowledge**

For the R Consortium to understand whether resources should be applied to the problem of licensing, we asked package developers about the level of understanding of open source licenses. While 12% outright stated they do not feel comfortable interpreting or applying open source licenses, 62% find license details and options confusing – even if they understand the basic premise of open source licenses.

Only 23% felt confident in choosing the right open source license(s) for their packages, while about 1% claim to have access to Legal Counsel to guide their choice of open source licenses. Another 1% claim to have sufficient legal background to choose the appropriate licenses(s) for their packages.

While licensing is important when trying to use software in corporate settings, only 24% of respondents consider the license of an R package important in determining whether or not they use it – 35% are neutral and 40% don't think it's important.

A majority (56%) of respondents believe that corporate adoption of R technology (engine and packages) is important for the R Community – 36% are neutral while 8% feel corporate adoption is not important. Consistent with this, 56% of respondents feel the R ecosystem should make it easy for corporate use of R – 37% are neutral and 6% disagreeing.

**Tools and Guidance**

As open source communities and technology continues to evolve, there are more tools available to assist with license choice. For example, code scanning tools exist in other open source communities to identify potential licensing issues. While following the advice of such tools is optional, most if not all developers want to "do the right thing" with respect to licensing. Testament to this is that over 71% of respondents indicated they would welcome the availability of a license scanning tool to flag package license issues – only 3% disagreed.

With the objective to enable package developers to make an informed choice of license, respondents were asked if they would like the R Consortium to provide guidance on open source license choices and implications. Over 89% indicated they would. One respondent put it best "I want whatever is best for making sure the CRAN community thrives in the long-term." This is the intent of the R Consortium as well.

The R Consortium thanks the respondents to this survey for taking the time to share their experience, concerns, and needs. As a next step, the R Consortium will work with the R Community to provide best practices for good "license hygiene." If you would like to be part of this activity, please reach out to the R Consortium by responding to this post.
