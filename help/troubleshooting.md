---
title: Headless Adaptive Forms Troubleshooting
description: Headless Adaptive Forms Troubleshooting
keywords: headless, adaptive form, Troubleshooting
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
index: true
exl-id: bfb7e688-d2be-4aaa-ac9b-147cbd74b516
TQID: https://experienceleague.adobe.com/yjO3VhNmqIAyfnD7daHB7eAEUNmaAjnUgEm0fHc1ArY
product_v2:
  - id: e8f6de9b-cf88-4405-8d10-15efa08c230e
    internal-label: Experience Manager Forms
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Troubleshooting 

## Unable to deploy the Archetype project on local development environment 

### Issue

When you use the `mvn -PautoInstallPackage clean install` or similar commands to deploy an AEM Archetype project, the project fails to deploy.

### Reason 

It can happen due to an unsupported version or corrupt installation of `node.js` or `NPM`.

### Solution

1. Completely [remove present installations of Node.JS](https://khushwantsehgal.wordpress.com/2022/06/28/how-to-remove-node-js-completely-from-windows-10/) from your environment.

1. Install `node.JS 16.13.0` or later with `NPM`.

1. Reboot your machine.


## The `mvn clean install` command fails to run

### Issue

When you use the `mvn clean install` or similar commands to deploy an AEM Archetype project, the command fails to run.

### Reason

It can happen if Git is not installed.

### Solution

Download and install the [latest release of Git](https://git-scm.com/downloads). If you are new to Git, see [Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
