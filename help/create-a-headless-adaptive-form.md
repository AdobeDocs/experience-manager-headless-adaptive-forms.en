---
title: Create a Headless adaptive form using the Adaptive Forms editor
description: Create a Headless Adaptive form using the Adaptive Forms editor.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: no
exl-id: 0214dc2e-52ce-40e9-bef3-f4f4a7ff266f
---
# Create a Headless adaptive form using Adaptive Forms editor {#create-a-headless-adaptive-form-using-adaptive-forms-editor}

AEM Forms as a Cloud Service offers a user-friendly editor to create Headless Adaptive Forms. With over 24 core components available, you can easily create a form by dragging and dropping components in the editor. Additionally, the Rules editor allows you to add validations to your form fields. 

>[!NOTE]
>
>If you are new to Headless Adaptive forms, start with the tutorial [Create and publish a headless form using the starter kit](create-and-publish-a-headless-form.md). It covers the basics and walks you through hand-crafting a form before moving to the Adaptive Forms editor for headless forms.


Perform the following steps to create a Headless adaptive form using the Adaptive Forms editor: 

## Before you start

You require the following to create an Adaptive Form using the Adaptive Forms editor:

**For AEM 6.5 Forms:**

* Access to an AEM 6.5.16.0 or later Forms author instance. 

* Adaptive Forms Core Components

* Adaptive Forms Core Components template 

* An Adaptive Form theme for Core Components based template 

* Add your users to the [!DNL forms-users] group. The members of the [!DNL forms-users] group have permissions to create an Adaptive Form. 


**For AEM Forms as a Cloud Service**

* Access to an [AEM Forms as a Cloud Service author instance](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-forms-cloud-service) or a [local AEM Forms as a Cloud Service SDK](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment) environment. 

* **An Adaptive Form template**: A template provides a basic structure and defines the appearance (layouts and styles) of an Adaptive Form. It has pre-formatted components containing certain properties and content structure. It also provides the options to define a theme and submit an action. The theme defines the look and feel and submit action defines the action to take on submission of an Adaptive Form. For example, sending the collected data to a data source. The cloud service provides an OOTB template, named blank:

    * The `blank Adaptive Forms (Core Components)` template is included with every fresh AEM Forms as a Cloud Service program.
    * You can also [create a new Adaptive Forms (Core Components) template ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/template-editor) from scratch.

* **An Adaptive Form theme**: A theme contains styling details for the components and panels. Styles include properties such as background colors, state colors, transparency, alignment, and size. When you apply a theme, the specified style reflects on the corresponding components.  The `Canvas` template is included with every fresh AEM Forms as a Cloud Service program.

* **Permissions**: Add your users to the [!DNL forms-users] group. The members of the [!DNL forms-users] group have permissions to create an Adaptive Form. For a detailed list of forms for specific user groups, see [Groups and permissions](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/forms-groups-privileges-tasks).


## Create an Adaptive Form {#create-an-adaptive-form-components}

1. Log in to your [!DNL Experience Manager Forms] Author instance. 

1. Enter your credentials on the Experience Manager login page. After you are logged in, in the upper-left corner, tap **[!UICONTROL Adobe Experience Manager]** &gt; **[!UICONTROL Forms]** &gt; **[!UICONTROL Forms & Documents]**.

1. Tap **[!UICONTROL Create]**  &gt; **[!UICONTROL Adaptive Forms]**. The Wizard opens. In the Source tab, select a template:

    ![Template](/help/assets/core-components-template.png)

    When you select a template, a theme and submit action specified in the template are auto-selected, and the **[!UICONTROL Create]** button is enabled. You can go to the **[!UICONTROL Style]** or **[!UICONTROL Submission]** tabs to select a different theme or submit an action. If the selected template does not specify a theme, the create button remains disabled. You can go to the **[!UICONTROL Styles]** tab to select a theme manually.

1. In the **[!UICONTROL Style]** tab, select a theme:

    * When the selected template specifies a theme, the theme is auto selected in the wizard. You can also choose a different theme from the Style tab.
    
    * If the selected template does not specify a theme, you can use the Style tab to choose a theme. The **[!UICONTROL Create]** button is enabled only after a theme is selected. 

1. (Optional) In the Data Tab, select a data model:

    * **Form data model**: A [Form Data Model](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration) lets you integrate entities and services from disparate data sources to an Adaptive Form. Choose Form Data Model if the Adaptive Form that you are creating involves fetching and write data from and to multiple data source.
    
    * **JSON Schema**: [JSON schema](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/adaptive-form-json-schema-form-model) Adaptive Forms allow seamless integration with your organization's back-end system by providing the ability to associate a JSON schema, which represents the structure of the data being produced or consumed. This association enables authors to add content dynamically to the Adaptive Form using the elements of the schema. During authoring, you can quickly access schema elements in the Content browser's Data Model Objects tab. When you create a new Adaptive Form, the editor automatically adds all fields.

    By default all fields of the associated JSON schema are automatically selected and converted into corresponding Adaptive Form components, streamlining the authoring process. The wizard offers the added convenience of allowing you to choose selectively which fields should be included in the Adaptive Form through the use of checkboxes. 

1. In the **[!UICONTROL Submission]** tab, select a submit action:

    * When you select a template, the submit action specified in the template is auto-selected. You can select a different submit action from the Submission tab. The **[!UICONTROL  Submission]** tab displays all the available submit actions. 
    
    * When the selected template does not specify a submit action, you can use the **[!UICONTROL Submission]** tab to select a submit action

1. (Optional) In the **[!UICONTROL Delivery]** tab, you can specify a publishing or unpublishing date for an Adaptive Form. 
   
1. Tap **[!UICONTROL Create]**. A dialog box to specify the title, name, and location to save the Adaptive Form appears:

    * **[!UICONTROL Title]** Specifies the display name of the form. The title helps you identify the form in the [!DNL Experience Manager Forms] user interface.
    * **[!UICONTROL Name:]** Specifies the name of the form. A node with the specified name is created in the repository. As you start typing a title, the value for the name field is automatically generated. You can change the suggested value. The name field can include only alphanumeric characters, hyphens, and underscores. All the invalid inputs are replaced with a hyphen.
    * **[!UICONTROL Path:]** Specifies the location at which the Adaptive Form is to be saved. You can save the Adaptive Form directly at `/content/dam/formsanddocuments` or create a folder such as `/content/dam/formsanddocuments/adaptiveforms` to save an Adaptive Form. Ensure that you create the folder before using it in the path. The **[!UICONTROL Path]** field does not create a folder automatically. 

1. Tap **[!UICONTROL Create]**. An Adaptive Form is created and opens in the Adaptive Forms editor. The editor displays the contents available in the template.  Based on the type of Adaptive Form, the form elements present in the associated <!--XFA form template, XML schema or --> JSON schema or Form Data Model are displayed in the **[!UICONTROL Data Model Objects]** tab of the **[!UICONTROL Content Browser]** in the sidebar. You can also drag-drop these elements to build your Adaptive Form.

Now, you can drag-and-drop the Adaptive Forms components to the Adaptive Forms container to design and create the form. 


## View JSON rendition of an Adaptive Form {#preview-form}

Select the Adaptive Form and tap **Preview**. The preview of the form appears. To view the form definition (JSON) of the form, replace the .html extension in the URL with .model.json

For example, http://[author-server]:[port]/editor.html/content/forms/af/contact-us.model.json

You can use the Headless Adaptive Forms [getForm](https://opensource.adobe.com/aem-forms-af-runtime/api/#tag/Get-Form-Definition) API to fetch the form definition (JSON) and use it in your application.  

![View form definantion(JSOI)](assets/json-definantion.png)

