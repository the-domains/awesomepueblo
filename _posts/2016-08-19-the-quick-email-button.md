---
datePublished: '2016-08-29T18:01:52.110Z'
sourcePath: _posts/2016-08-19-the-quick-email-button.md
hasPage: true
author: []
via: {}
dateModified: '2016-08-29T18:01:51.843Z'
title: The Quick Email Button
publisher: {}
description: Awesome discussion about URL hacking a customer…
starred: false
url: the-quick-email-button/index.html
_type: MediaObject

---
# The Quick Email Button

Awesome discussion about URL hacking a customer...

<article style=""><img src="https://s3-us-west-2.amazonaws.com/the-grid-img/p/c13cf54bf0e5112c8e0ac636091f0de16d186970.png" /><h1>The Quick Email Button</h1><p>or, mastering the black art of URL hacking the email page. Sending an email from Salesforce.com can be a clicky operation. You dig around for the Send An Email button, click it, click Select Template, find your template and click it, maybe...</p></article>

**retURL** = Item/Object to return to after email is sent  
**rtype** = ???  
**p2\_lkid** = To address  
**p3\_lkid** = ???  
**p4** = CC address  
**p5** = BCC address  
**p26** = From address  
**save** = Send action  
**template\_id** = Email template ID

location.replace('/email/author/emailauthor.jsp?retURL=/{!Case.Id}&p3\_lkid={!Case.Id}&rtype=003&p2\_lkid={!Case.ContactId}&template\_id=00X12000001Z29C&p5=&p26=customer.support@confirmation.com');