Is there a "user_created" trait that I get automatically, so I do not need to add one?
Flagsmith does not currently have automatic traits (like location, create date etc), but it is on our backlog.

Can I create common User Traits for all users in the same environment?
No, Traits are created automatically when you set them for each Identity.

Does the Open Source version of Flagsmith have a limit of requests per month?
No, there are no limits to API calls on the self hosted open source version of Flagsmith

Can the open source version be configured to connect to an LDAP server?
We have SAML/Okta integrations and there are connectors for LDAP within Django, but we don't have any configurations set up for that as of yet.



These are features of our Enterprise Edition, however. Please reach out to us and we can help you get on an Enterprise license.

Does the Open Source version of Flagsmith have any restrictions?
The entire codebase of Flagsmith is publicly available. The Flagsmith product has a dual license for use, with the majority of the codebase being Open Source under a BSD 3-Clause license.



The Enterprise Edition (EE) repository holds a portion of code for features we sell under an Enterprise license. These may not be used in production without an Enterprise license from Flagsmith. This includes RBAC, and other features we may include in this license in the future.



You can see which repositories are in which license on GitHub: https://github.com/Flagsmith

Is Flagsmith SOC 2 certified?
Flagsmith is SOC2 Type 2 certified. We can provide our SOC2 audit report on request.



If data security is a top priority we recommend using Flagsmith On-Premises. We support this for our Enterprise clients, and work with large banks and healthcare providers that have chosen us because this gives them the highest level of control and security.

How do I delete an Organization?
Go to 'Organization' in the top right of the application.
Click 'Manage' next to the Organization you want to delete.
Scroll to the very bottom and click the trash can icon next to 'Delete Organization'.
Type in the organization name and confirm you would like to delete it.


Careful! This organisation will be PERMANENTLY deleted, along with all projects and features!

How do I downgrade to the Free Plan from a paid plan?
You can manage your subscription in the 'Organizations' dashboard:

Go to your Organization in the top right and click "manage".
Then click 'Manage Invoices'
Enter your billing email address
Enter the one time passcode sent to your email


How do I delete an account?
Go to 'Organization' in the top right of the application.
Click 'Manage' next to the Organization the account is in.
In 'Team Members' click the trash can next to the account you would like to delete.




Does Flagsmith have G Suite Integration?
Yes you can log in with G Auth for SSO.

Does Flagsmith support SSO?
Yes we support Google and Github SSO on all of our plans including the free tier.

How can I change the email associated with my account?
You will need to contact support to perform this action. Please chat us!

How do I update my payment details?
Go to 'Organization' in the top right an click edit

Click 'Manage Invoices'
Enter your billing email address
Enter the one time passcode sent to your email
Click on 'Payment Methods'

How do I add a new person to my organisation?
You can do this in one of two ways, whichever you prefer.



1) Invite them via Email:

Go to 'Organization' in the top right and click 'Edit'
Under 'Team Members' click 'Invite Members'
Enter their email address, select their role, and click 'Send Invitation'
They will get an email inviting them to join your Organization in Flagsmith


2) Send them an invite code:

Go to 'Organization' in the top right and click 'Edit'
Under 'Team Members' select the role and click 'Get Invite Link'
Share this invite link with the person you would like to add

How do I view past invoices?
We email your invoice every month, it should come from: Ben Rometsch - Flagsmith <ben.rometsch@flagsmith.com>



You can also self serve on the website:

Go to 'Organization' in the top right and click 'Edit'
Click 'Manage Invoices'
Enter your billing email address
Enter the one time passcode sent to your email

Is it possible to have a calendar based release using Flagsmith?
Go to your feature menu and select the feature you want to modify.
Then click on "Create Change Requests".






Create a tittle, description and select a day and time to release the feature.
Select the number of people to approve changes to the feature.






PS: It is only available for Scale-Up and Enterprise members

Is it possible to create two keys in one environment and have different permissions?
You could proxy the Flagsmith API to achieve this.



With this you would be able to have for example two environment keys in one environment, one can only get data, another one can get and set (like traits).

Is it possible to set a flag that has complete precedent over all users & segments?
Unfortunately at this time Flagsmith does not have that capability.



In other words, it is not possible to allow turning off a feature and later turning it on again without having to think for which segments the feature was initially turned on.


In the React SDK, is it possible to separate the initialization, like in the Node.js API?
Yes, there's a preventFetch option in flagsmith.init for this exact usecase. Then you can call identify/getFlags whenever you want.



This option makes possible to separate the initialization, like in the Node.js API. In other words, initialize without getting flags and then get flags later.

Is it possible to clone a flag?
Unfortunately at this time Flagsmith does not have that capability.



What this means is that we are NOT able to create a 'template' flag that includes all tenants/segments and then cloning that flag with all the correct settings ready for use.

When querying identities, is it possible to sort by creation date?
Unfortunately this feature is not available right now.



You may want to connect to your analytics platform such as Amplitude or Mixpanel using our integrations.


Is the function startListening(ms) something that can "auto-fetch"?
Yes, that hits the API for new flags every x milliseconds.



Follow-up question: Will such startListening(ms) API calls be counted in monthly quota?

Answer: Yes, this will count against your monthly API quota.

How do I identify an anonymous user? What about running AB tests with anonymous users?
In this case you should generate a GUID/hash for the user on your client side, cookie it, and use that to identify the user.



In terms of running tests against anonymous users, Flagsmith needs some sort of consistent ID that you store against the user on the client, otherwise it's impossible for us to serve a consistent test to that user. Generally people just create a random GUID and then store it on the client (e.g. using cookie on web) but it depends on your client implementation.

Is there way to render traits in users list in your webUI
We don't have the option to view in the webUI currently. You can get use Traits via the API.

Can my application send multiple values with remote config?
Yes, that can be done with Flagsmith.

Is there a way to await the response from the method bullettrain.identify()?
Identify returns a promise, so yes. Identify will resolve after the new flags have been resolved so flagsmith.getValue / hasFeature, etc. will be updated after the promise resolves.

Can I create Environments using the API?
Yes you can create environments via the API - there's info on how to do this here: https://docs.flagsmith.com/clients/rest/

Can I create flags via an SDK API?
To create flags, you will need to use the REST API directly.



More info on the REST API here: https://docs.flagsmith.com/api/

Is there any way to export a config in Flagsmith?
There's not at the moment. You could write a script to export things via the API.

Can I bulk change flags?
You can use our API to bulk change flags.



There's no way currently within our UI to bulk change flags.

When I query for feature flags what method / API should I be using to pass the user email address?
You need to identify the user, so you would call - bulletTrain.identify(""<email address>"");



More on user Identities here: https://docs.flagsmith.com/managing-identities/

Can I copy Features across Environments?
Features are shared across Environments automatically.

What is the difference between Feature Flag and Remote Config?
A Feature Flag is an on/off.



Remote Config, rather than just an on/off allows you to set values to strings, bools or numbers. It is often used for things like api keys and adding settings to components.

If a segment is 'off' what does that mean?
What it means is that any segments associated with a flag marked as 'off' will override the flag state for any Identities that are members of that segment and set the flag to 'off'.

How can I check which users belongs to which Segment?
That's not possible right now. However, we do have this feature in the backlog.



You can view a segment and see which user are in the segment, but not the other way around.

Can I view all the users in a segment?
To do this you need to go in your segments and under "Users".



This will show you a list of the users and which ones are o aren't in the segments. ***

Does the % split segment feature work for non-identified users?
No, it does not. If you have anonymous users and you want to use the % split you will need to provide a unique key for them and store it on the client somehow (depending on what platform you are targeting). They will be using the environment defaults.

Does Flagsmith allow me to incorporate user segmentation data (eg from mixpanel) to deploy flags based on user attributes?
We do offer the ability to target users based on pre-defined Segments.



We call the list of users ""identities"". You can read more about it here: https://docs.flagsmith.com/managing-identities/



In terms of third parties, we have a built in integration with Amplitude (similar platform to Mixpanel), and with Segment if that is your CDP.

When using a segment with "% split", would changing the value affect existing users?
The segment % split value will not change for an individual identity, so for example if someone is in a 10% split they will also be in an 11%, 20% or 80% split. Every Identity/Segment combination is combined and then hashed, and a floating point value between 0.0 and 1.0 is generated from this hash. This value is then evaluated against the "% Split" rule. So that number wont change for an Identity/Segment combination.



Each Identity gets assigned a float between 0.0 and 1.0. So if the Identity for that segment came out at 0.04 then they would be outside of a 5% segment but inside a 2% segment.



As an example. If you had 1000 Identities, and set the % split to 20%. You would get roughly 200 Identities in that segment. If you moved the split to 50%, you would get roughly 500. If you moved it back to 20%, you would get the exact same 200 as you originally had.

Can I put a Segment inside a Segment?
No, this cannot be done today.



It is on our future roadmap, but is often better solved with Multivariate Flags, which is being launched in Q1 2021.

Is there a way to combine two conditions with 'AND' for Segments?
Yes, in create New Segment of Edit Segment, you can add or remove 'AND' conditions with the 'Add AND Condition' button.

What happens if I have the same user that is attached to two segments and have an opposite config on the same feature?
You can control the priority of the Segment Overrides by dragging the segments up and down in the Segment Overrides portion of the Feature Editing page. Highest on the list will get priority in case of a conflict.

Will a segment override work if the feature is toggled off?
Yes, a segment override will work regardless of whether the feature is toggled on or off.

Is it possible to export the users to a .CSV or something similar?
Yes, you can grab them via the API.

What events can I send from Flagsmith into my own infrastructure?
We have webhooks for both flag change events and audit log events.



We do not have webhooks at the user level at present.



More info here: https://docs.flagsmith.com/system-administration/

How would I define an experiment for a subset of users based on existing traits in a CDP?
We have integrations between our platform and many popular CDP platforms.



For example we have an integration with Amplitude which sends user flags from our API to Amplitude behind the scenes. This then allows customers to use Amplitude to work with this data downstream.



Our current list of integrations can be found here - https://docs.flagsmith.com/integrations/overview



We're always working on adding customer requested integrations, let us know if there is an integration you are interested in.

Is customer bucketing guaranteed in A/B tests over time to ensure their consistent system experience?
Yes, as long as the user is identified then they are placed in the same cube as long as they have the same ID.

Where is Flagsmith hosted?
The Edge API provides a datastore and Edge compute API that is replicated across 8 AWS regions, with latency-based routing and global failover in the event of a region outage.

What is the official base URI for the API?
https://api.flagsmith.com/api/v1/

How can I check in Flagsmith how many requests I've send to the service?
If you go to the Organisation console, the API usage chart is on that page.

Where can I find my Project ID?
If you go to the project settings page, you can see the ID in the URL.



Also, you can find them by looking at the network tab when creating a feature in the browser. Create a new flag and then look at the inspector.

Is there support for initializing a client that does not establish a network connection to Flagsmith?
If you initialise the client without requesting any flags etc, it won't make a call to the Flagsmith API.

Where can I get the Flagsmith token for an Environment?
You can find it in the 'Settings' for the Environment

Do you support Python?
Yes. All the languages we support can be found here: https://docs.flagsmith.com/clients/rest/

Does the Flagsmith .net SDK work with Unity 3D?
Yes, it was built with .NET Standard 2.0 which works across virtually everything.

When deploying with Docker, how do I configure SES credentials?
You can provide regular env vars for AWS e.g.



AWS_ACCESS_KEY_ID = 'YOUR-ACCESS-KEY-ID'

AWS_SECRET_ACCESS_KEY = 'YOUR-SECRET-ACCESS-KEY'

