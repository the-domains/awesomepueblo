---
datePublished: '2016-08-29T18:02:09.291Z'
sourcePath: _posts/2016-08-02-step-by-step-through-email-to-case-again-again.md
hasPage: true
author: []
via: {}
dateModified: '2016-08-29T18:02:08.885Z'
title: 'Step by Step Through Email-to-Case, again, again..'
publisher: {}
description: >-
  Guide I'm following now that I've got a test email address from the IT that's
  actually set up on our Exchange Server and not just a gmail account...
starred: false
url: step-by-step-through-email-to-case-again-again/index.html
_type: MediaObject

---
# Step by Step Through Email-to-Case, again, again..

Guide I'm following now that I've got a test email address from the IT that's actually set up on our Exchange Server and not just a gmail account...

following the guide...

## [Service Cloud Workbook][0]

Logging in to my [Partial Copy Sandbox][1]. The same sandbox I'm setting up for [Service Console][2], refreshed from the last update.   
Turn on On-Demand Email-to-Case. I believe this is the one we're going to go with so testing this first.

[Differences between Email-to-Case and On-Demand Email-to-Case.][3]

Second sentence of step 1... _Note that this step assumes you've set the Default Case Owner and Automated Case Owner in Salesforce---these settings just make sure that each case is automatically assigned an owner and not lost in a technological void._

Didn't do that yet! Heading there now.

Going through the Support Settings...  
| Setup | Support Settings

Customize Support Settings  
Here's a [breakdown ][4]of what each of the setting entail.

Now I've come across a comment regarding **assigning a queue **as the default case owner. I don't have any queues yet so back tracking again.

OK, starting here instead...

## 1\. [Set Up Customer Support][5]

* Asked support managers for [business hours][6] for the different offices. Set up the US office as the default.
* Asked HR for list of [corporate holidays][7] to enter.
  * Christmas and Thanksgiving are set up for multiple days. Can't just create another holiday called "Day After Thanksgiving" and set it for the 4th Friday of every November because is may be the 5th Friday some years. So, set up Christmas and Thanksgiving like this. Occurs every December 24 effective 12/24/2016 until 12/25/2016 Should Work.
* [Queues][8] - created US Support Queue with our support team members added. Used the test email,_supporttest@..., _as the Queue's email address.
  * created US, UK, India, APAC, Japan and South Africa Support Queues

* [Assignment Rules][9]. - scheduled meeting with management to discuss.
  * US gets everything coming to the support email. unless...
    * if accounting firm in UK then assign to UK support queue. if within UK business hours
      * (Case: Account TypeEQUALSAccounting Firm) AND (Account: Billing CountryEQUALSUnited Kingdom) AND (Case: Business HoursEQUALSUK)
    * if accounting firm in APAC then assign to APAC support queue, any hours
      * (Case: Account TypeEQUALSAccounting Firm) AND (Account: RegionEQUALSAsiaPac (CAP))
    * also added these email domain suffixes in the filter for APAC.
      * Malaysia -- com.myAustralia -- com.auNew Zealand -- com.nzSingapore -- com.sgHong Kong -- com.hkSometimes the codes can be reversed.my.com; .au.com; .nz.com; .sg.com; .hk.com
* Escalation Rules - none yet
* Support Settings, below..
* Auto-Response Rules - waiting for support team response
* Enable On-Demand Email-to-Case

IT hooked me up with the

## 2\. [Customize Support Settings][10]

Created Case Creation Template :

The template used to notify contacts that their case was created manually by a support agent. The notification is optional; it's triggered by a checkbox on the case edit page. This template must be Available for Use.

Created Case Assigned Template as well.

The template used to notify users that a case was manually assigned to them by an administrator or another user. The notification is optional; it's triggered by a checkbox on the Change Case Owner page. This template must be Available for Use.

3\. [Service Cloud Workbook][0]

Step 1: Enable On-Demand Email-to-Case

Now that the Default Case Owner and Automated Case Owner are assigned...

Enabling On-Demand Email-to-Case

Step 2: Define and Verify Routing Addresses

Filled out the fields. Saving Email Headers. Not creating Tasks. Normal Priority. Case Origin = In-bound Email, of course.

_Verifying the email , done_

_Asked IT to forward emails to our test support address to the long SFDC email string. done. When the emails came in to Salesforce and created the case they were automatically marked closed. I have a process to do this that forgot about. "Mark Case Closed" process. Deactivated that._

\*need to enable Feed View on the Case page layout. I remember this being a sticking point for people at the training down in FL. I don't remember having an issue myself then but can't figure it out now.

Think this is it.

Be sure feed tracking is enabled for the object on which you want to create a feed-based layout. To enable feed tracking, from Setup, enterFeed Trackingin theQuick Findbox, then select**Feed Tracking**.

[Create a new page layout][11]and selectFeed-Based Layout.

Current Feed Settings for the Case Layout
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/ec481da5-4e73-49a6-b9e1-196f397f36f4.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/efe98064-029d-4f8a-9cdc-63e65628c093.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/7f8d4412-59bf-4219-9ab3-8ac002411d74.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/394dc3de-7c53-4e6c-bb21-a3f70d4800b0.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/62269564-e854-43cd-a01e-dc3bce588ec9.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/27f0efa1-7061-4b76-8553-ded05cf40d0c.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/1c360d28-7cde-4b7c-9acf-553ae77ab610.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/9e701714-edb1-433c-9c4c-73c790ad163d.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/fc700a8c-821c-4316-9d36-eaff3ceeaf56.png)

Created global action to Send Email and make it part of the feed on the Case page.

Could not find out why the reply and reply to all options were not showing up on my email related list on the case page. EMAIL [Deliverability][12] !!!

Need to set up a standard signature for the customer support email replies.

Tried using the org-wide email footers but this is not working.

Updated all of the list views so only the queue members can see the cases in the queue   
Added 'Send Email' to the page layout.

Customizing the 'Custom Console Components' in the page layout. Making sure Knowledge is added via the 'Layout Properties' section. Added info on the left side of the console on the Case layout for Account and Contact info.

TESTING...

I'm testing the email-to-case functionality. Created some fake users and email address to have cases created automatically and assign to the queue.

However, what happens when you Close a case and then the customer emails again. Here's the [answer][13].

## Items to consider in testing;

1. _is the case getting routed to UK queue when the customer is associated with a UK account? _**yes**
  1. _only during business hours in UK_**- no, anytime. will build escalation to route to US queue when case isn't answered in 8 business hours.**
2. _is the case getting routed to APAC queue when the customer is associated with APAC account, anytime?_
3. _is routing assigning the cases to reps that are available automatically? _**YES**
4. _how do the reps get notified if the case is reopened? _**The case show up in their My Open Cases list view**
5. _how to assign the reopened case back to omnichannel notification for owner of the account. _**no.**
6. _what happens when case gets declined by everyone? _**goes back into the queue**.

[0]: https://developer.salesforce.com/docs/atlas.en-us.200.0.workbook_service_cloud.meta/workbook_service_cloud/service2_step1.htm
[1]: https://help.salesforce.com/apex/HTViewHelpDoc?id=create_test_instance.htm
[2]: http://sfdclrh.blogspot.com/2016/06/setting-up-service-console-on.html
[3]: https://help.salesforce.com/apex/HTViewHelpDoc?id=customizesupport_email.htm
[4]: http://help.salesforce.com/apex/HTViewHelpDoc?id=customize_supportrules.htm
[5]: http://help.salesforce.com/apex/HTViewHelpDoc?id=admin_supportsetup.htm&language=en_US
[6]: http://help.salesforce.com/apex/HTViewHelpDoc?id=customize_supporthours.htm&language=en_US
[7]: http://help.salesforce.com/apex/HTViewHelpDoc?id=customizesupport_holidays.htm&language=en_US
[8]: http://help.salesforce.com/apex/HTViewHelpDoc?id=setting_up_queues.htm&language=en_US
[9]: http://help.salesforce.com/apex/HTViewHelpDoc?id=creating_assignment_rules.htm&language=en_US
[10]: https://www.blogger.com/
[11]: https://help.salesforce.com/apex/HTViewHelpDoc?id=customize_layoutcreate.htm&language=en_US "With the enhanced page layout editor, you can tailor record page layouts to the needs of your users. Add, remove, or reorder actions, buttons, fields, and sections on a record’s detail page."
[12]: https://developer.salesforce.com/forums/?id=906F0000000AaIFIA0
[13]: https://help.salesforce.com/apex/HTViewSolution?id=000220076&language=en_US