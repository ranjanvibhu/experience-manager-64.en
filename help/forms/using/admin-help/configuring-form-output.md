---
title: Configuring form output
seo-title: Configuring form output
description: Learn how to configure form output.
seo-description: Learn how to configure form output.
uuid: 70aad14e-c845-4ef3-a751-ad8860d5d505
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 17c9b69a-3c6f-47e3-a828-841bb90eba8b
exl-id: b19cae88-a549-41ba-b4a6-4b065a995296
---
# Configuring form output{#configuring-form-output}

## Specify the type of HTML output returned to the web browser {#specify-the-type-of-html-output-returned-to-the-web-browser}

1. In administration console, click Services &gt; forms.
1. Under Form Output, in the Output type list, select one of the following options:

   **Full HTML:** To render the form within full HTML tags (a complete HTML page). This value is the default.

   **Form body:** To render the form within `<BODY>` tags (not a complete HTML page).

1. Click Save.

## Specify the location where PDF content is rendered {#specify-the-location-where-pdf-content-is-rendered}

1. Under Form Output, in the Render at list, select one of the following options:

   **Client:** To render PDF forms within Adobe Acrobat or Adobe Reader. Client-side rendering improves the performance of AEM forms and applies only to PDFForm transformation.

   **Server:** To render PDF forms on the application server.

   **Auto:** To render the PDF form in the location specified by the `dynamicRender` configuration value of the XDP file. This value is the default.

1. Click Save.

## Configuring invocation of custom scripts before form submit {#configuring-invocation-of-custom-scripts-before-form-submit}

Perform the following steps to enable the feature:

1. Login to the administration console.
1. Go to **Services** &gt; **forms**.
1. Specify the Output type as Form Body.
1. Save the settings.
1. Declare a JavaScript variable, __CUSTOM_SCRIPTS_VERSION, in the head section of the HTML code and set its value to 1.

   >[!NOTE]
   >
   >*To disable the feature, you can remove the JavaScript variable or set its value to 0.*
