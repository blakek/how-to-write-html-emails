# Email Template Overview
> A guide helping everyone get what is needed from the client, designer, and developer when making an HTML email.

Emails are one of the most [over-]used forms of communication, and the technology and standards that make them work is archaic. Creating a good email is _nothing_ like making a good web page. This guide is aimed at helping everyone involved in creating emails get the best results possible with the fewest number of surprises possible. This guide is a non-exhaustive list of necessary information from the client, realistic expectations from HTML emails, best practices in designing emails, and unanticipated gotchas for developers.


#### Contents:

* [Information for Account Managers and Project Managers](#information-for-account-managers-and-project-managers)
  - [Required Information Before Design and Dev Can Begin](#required-information-before-design-and-dev-can-begin)
  - [Optional Information and Extra Tricks](#optional-information-and-extra-tricks)
  - [Email systems we commonly use](#email-systems-we-commonly-use)
* [Design Best Practices](#design-best-practices)
* [Development Tips and Best Practices](#development-tips-and-best-practices)
  - [General tips, tricks, and gotchas](#general-tips-tricks-and-gotchas)
  - [Responsive Emails and Issues for Mobile Clients](#responsive-emails-and-issues-for-mobile-clients)
* [Stuff to Add](#stuff-to-add)


## Information for Account Managers and Project Managers

### Required Information Before Design and Dev Can Begin

* What is the subject of the email? Please provide this explicitly with the body text.
* There will be links in the email. Please provide where the links are expected to go (i.e. the complete URL) along with the copy text.
* Who is will need to review the email before it is sent? Please provide the names and email addresses of everyone that will be involved.
* Is this an email template or a one-off email? These are developed differently, so please let the developer know.
* Who will be sending the email? Our firm, or another?
  - If __another firm__ is sending:
    * Who will be hosting the images for the email? If we are, we will need to know - otherwise, no images in the email will show.
    * Who will add the unsubscribe links?
    * What service is the other firm using to send the email? This is not always required, but it **is** required if we are to add an unsubscribe link or if we are delivering a reusable template (as opposed to a one-off email).


### Optional Information and Extra Tricks

It is possible to have text that is shown in the email list preview area, but is hidden in the email itself. The text in the preview area could be a way of generating interest (and email opens) from the end users. It can also get a key idea across in a content-heavy email. If this is desired, please let the dev team know. Remember, this needs to be very short!

#### Example
![example of text only in preview area](./images/hidden-preview-text.png)

Will the email include any links to social accounts? If so, please let design and dev know:

* what social accounts are going to be used
* a list of links (i.e. the full URL) to the social accounts


### Email systems we commonly use:
* [Campain Monitor](https://www.campaignmonitor.com/)
* [MailChimp](http://mailchimp.com/)
* [Emma](https://myemma.com/login)



## Design Best Practices

What is the purpose of the email? Is it to get users to read the content, to buy something, or to join an event and/or subscription? [MailChimp][mc-layout-and-purpose] does a great job of describing the differences, but the takeaway is there are three main types of emails that should be designed with different purposes in mind:

* __Read Me__ emails encourage readers to learn more using the content within the mail. These need:
  - well written copy
  - fewer images
  - good/readable typography
  - an attention-grabbing "hook" in the leading sentences of the email
* __Buy Me__ emails try to encourage an action based on a product. These need:
  - interesting, focused, well-cropped images (e.g. product photos)
  - simple copy
  - easy-to-find links to product pages
  - an attention-grabbing "hook" - usually before each product
* __Join Me__ emails try to encourage another type of action - often to attend an event. These need:
  - very short, clear copy
  - specific details, e.g. an event date and location, should __always__ be prominently placed at the top of the message
  - the call-to-action should be easy to understand and easy to see

[According to][cm-max-width-2] [very reputable][cm-max-width] [email creators][mc-basics], emails should be **no more than 600-650 px wide**. While everyone at an agency may have a huge, high-pixel-density monitor, a vast majority of email users use a preview pane to read email, which is commonly only ~750-800px wide.

Typography should be limited to [standard system typefaces][mc-typography]. On a website, we can import fonts from e.g. Google, but, sadly, popular email clients such as Gmail, Outlook, and Yahoo! Mail **do not support web fonts** at all. If the client really wants a particular typeface used, an image of the text _can_ be used, but [several email clients][cm-image-blocking] block images by default. It's generally not a good idea to use images to show any key information.

> **NOTE:** remember that anyone with Microsoft Office installed will have the base font set supplied with Office.  While this is nice to take advantage of, it is still _highly_ recommended to test the design with a standard system font as a fallback.

As mentioned in the previous point about typography, images are [blocked by default][cm-image-blocking] on several, popular email clients. **It's generally not a good idea to use images to show any key information.**

While your list of fonts is limited, email clients have good support for things such as the line-height (vertial character spacing), letter-spacing (e.g. tracking, e.g. horizontal character spacing), word-spacing, etc.

Email client support for margins and general positioning is very poor. Where this has the biggest effect is text and images cannot overlap without putting copy inside "sliced" images.

#### Expected result (Apple Mail)
![correctly displayed margins](./images/negative-margin-apple-mail.jpg)

#### Most email clients (Gmail)
![incorrectly displayed margins](./images/negative-margin-gmail.jpg)

#### Links
There will be links to web pages in emails. Please explicitly tell the dev team what is expected to be a link.

Keep in mind that using a plain image as a link is not intuitive. Instead, use buttons as the primary calls to action that demands attention, and use links for everything else. Try to restrict using buttons to a couple key links and use links for everything else. If images must be used, please make sure they indicate to the user in some way they can be clicked on (e.g. using text in the image that says "view now &raquo;" tends to be better)

Also, keep in mind that, unlike a web page, there is almost no control over what looks "clickable" by using hover states. That means that there is no way of making a link darker/lighter when a user hovers over it, and there is little control over what the cursor looks like when hovering over a link.

A link to allow users to unsubscribe is **required** for all emails. Usually, this is an entire area below the footer. Please keep this section in mind during design. Other optional links that may also be in the unsubscribe area of the email include:

* "Edit your subscription" or "Email preferences" link
* A link to see the web version of the email
* Perhaps social links - they usually end up around this area



## Development Tips and Best Practices

What developers need to be aware of greatly overlaps what designers should be aware of. It is recommend you read over the [design best practices](#design-best-practices) section. As a brief recap:

* Emails should be **600-650px wide** due to the size of preview panes.
* Web fonts **cannot** be used due to the [low support from email clients][mc-typography]. Desktop Outlook even defaults to Times New Roman when it sees a web font reference. Use [standard system fonts][mc-typography].
* It's generally not a good idea to use images to show any key information because [several email clients][cm-image-blocking] block images by default.

In addition to the look and feel, differences and bugs in email clients are far worse and prolific than those found in web browsers. The following list is by no means comprehensive, and at best scratches the surface of what you should be aware of.

> **Please keep in mind**: Apple's email clients have by far the best support for almost everything you would normally use when making a webpage. That means testing your results on an iPhone on in Mail isn't the best idea because they will show you what you'd expect to see. Test in Gmail, and, if available, Outlook. If you have a Litmus subscription or something similar, that is by far the best way to test.




### General tips, tricks, and gotchas

**Several** CSS selectors and features are simply not supported on various email clients (e.g. even the element selector - such as `body { }` - is not supported in Outlook.com, Yahoo!, Gmail, or AOL).  In some cases (e.g. Outlook.com), support is getting WORSE (e.g. Outlook.com has recently dropped support for CSS margins and floats).

You can have hidden text that gets shown in the email list preview area, but isn't shown in the email itself.

Supposedly, margins are supported in Gmail, but I have never gotten it them work correctly -  especially negative margins.

Almost all styles should be inlined as several, very popular email clients do not read styles in a style tag. There are several tools for helping you do this, so use whatever works best for you. The exception to this rule would be styles in media queries.

It is possible to have text that is shown in the email list preview area, but is hidden in the email itself. The text in the preview area could be a way of generating interest (and email opens) from the end users. It can also get a key idea across in a content-heavy email. If this is desired, please let the dev team know. Remember, this needs to be very short!

#### Example
![example of text only in preview area](./images/hidden-preview-text.png)



### Responsive Emails and Issues for Mobile Clients

> Responsive emails are _possible_, but they require more planning. No popular desktop mail app supports media queries (except Apple Mail), but media queries tend to work well on native mobile email clients. The Gmail and Yahoo! Mail apps do NOT support media queries, but all Apple Mail clients, Android 2.2+ clients, and BlackBerry OS 6+ clients support media queries. Funnily enough, the Windows Phone 7.5 email client was the first Microsoft email client to support media queries, but support was dropped again in Windows Phone 8.

The minimum font size on some devices is 13px, but [you can override this][cm-min-font].

The contents of the `<title>` tag is important, as it shows in some client notifications (e.g. Android 4.4).

Media query styles should not be inlined (how would you do that, anyway??). There is no such thing as "mobile-first" in email development, so make everything work on desktop first, and then add extra styles for mobile devices that support it.



## Stuff to Add

  * you can optionally show content if you are in Outlook:
  ```html
  <!--[if mso]> shown only in Outlook <![endif]-->
  <!--[if !mso]> don't show in Outlook <![endif]-->
  ```
  * design and dev: prefer html buttons over images

[dev-cerberus-home]: http://tedgoas.github.io/Cerberus
[dev-cerberus-github]: https://github.com/TedGoas/Cerberus
[mc-basics]: http://templates.mailchimp.com/getting-started/html-email-basics/ "MailChimp Designer/Developer Reference"
[mc-typography]: http://templates.mailchimp.com/design/typography/ "MailChimp Typography Reference"
[mc-layout-and-purpose]: http://templates.mailchimp.com/design/layout-and-purpose/ "MailChimp Layout and Purpose"
[cm-min-font]: http://www.campaignmonitor.com/blog/how-to/2010/12/save-your-layout-by-overriding-the-minimum-font-size-on-the-iphone-and/
[cm-css]: https://www.campaignmonitor.com/css/
[cm-image-blocking]: https://www.campaignmonitor.com/dev-resources/will-it-work/image-blocking/
[cm-max-width]: https://www.campaignmonitor.com/blog/email-marketing/2005/04/maximum-width-for-html-emails/
[cm-max-width-2]: https://www.campaignmonitor.com/blog/email-marketing/2011/06/how-wide-are-html-email-designs-today/
