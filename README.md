## Campaign Attribution First Touch and Last Touch Tagging

Objects Referrenced<br>
-Contact<br>
-Lead<br>
-Opportunity<br>
-Campaign<br>
-Campaign Member<br>

## Overview

Contains custom fields and automation needed to implement first touch and last touch campaign influence within Salesforce. This tool leverages the campaigns object to attribute first and last touch campaigns to opportunities. It does this by looking at leads and contacts at both the time of opportunity creation and when campaign member records are updated.

Note that the Add Lead and Add Contact automation are from a forked project from Douglas Ayers. <a href="https://github.com/mainsail-partners/sfdc-add-lead-to-campaign-flow">sfdc-add-lead-to-campaign-flow</a>

## Process for Deploying

It is highly recommended that these are deployed into a staging environment or sandbox before moving to production. The metadata automatically sets the process builders and flows to active.
<br>
To deploy press the button below and you will be directed to a page where you will authenticate a production or sandbox environment and then deploy the metadata.<br>

<a href="https://githubsfdeploy.herokuapp.com">
  <img alt="Deploy to Salesforce"
       src="https://raw.githubusercontent.com/afawcett/githubsfdeploy/master/deploy.png">
</a>
<br>
Note this button/application was provided by Andy Fawcett and information can be found at https://andyinthecloud.com/category/githubsfdeploy/<br>

## Manifest for Changeset

Make sure that when you create an outbound changeset it contains the following resources:
<br>
-Custom Fields<br>
--Campaign<br>
---Landing Page URL<br>
---Members<br>
---MMR of Opportunities in Campaign<br>
---MRR of Won Opportunities in Campaign<br>
--Campaign Member<br>
---Count<br>
--Contact<br>
---Campaign Count<br>
---Campaign ID<br>
---First Touch Campaign<br>
---Last Touch Campaign<br>
--Lead<br>
---Campaign Count<br>
---Campaign ID<br>
---First Touch Campaign<br>
---First Touch Campaign Type<br>
---Last Touch Campaign<br>
--Opportunity<br>
---First Touch Campaign<br>
---Last Touch Campaign<br>
---Primary Contact<br>

-FlowDefinitions<br>
--Campaign: Add Contact to Campaign<br>
--Campaign: Add Lead to Campaign<br>
--Campaign Member Count<br>
--Campaign: Set First Touch Campaign<br>
--Campaign: Set Last Touch Campaign<br>
--Contact: Add Contact to Compaign<br>
--Lead: Add Lead to Campaign<br>
--OPPORT Assign First Last Touch Campaign<br>

-PermissionSets<br>
--Campaign Attribution Permissions

## Note on Field Permissions

We are unable to update field permissions for all custom profiles through this deployment. If you need to update profiles this can be done by applying the <b>Campaign Attribution Permissions</b> Permission Set to the specific users or roles.
