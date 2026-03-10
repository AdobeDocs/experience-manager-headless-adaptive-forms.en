---
title: Use custom components to render a headless form
description: Learn how to create custom components and map them to Headless Adaptive Forms fields. This guide explains how to map components by field type and resource type to achieve custom rendering and behavior.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: no
exl-id: 5aba1821-35dc-4da4-b188-d4853d64d5ee
---

# Use custom components to render a headless form {#developing-for-headless-forms-using-your-own-components}

In Headless Adaptive Forms, you can create and implement custom components to define the appearance and functionality of your forms. While the default components provide standard behavior, you might need specific UI elements or interactions—such as a custom "Announcement" component or a specialized "Scribble Signature" field.

This article guides you through creating a custom React component and mapping it to your Headless Adaptive Form.

## 1. Create a Custom React Component

First, create the React component that will render your form field. This component can use any React library (like Material UI, Ant Design, or your own custom styles).

For example, let's create a custom **Announcement** component that renders a read-only message with specific styling.

1.  Navigate to your React project's components directory (e.g., `src/components`).
2.  Create a new folder and file for your component, for example `Announcement/index.tsx`.
3.  Implement the component. It should accept `props` compatible with the Headless Forms runtime (typically receiving the state of the field).

```tsx
import React from 'react';
import { useRuleEngine } from '@aemforms/af-react-renderer';
import { FieldJson, State } from '@aemforms/af-core';

const Announcement = function (props: State<FieldJson>) {
    // The useRuleEngine hook connects the component to the form logic
    const [state, handlers] = useRuleEngine(props);

    if (!state.visible) {
        return null;
    }

    return (
        <div className="custom-announcement" style={{ border: '1px solid #ccc', padding: '10px', backgroundColor: '#f9f9f9' }}>
            <h3>{state?.label?.value}</h3>
            <p>{state?.default}</p>
        </div>
    );
}

export default Announcement;
```

## 2. Map the Custom Component

To use your custom component, you must map it in the `mappings.ts` file. The Headless Forms runtime uses this mapping to determine which React component to render for each field in the form JSON.

There are two primary ways to map components: by **Field Type** or by **Resource Type**.

### Mapping by Field Type

The standard mapping is based on the `fieldType` property in the Form JSON (e.g., `text-input`, `checkbox`, `button`). This is useful when you want to replace *all* instances of a standard component with your custom version.

1.  Open `src/utils/mappings.ts` (or wherever your mappings are defined).
2.  Import your custom component.
3.  Add it to the mappings object using the `fieldType` as the key.

```typescript
import { mappings } from "@aemforms/af-react-components";
import Announcement from "../components/Announcement";

const customMappings: any = {
  ...mappings,
  "text-input": Announcement // This would replace ALL text-input fields (use with caution)
};

export default customMappings;
```

### Mapping by Resource Type (Custom Components)

If you have created a custom component in AEM (e.g., an "Announcement" component extending a standard Text component) and you want to render *only* that specific component differently in your React app, you should map it by its **Resource Type** or a unique identifier.

This approach allows you to have standard Text components rendered normally, while your custom "Announcement" component uses your specialized React implementation.

1.  Identify the unique identifier for your component. In the Headless Form JSON, this is often found in the `:type` property or a custom `fieldType` if configured.
2.  Add the mapping using this identifier.

```typescript
import { mappings } from "@aemforms/af-react-components";
import Announcement from "../components/Announcement";

const customMappings: any = {
  ...mappings,
  // Map by resource type or custom identifier
  "my-project/components/announcement": Announcement
};

export default customMappings;
```

> **Note:** Ensure that your AEM Form model exports the correct `:type` or identifier that matches the key you use in `mappings.ts`.

## 3. Apply the Mappings

Finally, ensure your Headless Form instance uses these custom mappings.

```tsx
import React from 'react';
import { AdaptiveForm } from '@aemforms/af-react-renderer';
import customMappings from './utils/mappings';
import formJSON from './form-def.json';

function App() {
  return (
    <AdaptiveForm
      formJson={formJSON}
      mappings={customMappings}
    />
  );
}

export default App;
```

By following these steps, you can extend the capabilities of your Headless Adaptive Forms with components that match your specific design and functional requirements.
