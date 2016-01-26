# Email Template Overview
> A guide helping everyone get what is needed from the client, designer, and
> developer when making an HTML email.

While emails are one of the most [over-]used forms of communication, the
technology and standards that make them work is archaic.  This guide is aimed at
helping everyone involved get the best results possible with the least stress
possible.  This guide is a (non-exhaustive) list of necessary information from
the client, realistic expectations from HTML emails, best practices in designing
emails, and unanticipated gotchas for developers.

Contents:

  * [Information for Account Managers](#)
    - [Information Needed from the Client Before Making an Email Template](#)
  * [Information Needed from the Client Before Making an Email Template](#)
  * [Design Best Practices](#)
  * [Development Tips and Best Practices](#)



## Information for Account Managers

### Information Needed from the Client Before Making an Email Template

  * Is this an email template or a one-off email?
  * What is the subject of the email? Please provide this explicitly to dev.
  * Who will be sending the email?
    - If __another firm__ is sending:
      * Who will be hosting the images for the email?
      * Who will add the unsubscribe links?
      * What service is the other firm using to send the email?  This is not always required, but it **is** required if we are to add an unsubscribe link or if we are delivering a reusable template (as opposed to a one-off email).



## Design Best Practices

  * [According to][cm-max-width-2] [very reputable][cm-max-width] [email creators][mc-basics], emails should be **no more than 600-650 px wide**.  While everyone at the agency may have a 5k monitor, a vast majority of email users use the preview pane to read email, which is commonly only ~750-800px wide.
  * Typography should be limited to [standard system typefaces][mc-typography].  On a website, we can import fonts from e.g. Google, but, sadly, popular email clients such as Gmail, Outlook, and Yahoo! Mail do not support web fonts at all.
    - NOTE: remember that anyone with Microsoft Office installed will have the base font set supplied with Office.  While this is nice to take advantage of, it is still recommended to test the design with a standard system font as a fallback.
  * While your list of fonts is limited, email clients have good support for things such as the line-height (vertial character spacing), letter-spacing (e.g. tracking, e.g. horizontal character spacing), word-spacing, etc.
  * Email client support for margins and general positioning is very poor.  Where this has the biggest effect is text and images cannot overlap without just "slicing" an image.
  ![](http://dev.gsandf.com/how-to-articles/assets/email-guide/images/negative-margin-apple-mail.png) ![](http://dev.gsandf.com/how-to-articles/assets/email-guide/images/negative-margin-gmail.png)


## Development Tips and Best Practices




## Stuff to Add

  * the contents of the `<title>` tag is important, as it shows in some email notifications (e.g. in Android 4.4)
  * web fonts? forget about it. Desktop Outlook even defaults to Times New Roman when it sees a web font reference. use system fonts (list here)
  * luckily, you can optionally show content if you are in Outlook:
  ```html
  <!--[if mso]> shown only in Outlook <![endif]-->
  <!--[if !mso]> don't show in Outlook <![endif]-->
  ```
  * several CSS selectors and features are simply not supported on various email clients (e.g. even the element selector - such as `body { }` - is not supported in Outlook.com, Yahoo!, Gmail, or AOL).  In some cases (e.g. Outlook.com), support is getting WORSE ("Outlook.com no longer supports the margin CSS property, including margin-top, margin-right, margin-bottom and margin-left. Float support has also been dropped")
  * the only popular desktop mail app to support media queries is Apple Mail, but media queries tend to work well on native mobile email clients. The Gmail and Yahoo! Mail apps do NOT support media queries, but all Apple Mail clients, Android 2.2+ clients, and BlackBerry OS 6+ clients support media queries.  Funnily enough, the Windows Phone 7.5 email client was the first Microsoft email client to support media queries, but support was dropped again in Windows Phone 8.
  * The minimum font size on some devices is 13px, but [you can override this][cm-min-font].
  * supposedly margins are supported in Gmail, but I have never gotten it to work correctly. Especially negative margins
  * you can have hidden text that gets shown in the email list preview area, but isn't shown in the email itself
  * the issues with using images for everything
  * AM: get links - tell us where they should go

[dev-cerberus-home]: http://tedgoas.github.io/Cerberus
[dev-cerberus-github]: https://github.com/TedGoas/Cerberus
[mc-basics]: http://templates.mailchimp.com/getting-started/html-email-basics/ "MailChimp Designer/Developer Reference"
[mc-typography]: http://templates.mailchimp.com/design/typography/ "MailChimp Typography Reference"
[cm-min-font]: http://www.campaignmonitor.com/blog/how-to/2010/12/save-your-layout-by-overriding-the-minimum-font-size-on-the-iphone-and/
[cm-css]: https://www.campaignmonitor.com/css/
[cm-max-width]: https://www.campaignmonitor.com/blog/email-marketing/2005/04/maximum-width-for-html-emails/
[cm-max-width-2]: https://www.campaignmonitor.com/blog/email-marketing/2011/06/how-wide-are-html-email-designs-today/
