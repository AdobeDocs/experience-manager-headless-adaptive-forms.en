---
title: Mobile forms best practices
description: For mobile and offline form use cases, build your own native app and fetch form definitions via the Headless Adaptive Forms API. Recommended approach for native mobile applications.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: mobile forms, native app, offline forms, headless API
hide: no
exl-id: b8e2f1a4-5c6d-4e2a-9f3b-1d4e5a6c7b8d
---
# Mobile forms best practices {#mobile-forms-best-practices}

For mobile and offline form use cases, the recommended approach is to build your own native app and fetch form definitions via the Headless Adaptive Forms API. This gives you full control over the mobile experience and ensures ongoing support as mobile platforms evolve.

## Recommended approach {#recommended-approach}

Build a native mobile application (iOS or Android) that:

1. **Fetches the headless form definition** – Use the [Headless Adaptive Forms APIs](https://opensource.adobe.com/aem-forms-af-runtime/api/) to retrieve the form JSON on demand (for example, when the user opens a form or navigates to it in your app). You can list available forms and then fetch the form definition by ID.

2. **Renders the form in your app** – Use your preferred UI framework (for example, React Native, or native views) to render the form from the JSON. You can use the Forms Web SDK and existing Headless adaptive forms React components where they fit your stack, or build your own renderer that consumes the same JSON structure.

3. **Optionally supports offline** – Implement local storage and sync in your app. For example, cache form definitions when online, save drafts locally, and submit or sync data when the device is back online.

This approach keeps your app maintainable as Android and iOS change, and uses the supported Headless Adaptive Forms platform for form authoring, validation, and submission.

## Getting started {#getting-started}

* [AEM Headless adaptive forms overview](overview.md) – Capabilities and concepts.
* [Headless adaptive forms APIs](https://opensource.adobe.com/aem-forms-af-runtime/api/) – List, fetch, validate, and submit forms programmatically.
* [Architecture](architecture.md) – How Headless adaptive forms work and how front-end apps consume them.

For step-by-step integration, see [Create and publish a headless form](create-and-publish-a-headless-form.md) and the [Developer portal](https://experienceleague.adobe.com/landing/aem-headless-forms/developer.html?lang=en).
