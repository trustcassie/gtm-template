# Cassie Google Tag Manager Consent Mode v2 Integration

**Overview**

The Google Tag Manager template is designed to seamlessly integrate a Cassie Cookie Banner with Google Consent mode v2. Our Cassie CMP tag allows you to adjust how your Google tags behave based on the consent status of your users.

**Cassie CMP Tag Features**

Our custom tag extends the capabilities of Google Tag Manager by providing enhanced consent management features based on the visitor's location. This allows you to automate consent-related actions such as opting in or out users based on their geographical location.

**Key Features:**

1. **Flexible Consent Workflows:** Customize consent workflows based on the specific needs of your website or application.
2. **Location-Based Default Consent Setting:** Customize default opt In/ Out setting for all or selected GTM Consent states based on the specific geographical regions (e.g. US, the United States or UK, the United Kingdom).

**Prerequisites for Cassie Clients**

This document assumes Cassie clients have configured their Cooke Scripts with the relevant Consent Types in the Cassie Administration Portal.

Cassie supports the following Consent Types:

- ad\_storage
- ad\_user\_data
- analytics\_storage
- functionality\_storage
- personalization\_storage
- ad\_personalization
- security\_storage

More information on these consent types and the impact of granting and denying consent on their behavior can be
found in the Google documentation [here.](https://support.google.com/tagmanager/answer/13802165?hl=en)

**Google Tag Manager Installation Guide**
 Clients should follow the steps below to integrate our Cassie CMP tag within Google Tag Manager:

**Step 1: Access Google Tag Manager**

- Log in to your Google Tag Manager account.
- Navigate to the desired container for your website.

**Step 2: Add Cassie's CMP Tag to your Library**

- In the container, go to the "Tags" section.
- Click on "New" to create a new tag.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/3db03ebe-3125-4385-910c-8a5155b0328d)

- Select the "Tag Configuration" container to access the available tag templates.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/75f5e1bd-ec4a-47c3-9c27-e276be932c1d)


- Select the "Discover more tag types" to access the GTM gallery.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/b1bcaf28-6989-48ff-8752-cf734faff9bd)

- Search and select the "Cassie CMP" tag.
  - Selecting the tag will now add this to your tag library and you can make custom adjustments based on your specific requirements.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/517d2d0b-ab44-47df-9c17-cd3e15c75cf1)

If you are unable to find the tag within the Gallery it can be downloaded and imported as a Custom Template from our [github repository.](https://github.com/trustcassie/gtm-template/)

- Navigate to the github repository and select template.tpl from the menu at the top of the page.
  
    ![image](https://github.com/trustcassie/gtm-template/assets/156684279/b8b0744a-969a-4395-b4af-ae90263350f3)

- Select 'Download raw file' in the top right hand corner of the template.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/e03ef6d5-9819-4e9f-bd5f-5f0f25097ae6)

- In your Google Tag Manager workspace select 'Templates' from the left hand menu and select 'New'.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/d016efac-086b-45b3-ac86-fdecdd88df96)

- Click on the elipsis menu in the top right hand corner and select 'Import'.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/fe1ef510-4a39-4645-bfc4-a17376a7d000)

- Select the template.tpl file from your downloads and click 'Save'.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/3df30efe-8f0f-4218-8f44-2421b22685fd)

- The template will now appear in your tag library.

**Step 3. Configure Cassie CMP Tag**

Now that you have selected the Cassie CMP tag, it is required that the tag is configured to the Cassie Cookie Banner by populating the Access Key, detailed in step 3.1. You have the ability to configure this tag to meet your specific requirements however we recommend following the below steps in addition to your custom configurations.

- Step 3.1 Access Key (Required)
- Step 3.2 Location-Based Default Consent Mode Settings (Optional)

**3.1: Access Key**

The access key field can be located within the Cassie CMP tag titled "Cassie Access Key". It is required that this field is populated using the same access key used for the Cassie Cookie Banner in order for the Cassie CMP tag to register the session consent.

The Access Key can be obtained in the Cassie Administration Portal.

⚠️ **Warning**: While keys are issued in UPPERCASE and are generally not case‑sensitive, this stage of the process requires all entries to be in lowercase. Testing will fail if this requirement is not followed. The absence of validation may make this constraint less apparent.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/d8ba6984-fd42-405f-a811-46df274c9165)

**3.2: Set up Location-Based Default Consent Mode Settings (Optional)**

GTM applies a default state of 'Granted' to all Consent states until a user's consent is received. You can configure default consent based on your regulatory requirements per geographical region in the Cassie CMP tag by using "Default Consent Settings".

A default consent setting profile can be created per geographical region by creating a profile defining the ISO Code or creating a Global profile by leaving the ISO Code empty. When established the default consent will be applied to all consent states for users in that specified region.

\*Please use ISO-3166-1 alpha-2 country codes for region values.

**Example:**

The below example highlights the different consent settings per different region:

![image](https://github.com/trustcassie/gtm-template/assets/156684279/d1db4e9e-72ee-41b6-89c4-01ed3c503a7e)

**Set Up Steps**

- Select Cassie CMP Tag within your Tags library
- Select the "Edit" icon within the Tag Configuration container.
- Enable the "Enable Consent Mode Settings" checkbox to access the Consent settings
- Select "Add Row", located within the "Default Consent Settings" section.
- Populate the "Region" field with the 2 letter code for the desired region
- Configure the Consent type options based on your specific requirements for the defined region
- Select "Add", located within the Add new row modal
- Select "Save", located within the Tag modal.

![image](https://github.com/trustcassie/gtm-template/assets/156684279/d1161c96-0d7e-4407-909b-3f2008767b3e)

![image](https://github.com/trustcassie/gtm-template/assets/156684279/b40b3291-4dbf-4d35-8423-ee75d7c88154)

**Step 4: Configure Trigger**

A firing trigger is required for the Cassie CMP tag to fire. In addition to the built-in trigger “Consent Initialization - All Pages” you also need to add a custom trigger.
<img width="940" height="183" alt="image" src="https://github.com/user-attachments/assets/4b06bc3f-369f-4dfd-86d2-25450ad8db69" />

**Step 4a: Creating a custom trigger**

To create the custom trigger from within the tag:
- Select ‘+’ in the top right of the Triggering section
<img width="3091" height="1695" alt="image" src="https://github.com/user-attachments/assets/6f3c0b79-c527-456b-bf90-adfdc50e9178" />

- Select ‘+ New Trigger’ in the top right 'Choose a trigger' screen
- Name your trigger ‘CassieGtmConsent’
<img width="3094" height="1146" alt="image" src="https://github.com/user-attachments/assets/0cdedfe4-c6ef-451d-80d4-aa02caec900f" />

- Select the 'Trigger Configuration' section and choose 'Custom Event' trigger type
<img width="3774" height="2004" alt="image" src="https://github.com/user-attachments/assets/f4e1fe34-3165-4171-8515-7843d49e080e" />

- Enter the event name as 'CassieGtmConsent'
- Select ‘All custom events’ for this trigger to fire on
<img width="940" height="413" alt="image" src="https://github.com/user-attachments/assets/e7c5d942-bbb4-48d2-b3e2-ae550cb65484" />


**Step 5: Save and Publish**

- Save your configuration.
- Publish the changes to your Google Tag Manager container.

**Tag Advanced Settings – Required Consent to Fire**

Now that we have a Cassie CMP tag capturing updated user consent against GTM Consent states, we can configure other tags to fire based on the stored consent.

A number of tags within GTM are pre-configured to be consent aware and will show their Built-In Consent Checks in their Consent Settings, for example Google Analytics and Google Ads. Any tags that are pre-configured will not require additional consent checks and will automatically respond accordingly to the consent from the Cookie Banner.

Any tags that are not pre-configured will require additional consent to fire. The below example highlights a tag that checks if consent has been granted for Consent state: ad_storage before firing. This means that you can configure a tag to deploy based on consent state opt in status and your specific requirements.

**Set up steps**

- In the selected tag
- Select the "Advanced Setting" label
- Select "Consent Settings"
- Select the "Require additional consent for tag to fire" checkbox
- Select the consent state that you want to have a status of "granted" as a pre-requite for this tag to fire
- Save

![image](https://github.com/trustcassie/gtm-template/assets/156684279/c10ca39f-659d-4f4c-97ff-62d13ca61229)


If you encounter any issues or have further questions, please refer to our support documentation or contact our support team for assistance.
