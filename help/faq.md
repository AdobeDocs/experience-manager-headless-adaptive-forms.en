---
title: Frequently Asked Questions About Headless Adaptive Forms
description: Frequently asked questions
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: headless, adaptive form, FAQ
hide: no
exl-id: 5bfc307d-96a3-4007-b65f-32176ecdb710
---
# Frequently asked questions (FAQ) {#headless-adaptive-forms-faq}

## Should I know React.js to use Headless adaptive forms?

You can use any framework, library, or language to render Headless adaptive forms and use Adobe's REST APIs to validate and submit the forms. The AF-core library, provided to you out-of-the-box, is framework independent. React-Render and React-componet libraries, also provided to you out-of-the-box, are for your convenience. You can build your own components; you are not limited to the ones provided.
 

<!-- 
## Did Adobe release a new AEM Archetype for Headless adaptive forms?

You can use Archetype 37 with flag `includeFormsheadless` or later flag to create an AEM project with Headless adaptive forms functionality. 

-->

## Do I require Forms as a Cloud Service sandbox to use Headless adaptive forms?

You can use the starter app to start developing and styling your Headless adaptive forms. You require Forms as a Cloud Service to host and serve Headless adaptive forms along with backend forms capabilities. 

<!-- ## Do I need an archetype project to develop Headless adaptive forms?

You can use the starter app to start developing and styling your Headless adaptive forms. Later on, you can use the 
archetype project to deploy the finished Headless adaptive forms and corresponding custom code, created using starter app, to Forms as a Cloud Service environment. The Forms as a Cloud Service environment helps you test and productionize the forms. -->

## Where can I get a preview of a Headless adaptive form? {#storybook-example}

You can use the starter app to render and preview a custom Headless adaptive form. You can also modify a [storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--introduction) example to preview a Headless adaptive form.

![](/help/assets/storybook-example.png)

## Is it possible to use Headless adaptive forms with custom frameworks?

Headless adaptive forms are based on [standard specification](/help/assets/headless-adaptive-forms-specification.pdf). You can extend the specification to use it to build custom components. For example, components for Chakra UI, Vue.js, and more.

## Do Headless adaptive forms support cascading fields?

In cascading fields, the content of the second field depends on the content chosen in the first field. The [Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/adaptive-form-dynamic-behaviour--options&args=formJson.items[0].fieldType:drop-down;formJson.items[0].minimum:!undefined;formJson.items[0].maximum:!undefined;formJson.items[0].label.value:Choose+number+of+options;formJson.items[0].enum[0]:1;formJson.items[0].enum[1]:2;formJson.items[0].enum[2]:3;formJson.items[1].fieldType:drop-down) provides an example of cascading fields.

## Do Headless adaptive forms allow prefilling forms with personalized data?

Headless adaptive forms allow prefilling forms with personalized data. The [Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--prefill-form-with-personalised-data) provides an example of how to prefill a Headless adaptive form.

<!-- >
## Can I use existing Adaptive Forms editor to create a Headless adaptive form?

At this moment, you use the Adaptive Form Editor to specify the JSON structure and set submit action for the forms. Support for drag-and-drop components, applying rules using editor, and more editor-related options would be available later in the beta phase. Keep a watch on release notes.  -->

## Can I use Headless adaptive forms with Angular SPA?

You can use the Web SDK to integrate Headless adaptive forms with Angular SPA. It is independent of any framework. You can use the React SDK as a reference. 

<!-- ## Should the `-r prerelease` switch be used every time to start the AEM SDK instance or only for the first time?

During the limited release program, use the `-r prerelease` switch every time you start the AEM SDK instance. 

## What is AEM Forms add-on (.far file) and how to install it?

Adobe Experience Manager Forms as a Cloud Service feature archive provides tools to create Headless adaptive forms on the local development environment. To install the feature archive, see [Setup development environment](setup-development-environment.md).

<!-- 
## Where do one get the license.properties file from?

You do not require a license.properties file to run AEM Cloud Service SDK. 

-->

## Is there any plugin to make development easier for Headless AF?

Yes — a Visual Studio Code extension lets you manually author headless adaptive forms in JSON.

## Can a Headless adaptive form connect to any CRM to read or write data?

You can use Microsoft Dynamics and Salesforce to submit or prefill a Headless adaptive form. Apart from CRMs, Headless adaptive forms support submit or prefill using REST endpoints, email, and custom submit actions.
