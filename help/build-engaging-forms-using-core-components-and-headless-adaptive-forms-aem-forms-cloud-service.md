---
title: Build Engaging Forms Using Core Components and Headless
seo-title: Build Engaging Forms Using Core Components and Headless
description: Build Engaging Forms Using Core Components and Headless
seo-description: Build Engaging Forms Using Core Components and Headless
topic-tags: develop
exl-id: ef99ffe9-4a37-4f0a-a4d3-78976c92220f
---
# Build Engaging Forms Using Core Components and Headless Adaptive Forms on AEM Forms as a Cloud Service {#build-engaging-forms-using-core-components-and-headless}

<!-- This article is completely missing the image ALT tags (descriptions) for each added image asset. That is impacting the CQI score for Experience Manager in a negative way. Be sure you add the required missing image ALT tags.  -->

## Lab Overview {#lab-overview}

In this hands-on lab, you learn the following:

How to use AEM Forms to create adaptive forms easily using the latest core components. These components are consistent with AEM Sites and enable omnichannel data capture experiences by delivering the adaptive forms as headless forms to web, mobile, and chat. You also learn best practices around styling, customizations, and front-end development.

## Key takeaways {#key-takeaways}

* **Business Agility**: As a business user, I can author Form experience for multiple channels easily.

* **Power to frontend developer**: As a frontend developer, I can control the end-user experience using headless forms.

* **Developer Velocity**: As a developer, I can easily and consistently customize Sites and Forms components.

## Prerequisites {#prerequisites}

To use this hands-on lab:

* Install the [latest release of Git](https://git-scm.com/downloads). If you are new to Git, see [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Install [Node.js 16.13.0 or later](https://nodejs.org/en/download/). If you are new to Node.js, see [How to install Node.js](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs).

* [Enable Adaptive Forms Core Components](enable-headless-adaptive-forms-and-core-components-on-forms-cloud-service.md) for your AEM Forms as a Cloud Service environment.

* Install [Microsoft Visual Studio Code](https://code.visualstudio.com/download) or any plain text editor. Examples in this document make use of Microsoft Visual Studio Code. 



## Lesson 1 {#lesson-1}

### Objective {#lesson-1-objectives}

Familiarize yourself with AEM Forms as a Cloud Service environment.

### Lesson context {#lesson-1-context}

In this lesson, you familiarize yourself with AEM Forms as a Cloud Service environment by navigating the user interface.

### Exercise {#lesson-1-excercise}

1. Open your browser and enter the URL of the Cloud Service author environment. <!-- URL is 404! EXPLAIN THE URL IS FOR ILLUSTRATION PURPOSES ONLY? For example: [https://author-p105303-e986623.adobeaemcloud.com/ui#/aem/aem/start.html](https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/start.html) -->

1. Log in to the Cloud Service author environment. 
    ![](/help/assets/screenshot2028113829.png){width="50%" align="left"}

1. To navigate to the AEM Forms UI, click **Forms > Forms & Documents**.



    ![](/help/assets/screenshot2028113929.png){width="50%" align="left"}

    Dismiss any pop-ups related to preferences or information. All the available forms are displayed.
    

## Lesson 2

### Objective

Author an adaptive form using the latest core components, configure, and submit the form.

### Lesson context

In this lesson, as a business user, you will author an adaptive form for multiple channels like web, mobile, and chat using adaptive forms authoring with standardized OOTB core components for data capture.

### Exercise

1. Create a submission endpoint for the form:

    1. Open <https://pipedream.com/requestbin> in a new browser tab.
    1. Click **Create a public bin** and copy the endpoint URL.
        ![](/help/assets/screenshot2028114329.png){width="50%" align="left"}

        ![](/help/assets/screenshot202023-03-0120at206.10.0020pm.png){width="50%" align="left"}

1. Author an adaptive form using the Wizard interface:

    1. In the browser tab used in Lesson 1, navigate to AEM Forms as Cloud Service web interface and navigate to Forms and Documents.
        ![](/help/assets/screenshot2028114029.png)

    1. Click **Create** > **Adaptive Form**.
        ![](/help/assets/screenshot2028114629.png)

    1. Select the **Blank with Core Components** template from the template selection screen as shown below:
    ![](/help/assets/screenshot202023-03-0120at206.09.1520pm.png)

    1. Click the **Style** tab and select the **wknd-theme** theme as shown below:
    ![](/help/assets/screenshot202023-03-0120at206.09.2320pm.png)

    1. Click the **Submission** tab and select the **Submit to REST end-point** card and specify the public bin in the **URL for the POST request** field as shown below:
    ![](/help/assets/screenshot202023-03-0120at206.09.5320pm.png)

    1. Click **Create**. Specify a name and title on your form. For example, **registration**. Click **Create**.

    1. The adaptive form editor opens. Dismiss any pop-ups or dialogs for preferences or information. Click the components browser on the left rail and add the **Header** and **Footer** components respectively to the top and bottom of the blank form.
     ![](/help/assets/screenshot2028121929.png)

    1. Drag and drop components from the Components browser to create a form, similar to the following:

        ![](/help/assets/screenshot2028115129.png){width="50%" align="left"}

1. Add validations to the form:

    1. Click the **Phone number** component so that the pop-up menu is displayed. Click the **Wrench icon** in the menu to configure the field.

    1. Open the **validations tab**, mark the field **Required**, and click **Done**. The success message is displayed.
        ![](/help/assets/screenshot2028123529.png){width="50%" align="left"}
        
        ![](/help/assets/screenshot2028123629.png){width="50%" align="left"}

1. Preview and submit the form.

    1. Click **Preview** to preview the form from an end-user perspective.

    1. Fill the form with dummy data.

    1. Submit the form.
        ![](/help/assets/screenshot2028125729.png)

    1. In the Request bin tab, check the submitted data.
        ![](/help/assets/screenshot2028125829.png)

1. Add interactivity to the form with rules:

    1. Click the **Check the box to receive 5% off** component. On the options toolbar, click the Rules icon. The Rule editor option opens. 
    
    1. Create a rule, when the **Check the box to receive 5% off** option is selected, the options for applying credit card is disabled.

1. Publish the form.

    1. Open AEM Forms management interface, for example, `https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/forms.html/content/dam/formsanddocuments`, and select the form.
    
    1. Click **Publish**.

        ![](/help/assets/screenshot2028115629.png)
    
        The success message is displayed.

        ![](/help/assets/screenshot2028115729.png)

        The published URL of the form would be similar to `https://publish-p105303-e986623.adobeaemcloud.com/content/forms/af/registration.html`.

    1. To view the published form, replace the program ID (pXXXXXX) and environment ID (eXXXXXX) in the above URL with the IDs of your
    environment.

## Lesson 3

### Objective

Update styles using frontend development best practices.

### Lesson context

In this lesson, as a front-end developer, you learn how you can update styling for the previously created adaptive form easily.

### Exercise

Set up a local repository of the theme:

1. Open the Command Prompt or shell with administrator rights:

    ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. On the Command Prompt, use the following command to navigate to **c:\git** folder
    
    ```Shell
    
    cd c:\git
    
    ```

1. Use the following command to clone the theme frontend code:
    
    ```Shell
    
    git clone -b WKND https://github.com/adobe/aem-forms-theme-canvas

    ```
    

1. Use the following command in the listed order to navigate to the **aem-forms-theme-canvas** directory and open Visual Studio Code.
    
    ```Shell
    
    cd aem-forms-theme-canvas
    code .

    ```
    
    ![](/help/assets/screenshot2028126029.png)

1. Select **Trust the authors of all files in the parent folder** and click **Yes, I trust the authors**.

    ![](/help/assets/screenshot2028116229.png){width="50%" align="left"}

1. To render the form hosted on your cloud service publish environment, rename the `env_template` file.  To rename the file, right click the **env_template** file and select the **Rename** option.

    ![](/help/assets/screenshot2028116429.png){width="50%" align="left"}

     </br>

    ![](/help/assets/screenshot2028116529.png){width="50%" align="left"}

1. Set the following values for the variables in the .env file and save the file:

    * **AEM_URL**: Specify your cloud service publish environment. For example, `https://publish-p105303-e986623.adobeaemcloud.com/`
    
    * **AEM_ADAPTIVE_FORM**: Specify the path of the form. For example, if the form path is `/content/forms/af/registration`, the value of this variable would be `registration`.

        ![](/help/assets/screenshot2028116429.png){width="50%" align="left"}

1. Create a local user in the AEM environment.

    >[!NOTE]
    > To create a local user, Go to `AEM Home` > `Tools` > `Security` > `Users`. 
    > Ensure that the user is a member of the forms-users group.
    

1. In the Command Prompt window, run the following command:

    ```Shell

    npm install

    ```

    ![](/help/assets/screenshot2028117029.png)

    >[!NOTE]
    >
    > * If you get a message asking to update `npm` through the `npm notice Run npm nstall -g npm@9.6.0` command, ignore the message.
    > * Unless you are instructed in the workbook, do not run other `npm` commands.

1. Now, run the following command to preview the form.
    
    ```Shell
    
    npm run live
    
    ```
    
    ![](/help/assets/screenshot2028117229.png)

    Once the above command is executed, wait for the `webpack compiled` message and you are redirected to a AEM login page.
    
1. Click **Sign in Locally (Admin Tasks only)** on the AEM login page.
1. Enter the credentials for the created local user and the form is displayed in a browser tab.

    >[!NOTE]
    >
    >If you experience a blank screen in browser after executing the `npm run live` command for more than 3-4 minutes, change `localhost` in browser URL to 127.0.0.1 and hit **Enter**. 

    
    ![](/help/assets/screenshot2028115129.png){width="50%" align="left"}


1. In Visual Studio Code, open the `PROJECT\src\site\_variables.scss` file. Notice the `$error` color is a shade of RED.

    ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. In the browser, submit the form to see the Red color in the **First Name** field.

    ![](/help/assets/screenshot2028120829.png)

1. Set the **$error** color to **#5736eb** and save the file. 

    ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. Refresh the browser and submit the form. Notice that the error color on the first name field has changed accordingly.
    
    ![](/help/assets/screenshot2028121129.png)

1. In the Command Prompt, press **CTRL+C**, enter **Y**, and press the **Enter** key to terminate the npm process. It is important to stop the npm server so it does not conflict with the next set of exercises.
1. Close Visual Studio Code and Command Prompt windows.

## Lesson 4

### Objective

Render the form to Web/mobile and other interfaces as a headless form.

### Lesson context

In this lesson, as a frontend developer, you learn how you can render the adaptive form created previously as a headless form using a React spectrum design framework.

### Exercise

Set up a local repository using the React starter project:

1. Open the Command Prompt using administrator rights.

    ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. On the Command Prompt, use the following command to navigate to **c:\git** folder

    ```Shell
    
    cd c:\git

    ```

1. Use the following command to clone the adaptive form React starter project:
    
    ```Shell
    
    git clone https://github.com/adobe/react-starter-kit-aem-headless-forms

    ```
    
    ![](/help/assets/screenshot2028117329.png)

1. Use the following commands in the listed order to navigate to the **react-starter-kit-aem-headless-forms** directory and open Visual Studio Code.

    ```Shell
    
    cd react-starter-kit-aem-headless-forms

    code .

    ```
    
    ![](/help/assets/screenshot2028117529.png)
    

    The Visual Studio Code window opens.

    ![](/help/assets/screenshot2028117429.png){width="50%" align="left"}

To render the form hosted on your cloud service publish environment:

1. Rename the env_template file to the .env file. To rename, right-click the **env_template** file and select the **Rename** option. 
    
    ![](/help/assets/screenshot2028117629.png){width="50%" align="left"}
    
    ![](/help/assets/screenshot2028117729.png)

1. Set the following values for the variables in the .env file. After updating the variables, save the file.
    * **AEM_URL**: Specify the URL of the cloud service publish environment. For example, `https://publish-p105303-e986623.adobeaemcloud.com`

    * **AEM_FORM_PATH**: Specify the path of the adaptive form created in the previous lesson. For example, `/content/forms/af/registration/`

        ![](/help/assets/screenshot202023-03-0820at202.49.1820pm.png)

1. Open the command window, ensure you are at the **react-starter-kit-aem-headless-forms** directory, and run the following command:

    ```Shell
    
    npm install
    
    ```

    ![](/help/assets/screenshot2028118029.png)


1. In the Command Prompt window, run the following command:
    
    ```Shell

    npm start
    
    ```

    ![](/help/assets/screenshot2028118129.png)

    The above command starts a local development server which would render the form definition fetched from AEM in a headless way using the React spectrum frontend library.

    >[!NOTE]
    >
    > 
    > If you experience a blank screen in browser after executing the `npm start` command for more than 3-4 minutes, change `localhost` in browser URL to 127.0.0.1 and hit **Enter**. 

    ![](/help/assets/screenshot2028118229.png)

Let's check the execution of the rules in this headless form:

1. Select the **Check the box to receive 5% off** option. The subsequent option for applying for a credit card is disabled.

    ![](/help/assets/screenshot2028126229.png)

1. Uncheck **Check the box to receive 5% off** to enable the credit card option.

    ![](/help/assets/screenshot2028126329.png)

Let's make changes on the form on the server as a business user and view changes reflected in the headless form automatically.

1. Open the AEM Forms management interface in the browser. <!-- URL is 404. Consider saying the path is for illlustration purposes only. For example, [https://author-p105303-e986623.adobeaemcloud.com/ui#/aem/aem/forms.html/content/dam/formsanddocuments](https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/forms.html/content/dam/formsanddocuments). -->

1. Select the **`contactus`** form and click **Edit.** It opens the form in the adaptive forms editor.


1. Select the **Phone number** field and click the **Edit icon (Pencil icon)** in the toolbar. If you are not able to see the pop-up toolbar, switch to Edit mode. Click the **Edit** button in top right, left to **Preview** button.

    ![](/help/assets/screenshot2028119629.png)

1. Change the label to Mobile Number. Click any empty space in the form and the changes made to the form are saved.

      ![](/help/assets/screenshot2028119729.png)

Let's publish the updated form to propagate the changes to the published environment.

1. In the AEM Forms management interface tab, select the registration form, and click **Unpublish**. If you do not see the **Unpublish** button, skip to step 3 to publish the changes directly.

1. Click **Unpublish**. Click **Close** in the respective dialog.
    
1. After the browser refreshes, select the registration form and click **Publish**.

1. Click **Publish**. Click **Close** in the respective dialog.

1. Refresh the browser tab with the headless form displayed. Notice, the Phone number label has changed to Mobile Number.

    ![](/help/assets/screenshot2028120529.png)

1. Open the Command Prompt window that is used to start the **react-starter-kit-aem-headless-forms** project, press **CTRL+C**, then
    enter **Y** and press Enter key to terminate the npm process. It is important to stop the npm server so it does not conflict with the next set of exercises.

1. Close Visual Studio Code and Command Prompt windows.


## Lesson 5

### Objective

Render the form as a headless form using Google Material UI

### Lesson context

In this lesson, as a front-end developer, you learn how to render the adaptive form created previously as a headless form using Google Material UI.

### Exercise

Set up a local repository using the Material UI starter project:

1. Open the Command Prompt using administrator rights.
    
    ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}


1. On the Command Prompt, use the following command to navigate to **c:\git** folder:

    ```Shell

    cd c:\git

    ```

1. Run the following commands in the listed order to create a folder named `mui` and navigate to the `mui` folder using following commands: 

    ```Shell

    mkdir mui

    cd mui
    
    ```

1. Use the following command to clone the adaptive form React starter project: 

    ```Shell

    git clone -b mui-lab https://github.com/adobe/react-starter-kit-aem-headless-forms

    ```

    ![](/help/assets/screenshot2028126529.png)

1. Use the following command in the listed order to navigate to the **react-starter-kit-aem-headless-forms** folder and open the code in Visual Studio Code:

    ```Shell

    cd react-starter-kit-aem-headless-forms

    code .

    ```

    ![](/help/assets/screenshot2028126829.png)

To render the form hosted on your cloud service publish environment:

1. Rename the **env_template** file to the **.env** file. To rename, right-click the **env_template** file and select **Rename**.

    ![](/help/assets/screenshot2028126629.png){width="50%" align="left"}

1. Set the following values for the variables in the .env file. After updating the variables, save the file. Use the **CTRL + S** switch combination to save the file. 

    * **AEM_URL**: Specify the URL of the cloud service publish environment. For example, [https://publish-p105303-e986623.adobeaemcloud.com](https://publish-p105303-e986623.adobeaemcloud.com/)

    * **AEM_FORM_PATH**: Specify the path of the adaptive form created in the previous lesson. For example, /content/forms/af/registration/

        ![](/help/assets/screenshot2028126929.png) 

1. Open the command window, ensure you are at the **react-starter-kit-aem-headless-forms** directory, and run the following command:

    ```Shell
    
    npm install
    
    ```

    ![](/help/assets/screenshot2028127029.png)

1. In the Command Prompt window, run the following command:
    
    ```Shell

    npm start
    
    ```

    ![](/help/assets/screenshot2028127129.png)
    
    The command starts a local development server and renders the form definition fetched from AEM in a headless way using the Google
    Material UI frontend library.

    >[!NOTE]
    >
    >If you experience a blank screen in browser after executing the `npm start` command for more than 3-4 minutes, change `localhost` in browser URL to 127.0.0.1 and hit **Enter**. 

    ![](/help/assets/screenshot2028127229.png)

1. To evaluate the execution of the same business logic in this form rendition: 

    Select **Check the box to receive 5% off**. The subsequent option **Would you like to apply for `We.Finance` Corporate Credit Card Form?** gets disabled.

    ![](/help/assets/screenshot2028127329.png){width="50%" align="left"}

## Lesson 6

### Objective

Create an alternate look and feel of the headless form using Material UI component variations

### Lesson context

In this lesson, as a front-end developer, you learn how to create an alternate representation of different components. You use Material UI for the adaptive form created previously by the business user.

### Exercise

Update the variation of components in the headless project. To change the variant of the material UI text input component to `OutlinedInput`: 

1. In Visual Code, navigate to the text input component by opening the `index.tsx` file at `src/components/textinput/index.tsx`.

1. Add `//` at the beginning of the code line 103. It converts the line to a comment. 

    ```Shell

    //const Cmp = \'outlined\' === appliedCssClassNames ? OutlinedInput: Input;

    ```

1. Add the following at line 104 to use a different variant of the component and save the file. Use the **CTRL + S** switch combination to save the file. 

    ```Shell
    
    const Cmp = OutlinedInput;

    ```

    ![](/help/assets/screenshot2028127629.png)

    It is essential to use correct capitalization for the 'OutlinedInput' variant else the compilation would fail. The local development environment compilation begins automatically in Command Prompt. Wait until you see the following message

    `webpack 5.75.0 compiled with 3 warnings in 6659 ms` 
    `inside proxy req`
    `setting new origin header`

1. Refresh the browser, if it does not refresh automatically, to see the text input component use a different variant.

    ![](/help/assets/screenshot2028127729.png)

    
    This change happens for end users without any change to form definition at AEM Forms Server and is specific for the headless
    channel under consideration. For example, a web channel in this lab.
    
    ![](/help/assets/screenshot2028127529.png){width="50%" align="left"}


1. Close Visual Studio Code and Command Prompt windows.

## Frequently Asked Questions (FAQs)

+++ Is Adaptive Form Wizard available publicly?  

Yes, it is available with AEM Forms as Cloud Service.

+++


+++ Are core components available publicly?  

Yes, Adaptive Forms core components are available with AEM Forms as Cloud Service.

+++

+++ Are Headless forms available publicly?  

Yes, Headless forms are available with AEM Forms as Cloud Service.

+++

+++ Do Headless forms require a separate license?  

No, Headless forms use the same licensing value metric, number of form submissions.

+++

+++ Are core components and Headless forms available with AEM 6.5 Forms?  

Yes, both adaptive forms core components and headless forms are available with AEM Forms 6.5 Service Pack 16 and onwards. 

+++


## Next steps

You now know how to build adaptive forms and deliver them across channels with headless forms. Use those skills to create scalable, high-quality data-capture experiences wherever your users are.


## Resources

* [Adaptive Form core components introduction](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/adaptive-forms/introduction)

* [Create an adaptive form using core components](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components)

* [Update styling for core component-based AF](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)

* [Headless adaptive forms](https://experienceleague.adobe.com/en/docs/experience-manager-headless-adaptive-forms/using/overview)

* [Using a Headless React starter kit](https://experienceleague.adobe.com/en/docs/experience-manager-headless-adaptive-forms/using/get-started/create-and-publish-a-headless-form)
