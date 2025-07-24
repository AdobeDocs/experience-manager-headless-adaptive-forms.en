---
title: Enable Headless Adaptive Forms on AEM Forms as a Cloud Service
description: A step-by-step guide to enable Headless Adaptive forms in AEM Forms as a Cloud Service, simplifying setup and activation in your environment.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin
level: Beginner, Intermediate
contentOwner: Khushwant Singh
docset: CloudService
hide: yes
hidefromtoc: yes
exl-id: 7afff771-1296-4162-84c5-c8266b94af2f
---
# Enable Headless Adaptive Forms on AEM Forms as a Cloud Service {#enable-headless-adaptive-forms-on-aem-forms-cloud-service}

Enabling Headless Adaptive Forms on AEM Forms as a Cloud Service, allows you to start creating, publishing, and delivering Headless Forms using your AEM Forms Cloud Service instances to multiple channels. You require Adaptive Forms Core Components enabled environment to use Headless Adaptive Forms.

## Considerations 

* When you create a fresh AEM Forms as a Cloud Service program, [Headless Adaptive Forms are already enabled for your environments](#are-adaptive-forms-core-components-enabled-for-my-environment).

* If you are running an older Forms as a Cloud Service program where Core Components are [not enabled](#enable-components), first [add the Adaptive Forms Core Components dependencies](#enable-headless-adaptive-forms-for-an-aem-forms-as-a-cloud-service-environment) to your Cloud Service repository. Deploy the updated repository to each environment to enable Headless Adaptive forms.

* If your Cloud Service environment already lets you [create Core Components-based adaptive forms](create-a-headless-adaptive-form.md), Headless Adaptive forms are automatically enabled. You can then deliver those forms as headless experiences to mobile, web, native apps, or any service that requires them.

>[!NOTE]
>
>
> Adobe provides an Adaptive Forms [starter kit (React App)](create-and-publish-a-headless-form.md) to help developers start quickly with Headless Adaptive Forms development, without enabling Headless Adaptive Forms on AEM Forms as a Cloud Service environment. You can enable the Headless Adaptive Forms on a Forms as a Cloud Service environment later after a [quick hands-on with developing headless forms](create-and-publish-a-headless-form.md). 

## Enable Headless Adaptive Forms for an AEM Forms as a Cloud Service environment

Perform the following steps, in the listed order, to enable Headless Adaptive Forms for an AEM Forms as a Cloud Service environment

<!-- Missing image ALT tag -->
![](/help/assets/enable-headless-adaptive-forms-on-aem-forms-cloud-service.png)


## 1. Clone your AEM Forms as a Cloud Service Git Repository {#clone-git-repository} 
    
1. Log in to [Cloud Manager](https://my.cloudmanager.adobe.com/) and select your organization and program.

1. Navigate to the **Pipelines** card from your **Program Overview** page.

1. Click the **Access Repo Info** button to access and manage your Git Repository. The page includes the following information:

    * URL to the Cloud Manager Git Repository.
    * Credentials of the Git Repository (Username and Password) Git username.

    Click **Generate Password** to view or generate the password. 
    
1. Open terminal or command prompt on your local computer and run the following command:

    ```Shell 

    git clone [Git Repository URL]

    ```

    When prompted, provide the credentials. The repository is cloned to your local computer.  

    
## 2. Add Adaptive Forms Core Components dependencies to your Git Repository {#add-adaptive-forms-core-components-dependencies}

1. Open your Git Repository folder in a plain text code editor. For example, VS Code.
1. Open the `[AEM Repository Folder]\pom.xml` file for editing.
1. Replace versions of the `core.forms.components.version`, `core.forms.components.af.version` and `core.wcm.components.version` components with versions specified in [core components documentation](https://github.com/adobe/aem-core-forms-components). If the component does not exist, add these components. 
        
    ```XML

    <!-- Replace the version with the latest released version at https://github.com/adobe/aem-core-forms-components/tags -->

    <properties>
        <core.forms.components.version>2.0.14</core.formscomponents.version>
        <core.forms.components.af.version>2.0.14</core.forms.components.af.version>  
        <core.wcm.components.version>2.21.2</core.wcmcomponents.version>
    </properties>

    ```
     
    ![Mention latest version of Forms Core Components](/help/assets/latest-forms-component-version.png)

1. In the dependencies section of the `[AEM Repository Folder]\pom.xml` file, add the following dependencies, and save the file.

    ```XML

        <!-- WCM Core Component Examples Dependencies -->
            <dependency>
                <groupId>com.adobe.cq</groupId>
                <artifactId>core.wcm.components.examples.ui.apps</artifactId>
                <type>zip</type>
                <version>${core.wcm.components.version}</version>
            </dependency>
            <dependency>
                <groupId>com.adobe.cq</groupId>
                <artifactId>core.wcm.components.examples.ui.content</artifactId>
                <type>zip</type>
                <version>${core.wcm.components.version}</version>
            </dependency>
            <dependency>
                <groupId>com.adobe.cq</groupId>
                <artifactId>core.wcm.components.examples.ui.config</artifactId>
                <version>${core.wcm.components.version}</version>
                <type>zip</type>
            </dependency>    
            <!-- End of WCM Core Component Examples Dependencies -->
            <!-- Forms Core Component Dependencies -->
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-core</artifactId>
                <version>${core.forms.components.version}</version>
            </dependency>
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-apps</artifactId>
                <version>${core.forms.components.version}</version>
                <type>zip</type>
            </dependency>
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-af-core</artifactId>
                <version>${core.forms.components.version}</version>
            </dependency>
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-af-apps</artifactId>
                <version>${core.forms.components.version}</version>
                <type>zip</type>
            </dependency>
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-examples-apps</artifactId>
                <type>zip</type>
                <version>${core.forms.components.version}</version>
            </dependency>
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-examples-content</artifactId>
                <type>zip</type>
                <version>${core.forms.components.version}</version>
            </dependency>
    <!-- End of AEM Forms Core Component Dependencies -->

    ```

1. Open the `[AEM Repository Folder]/all/pom.xml` file for editing. Add the following dependencies in the `<embeddeds>` section and save the file.

    ```XML

    <!-- WCM Core Component Examples Dependencies -->

    <!-- inside plugin config of filevault-package-maven-plugin -->  
    <!-- embed wcm core components examples artifacts -->

    <embedded>
        <groupId>com.adobe.cq</groupId>
        <artifactId>core.wcm.components.examples.ui.apps</artifactId>
        <type>zip</type>
        <target>/apps/${appId}-vendor-packages/content/install</target>
    </embedded>
    <embedded>
        <groupId>com.adobe.cq</groupId>
        <artifactId>core.wcm.components.examples.ui.content</artifactId>
        <type>zip</type>
        <target>/apps/${appId}-vendor-packages/content/install</target>
    </embedded>
    <embedded>
        <groupId>com.adobe.cq</groupId>
        <artifactId>core.wcm.components.examples.ui.config</artifactId>
        <type>zip</type>
        <target>/apps/${appId}-vendor-packages/content/install</target>
    </embedded>
    <!-- embed forms core components artifacts -->
    <embedded>
        <groupId>com.adobe.aem</groupId>
        <artifactId>core-forms-components-af-apps</artifactId>
        <type>zip</type>
        <target>/apps/${appId}-vendor-packages/application/install</target>
    </embedded>
    <embedded>
        <groupId>com.adobe.aem</groupId>
        <artifactId>core-forms-components-af-core</artifactId>
        <target>/apps/${appId}-vendor-packages/application/install</target>
    </embedded>
    <embedded>
        <groupId>com.adobe.aem</groupId>
        <artifactId>core-forms-components-examples-apps</artifactId>
        <type>zip</type>
        <target>/apps/${appId}-vendor-packages/content/install</target>
    </embedded>
    <embedded>
        <groupId>com.adobe.aem</groupId>
        <artifactId>core-forms-components-examples-content</artifactId>
        <type>zip</type>
        <target>/apps/${appId}-vendor-packages/content/install</target>
    </embedded>

    ```

    >[!NOTE]
    >
    >
    >  Replace `${appId}` with your appId. 
    >
    >  To find your `${appId}`, in the `[AEM Repository Folder]/all/pom.xml` file, search the `-packages/application/install` term. The text before the `-packages/application/install` term is your `${appId}`. For example, the following code, `myheadlessform` is `${appId}`. 
    >
    >   ``` 
    >        <embedded>
    >            <groupId>com.myheadlessform</groupId>
    >            <artifactId>myheadlessform.ui.apps<artifactId>
    >            <type>zip</type>
    >           <target>/apps/myheadlessform-packages/application install</target>
    >        </embedded>
    >   ```

1. In the `<dependencies>` section of the `[AEM Repository Folder]/all/pom.xml` file, add the following dependencies, and save the file:

    ```XML

            <!-- Other existing dependencies -->
            <!-- wcm core components examples dependencies -->
            <dependency>
                <groupId>com.adobe.cq</groupId>
                <artifactId>core.wcm.components.examples.ui.apps</artifactId>
                <type>zip</type>
            </dependency>
            <dependency>
                <groupId>com.adobe.cq</groupId>
                <artifactId>core.wcm.components.examples.ui.config</artifactId>
                <type>zip</type>
                </dependency>
            <dependency>
                <groupId>com.adobe.cq</groupId>
                <artifactId>core.wcm.components.examples.ui.content</artifactId>
                <type>zip</type>
            </dependency>
                <!-- forms core components dependencies -->
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-af-apps</artifactId>
                <type>zip</type>
            </dependency>
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-examples-apps</artifactId>
                <type>zip</type>
            </dependency>
                <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>core-forms-components-examples-content</artifactId>
                <type>zip</type>
            </dependency>

    ```

1. Open the `[AEM Repository Folder]/ui.apps/pom.xml` for editing. Add the `af-core bundle` dependency, and save the file.
    
    ```XML

        <dependency>
        <groupId>com.adobe.aem</groupId>
        <artifactId>core-forms-components-af-core</artifactId>
        </dependency>

    ```

    >[!NOTE]
    >
    >Ensure that the following Adaptive Forms Core Components artifacts are not included in your project.
    >
    > `<dependency>`
    >
    >   `<groupId>com.adobe.aem</groupId>` 
    >   `<artifactId>core-forms-components-apps</artifactId>`
    >
    > `</dependency>`
    >
    > and
    >
    > `<dependency>`
    >
    >   `<groupId>com.adobe.aem</groupId>`
    >   `<artifactId>core-forms-components-core</artifactId>`
    >
    > `</dependency>`


1. Save and close the file. 

## 3.  Update the project to include the latest version of Forms Core Components: 

1. Open the [AEM Archetype Project Folder]/pom.xml for editing. 


1.  Save and close the file.  

## 4. Commit the updates to your Git Repository and run a pipeline to deploy the repository {#Commit-the-updates-to-your-git-repository}

1. To commit code to your Git Repository:
    1. Open the terminal or command prompt. 
    1. Navigate to your `[AEM Repository Folder]` and run the following commands in the listed order

        ```Shell
    
        git add pom.xml
        git add all/pom.xml
        git add ui.apps/pom.xml
        git commit -m "Added dependencies for Adaptive Forms Core Components"
        git push origin
    
        ```

1. After the files are committed to Git Repository, [Run the pipeline](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/using/code-deployment).  

    After the pipeline run is successful, Adaptive Forms Core Components are enabled for the corresponding environment. Also, an Adaptive Forms (Core Components) template and Canvas 3.0 theme are added to your Forms as a Cloud Service environment, providing you with options to customize and create Core Components based Adaptive Forms. 


## Frequently Asked Questions {#faq}

### What are the core components? {#core-components}

The [Core Components](https://experienceleague.adobe.com/en/docs/experience-manager-core-components/using/introduction) are a set of standardized Web Content Management (WCM) components for AEM to speed up development time and reduce the maintenance cost of your websites.

### What all capabilities are added on enabling core components? {#core-components-capabilities}

When the  Adaptive Forms Core Components are enabled for your environment, a blank Core Components based Adaptive Form template and Canvas 3.0 theme are added to your environment. After enabling Adaptive Forms Core Components for your environment, you can:

* Create Core Components based Adaptive Forms.
* Create Core Components based Adaptive Form templates.
* Create custom themes for Core Components based Adaptive Form templates.
* Serve Core Component based Adaptive Form's JSON representations to channels such as mobile, web, native apps, and services that require a form's headless representation.

### Are Adaptive Forms Core Components enabled for my environment? {#enable-components}

To check that Adaptive Forms Core Components are enabled for your environment:

1. [Clone your AEM Forms as a Cloud Service repository](#1-clone-your-aem-forms-as-a-cloud-service-git-repository). 

1. Open the `[AEM Repository Folder]/all/pom.xml` file of your AEM Forms Cloud Service Git Repository. 

1. Search for the following dependencies:
    
    * core-forms-components-af-core
    * core-forms-components-core
    * core-forms-components-apps
    * core-forms-components-af-apps
    * core-forms-components-examples-apps
    * core-forms-components-examples-content

    
    ![locate the core-forms-components-af-core artifact in all/pom.xml](/help/assets/enable-headless-adaptive-forms-on-aem-forms-cloud-service-locate-core-af-artifact.png)

    If the dependencies exist, Adaptive Forms Core Components are enabled for your environment.
