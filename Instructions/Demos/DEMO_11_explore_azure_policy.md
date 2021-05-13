---
Demo:
    title: 'Explore Azure Policy'
    module: 'Module 4 Lesson 2: Describe the capabilities of Microsoft compliance solutions: Describe Azure Policy'
---


# Demo: Explore Azure Policy

## Instructions

#### Demo Part 1: Create a policy to require a tag on a resourge group (shows steps to create a policy from a template)

1. Open Microsoft Edge. In the address bar enter **portal.microsoft.com**.

1. Sign in with your admin credentials.
    1. In the Sign in window enter **admin@WWLxZZZZZZ.onmicrosoft.com** (where ZZZZZZ is your unique tenant ID provided by your lab hosting provider) then select **Next**.
    1. Enter the admin password which should be provided by your lab hosting provider. Select **Sign in**.
    1. When prompted to stay signed- in, select **Yes**.

1. You are now in the Azure Portal.  Underneath where it says Azure services, select **Policy**. This opens the Policy home page which provides a dashboard view.  The scope for which you are seeing the information applies the Azure Pass you are using, as part of this lab.   Notice the information available in the dashboard.

1. Form the left navigation panel, under Authoring, select **Assignments**.

1. From the top of the page, select **Assign policy**.

1. The Assign policy wizard opens to the guide the admin in the process of assigning a policy.  Next to the Policy definition field, select the **ellipses**.  A list of the available policy definitions is provided.  

1. In the search bar enter, **Tag**.

1. From the search results, select **Require a tag on resource group** (you may need to scroll down), then press **Select**.  Note: the effect of this policy is to Deny the creation of any new resource group that does not satisfy the requirement.  

1. Note the default assignment name.  Keep the name as is and from the bottom of the page, select **Next**.

1. In the Tag name field, enter **Environment** then select **Next**.  

1. In the non-compliance message, enter **An environment tag is required**, then select **Next**. Note: this message will appear as the reason for non-compliance for resource groups that were created before the policy assignment and do not have an Environment tag.  For resource groups created after the policy was created, the creating of the resource group will be denied if there is no environment tag.

1. Review the policy assignment, then select Create.  If you don’t immediately see the policy, select **Refresh**. Note: It may take up to 30 minutes for the policy to take effect.

1. Exit from the Policy assignments page by selecting the **X** on the top right corner of the screen.

1. You are now in the Azure services home page.  Keep this page open, you will need it for the next task.

#### Demo Part 2:  Show the impact of the policy by creating a resoruce group wtithout a tag, then fix it to have a tag.

1. Form the top of the page, underneath where it says Azure Services, select **Resource groups**.

1. From the top left corner of the page, select **+ Create**.

1. From the Basics tab of the Create a resource group, leave the Subscription field as is, Azure Pass -  Sponsorship.

1. In the Resource group field enter, **SC900-Labs**.

1. Leave the Region setting to the default, then select **Next: Tags**.

1. Leave the tag Name and Value field empty.  DO NOT POPULATE, then select **Review + create**.

1. You will see a validate passed (the tag name and value are not required fields in the wizard), then select **Create**.

1. You will see a failure message on the top of the screen, “Failed to create the resource group. View error details”.  Select **View error details**. The condition that is part of the Azure policy was not satisfied so the resource group creating was blocked, for non-compliance. Note: If you don’t see the failure message and the resource group was created, it is because the policy has not yet taken effect.  Go the Policy page for the policy you created in the previous task and once the policy takes effect you will see that the resource is not compliant.  The details page will include the non-compliance message.

1. The error summary shows the error type, “Resource ‘SC900-Labs’ was disallowed by policy.  Close this window by selecting the **X** on the top left corner of the screen.

1. From the Create a resource group window, select **<Previous**.

1. You are back in the Tags page for Create a resource group.  In the Name field enter Environment and in the Value field, enter **SC900-Labs**, then select **Next: Review + Create >**.

1. Verify the tag and select **Create**.

1. You will see the resource group listed.  Because the tag was provided in the resource group, the condition included as part of the Azure policy was satisfied.  The resource group is compliant with the policy.



