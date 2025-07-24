---
title: Known Issues of Headless Adaptive Forms
description: Known issues of Headless adaptive forms.
keywords: headless, adaptive form, known issues
hide: yes
---

# Known issues {#known-issues}

* Edit, display, and data patterns are not supported. (CQ-4327047)
* minItems constraint cannot be changed dynamically. (CQ-4342499)
* Panel level validations if violated do not throw any error. (CQ-4342373)
* File validations if violated do not throw any error. (CQ-4342372)
* Custom properties are not dynamic. (CQ-4342376)
* Changing file data dynamically on a change event using expressions leads to an infinite loop. (CQ-4342377)
* The file attachment does not support Help text. (CQ-4342370)
* The required checkbox does not show error upon submit, if not selected. (CQ-4342371)
* aria-label is not added in the file attachment. (CQ-4341494)
