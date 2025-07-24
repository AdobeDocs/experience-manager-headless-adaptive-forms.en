---
title: Create and Publish a Headless Form with Adobe Experience Manager Adaptive Forms | Step-by-Step Guide
description: Learn how to create and publish a headless form using Adobe Experience Manager's adaptive forms in this step-by-step guide. Discover the benefits of going headless and streamline your form creation process today. Start building dynamic, responsive forms that work seamlessly across devices with Adobe Experience Manager Headless Adaptive Forms.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: no
exl-id: cd7c7972-376c-489f-a684-f479d92c37e7
---


# Create and preview a Headless Form using a React app {#introduction}

<!-- Missing image ALT image tags -->

The starter kit helps you get started quickly using a React app. You are free to develop and use Headless Adaptive forms in an Angular, Vanilla JS, and other development environments of your choice.

Starting with Headless Adaptive forms is quite easy and quick. Clone the ready-made React project, install the dependencies, and run the project. You have a Headless Adaptive form integrated in a React app up and running. You can use the sample react project to build and test Headless Adaptive forms before deploying it in a production environment. 

Let's start:

>[!NOTE]
>
>
> This getting started guide uses a React app. You are free to use the technology or programming language of your choice to use Headless Adaptive forms. 

## Before you start {#pre-requisites}

To create and run a React app, you should have the following installed on your computer:

* Install the [latest release of Git](https://git-scm.com/downloads). If you are new to Git, see [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Install [Node.js 16.13.0 or later](https://nodejs.org/en/download/). <!-- URL is 404!! If you are new to Node.js, see [How to install Node.js](https://nodejs.dev/en/learn/how-to-install-nodejs). -->

## Get Started

Once you fulfill the requirements, perform the following steps to get started:

1. [Setup Headless Adaptive forms starter kit](#setup)

1. [Preview the Headless Adaptive form included in the starter kit](#preview)

1. [Create and render your own Headless Adaptive form](#custom)

    

## 1.  Setup Headless Adaptive forms starter kit {#install}

The starter kit is a React app with a sample Headless Adaptive form and corresponding libraries. Use the kit to develop and test your Headless Adaptive forms and corresponding React components. Run the following commands to set up the Headless Adaptive forms starter kit:

1. Open command prompt and run the following command:

    ```shell

    git clone https://github.com/adobe/react-starter-kit-aem-headless-forms

    ```

    The command creates a directory called **react-starter-kit-aem-headless-forms** in your current location and clones the Headless Adaptive forms React starter app into it. Along with the configurations and list of dependencies required to render the form, the directory includes the following important content:

    * **Sample form**: The starter kit includes a sample loan application form. To view the form (form definition) included with the app, open the `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` file. 
    * **Sample React components**: The starter kit includes sample react components for Rich text and Slider. This guide helps you create your own custom components using these Rich text and Slider components. 
    * **Mappings.ts**: The mappings.ts file helps you map custom components with form fields. For example, map a numeric stepper field with a ratings component. 
    * **Environment configurations**: Environment configurations let you choose to render a form included in the starter kit or fetch a form from an AEM Forms Server. 

    ![](/help/assets/getting-started-starter-kit-content.png)

    >[!NOTE]
    >
    > 
    > Examples in documents are based on VSCode. You are free to use any plain-text code editor. 
    

1. Navigate to the **react-starter-kit-aem-headless-forms** directory and run the following command to install the dependencies:

    ```shell

    npm install

    ```

    The command downloads every package and library required to build and run the app—including the Headless Adaptive forms libraries (@aemforms/af-react-renderer, @aemforms/af-react-components, @adobe/react-spectrum). It then runs validations and persists data for each form instance.
 

    ![](/help/assets/install-react-app-starter-kit.png)


## 2. Preview the Headless Adaptive form {#preview}

After setting up the starter kit, you can preview the sample Headless Adaptive form, replace it with your own custom form. You can also configure the starter kit to retrieve a form from an AEM Forms Server. To preview the form

1. Rename the `env_template` file to `.env` file. Also ensure, the USE_LOCAL_JSON option is set to true. 

   ![](/help/assets/rename-env-file.png)

    <!-- The options in the .env file help you configure source of the forms definantion (.JSON):
    *  To source forms definantion (.JSON) from an AEM Server, set USE_LOCAL_JSON option to false, use the AEM_URL option to specify URL  of your AEM Server, and set the AEM_FORM_PATH option to path of your adaptive form.
    *  To source forms definantion (.JSON) form-model.json file included in the starter-kit, set USE_LOCAL_JSON option to false. -->
  
1. Use the following command to run the app: 

    ```shell

      npm start

    ```

   
    This command starts a local development server, and opens the sample Headless Adaptive form, included in the starter app, in your default web browser.

    ![Sample Headless Form](assets/sample-headless-adaptive-form.png)

    All set! You are ready to start developing a custom Headless Adaptive form.
    
    <!--  As you know, in a headless form the form data and logic are separate from the presentation layer and can be used by any client that can make HTTP requests, such as a mobile app, a static site, or a different web application. The form is often managed and stored on a server, which serves as the backend for the form. The client sends requests to the server to retrieve the form, submit data, and receive updated form data. This allows for greater flexibility and integration with different technologies. You can store and retrive a Headless Adaptive form on an AEM Server  -->

## 3. Create and render your own Headless Adaptive form{#custom}

A Headless Adaptive form represents the form and its components, such as fields and buttons, in JSON (JavaScript Object Notation) format. The advantage of using the JSON format is that it can be easily parsed and used by various programming languages, making it a convenient way to exchange form data between systems. To view the sample Headless Adaptive form included with the app, open the `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` file. 

Let's create a `Contact Us` form with four fields: "Name," "Email," "Contact Number," and "Message." The fields are defined as objects (items) within the JSON, with each object (item) having properties such as type, label, name, and required. The form also has a button of type "submit." Here is the JSON for the form. 


```JSON
{
  "afModelDefinition": {
    "adaptiveform": "0.10.0",
    "items": [
      {
        "fieldType": "text-input",
        "label": {
          "value": "Name"
        },
        "name": "name"
      },
      {
        "fieldType": "text-input",
        "format": "email",
        "label": {
          "value": "Email"
        },
        "name": "email"
      },
      {
        "fieldType": "text-input",
        "format": "phone",
        "pattern": "[0-9]{10}",
        "label": {
          "value": "Contact Number"
        },
        "name": "Phone"
      },
      {
        "fieldType": "multiline-input",
        "label": {
          "value":"Message"
        },
        "name": "message"
      },
      {
        "fieldType": "button",
        "label":{
          "value": "Submit"
        },
        "name":"submit",
        "events":{
          "click": "submitForm()"
        }
      }
    ],
    "action": "https://eozrmb1rwsmofct.m.pipedream.net",
    "description": "Contact Us",
    "title": "Contact Us",
    "metadata": {
      "grammar": "json-formula-1.0.0",
      "version": "1.0.0"
    }
  }
}

```

>[!NOTE]
>
> * The "afModelDefinition" attribute is only needed for React applications and is not a part of the form definition.
> * You can hand-craft the form JSON or use the [AEM adaptive forms editor (adaptive forms WYSIWYG editor)](create-a-headless-adaptive-form.md) to create and deliver the form JSON. In a production environment, you use AEM Forms to deliver the form JSON, more on it later.
> * The tutorial uses the https://pipedream.com/ to test form submissions. You use your own or third-party endpoints approved by your organization to receive the data from a Headless Adaptive form.   


To render the form, replace the sample Headless Adaptive form JSON `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` with the above JSON, save the file, wait for the starter-kit to compile and refresh the form.    

![Replace the sample Headless Adaptive form JSON `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` with the custom Headless Adaptive form JSON](assets/render-custom-headless-adaptive-form.png)

<!-- Your form is ready. Let's add some validations and make "Name", "Email", and "Message" fields mandatory. -->

You have successfully rendered the Headless Adaptive form. 


## Bonus

Let's set the title of the webpage hosting the form to `Contact Us | WKND Adventures and Travel`. To change the title, open the _react-starter-kit-aem-headless-forms/public/index.html_ file for editing and set the title.  

![](assets/contact-us-headless-adaptive-forms-updated-title.png)

 
## Next step

By default, the starter kit uses [Adobe's Spectrum](https://spectrum.adobe.com/) components to render the form. You can create and use your own components or third-party components. For example, using Google Material UI or Chakra UI.

Let's [use Google Material UI](use-google-material-ui-react-components-to-render-a-headless-form.md) to render the `Contact Us` form.



    