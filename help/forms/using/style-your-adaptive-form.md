---
title: Style your adaptive form 
seo-title: Style your adaptive form 
description: Learn to create a custom theme, style individual components, and use web fonts in a theme 
seo-description: Learn to create a custom theme, style individual components, and use web fonts in a theme 
page-status-flag: de-activated
uuid: ffb2cc22-baaf-4525-a2e3-29f39271c670
topic-tags: introduction
discoiquuid: 655303a4-99bb-4ba3-9d50-a178f5edcf85
feature: Adaptive Forms
exl-id: 0ccf43eb-f0c6-4204-8325-f891caa8f5af
---
# Style your adaptive form {#do-not-publish-style-your-adaptive-form}

Learn to create a custom theme, style individual components, and use web fonts in a theme 

 ![](do-not-localize/08-style_your_adaptiveformmain.png) 

This tutorial is a step in the [Create Your First Adaptive Form](create-your-first-adaptive-form.md) series. It is recommended to follow the series in chronological sequence to understand, perform, and demonstrate the complete tutorial use case.

## About the tutorial  {#about-the-tutorial}

You can use themes to provide a unique appearance and style to an adaptive form. You can apply out of the box themes provided with adaptive forms editor or create custom themes of your own. AEM Forms provide a [theme editor](themes.md) to create custom themes. A single theme can provide the different appearance to the same adaptive form opened on mobile, tablet, or desktop. Any prior knowledge of CSS or LESS is not required to use theme editor but it is desired.

By the end of the tutorial, you will learn to:

* Apply an out of the box theme to an adaptive form
* Create a theme for adaptive form using the theme editor
* Style individual components
* Bonus Section: Use web fonts in a custom theme

The form will look similar to the following after you complete the tutorial:

![Form with a custom theme](assets/styled-adaptive-form.png) 

## Before you start {#before-you-start}

Download the header-style and logo images, given below, on your local machine. The header of the `shipping-address-add-update-form` adaptive form uses the header-style and logo images. The header-style image appears on the right side of the header.

[Get File](assets/header-style.png)

[Get File](assets/logo-1.png)

## Step 1: Apply a theme to your adaptive form {#step-apply-a-theme-to-your-adaptive-form}

Adaptive forms editor provides multiple out-of-the-box themes. If you plan not to use a custom style for your adaptive form, you can also publish your adaptive forms with an out-of-the-box theme. Themes are independent of adaptive forms. You can apply the same theme to multiple adaptive forms. To apply a theme to an adaptive form:

1. Open the adaptive form for editing.

   [http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html](http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html) 

1. Open properties of **Adaptive Form container**. In the properties browser, navigate to **Basic** &gt; **Adaptive Form Theme**. The **Adaptive Form Theme** field lists all the out-of-the-box and custom themes. By default, the Canvas theme is applied.
1. Select a theme from the **Adaptive Form Theme** field. For example, **Survey theme**. Tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) to apply the selected theme.

![Adaptive form with the default theme](assets/default-adaptive-form.png)

**Figure:** *Adaptive form with the default theme*

![Adaptive form with the Survey theme](assets/adaptive-form-with-survey-theme.png)

**Figure:** *Adaptive form with the Survey theme*

## Step 2: Update your adaptive form {#step-update-your-adaptive-form}

The design displayed above requires changes in placeholder text and logo of your existing adaptive form. Perform the following steps to make the required changes:

1. Change the existing logo and text of the header. To remove the logo:

    1. Open the form in form editor.

       [http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html](http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html)
    
    1. Tap logo image in the header component and tap ![cmppr](assets/cmppr.png) properties. In the image property, tap X to remove the existing logo image.
    1. Tap upload, select the logo.png, and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) to save the changes. The image was downloaded in the [Before you start](/help/forms/using/style-your-adaptive-form.md#before-you-start) section. 
    1. Tap header text, `We.Retail`, and tap ![aem_6_3_edit](assets/aem_6_3_edit.png) **edit**. Change header text to `we retail`. Apply bold formatting only to `we`in `we retail`.

   ![we-retail-logo-text](assets/we-retail-logo-text.png)

1. Remove title and add placeholder text:

    1. Tap the Customer ID field and tap ![cmppr](assets/cmppr.png) properties.
    1. Copy the content of the **Title** field to the **Placeholder Text** field.
    1. Delete the content of the **Title** field and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).
    1. Repeat the previous three steps for all the text boxes, numeric box, and email field in the form.

   ![updated-adaptive-form](assets/updated-adaptive-form.png)

## Step 3: Create a custom theme for your adaptive form {#step-create-a-custom-theme-for-your-adaptive-form}

You can use [theme editor](/help/forms/using/themes.md) to create custom themes. The theme editor is an all-powerful WYSIWYG editor. It is a visual method to apply CSS to various components of an adaptive form. It provides finer controls to style components and panels of an adaptive form.

A theme is a separate entity like adaptive forms. It contains styles (CSS) for the components and panels of an adaptive form. Styles include CSS properties such as background colors, state colors, transparency, alignment, and size. When you apply a theme, the specified style is applied to the corresponding components of an adaptive form.

In this tutorial, you will style header and footer, text and numeric components, attachment component, and buttons. Let’s start with creating a theme:

### Create a theme {#create-a-theme}

1. Log in to the AEM author instance and navigate to **Adobe Experience Manager** &gt; **Forms** &gt; **Themes**. The default URL is [http://localhost:4502/aem/forms.html/content/dam/formsanddocuments-themes](http://localhost:4502/aem/forms.html/content/dam/formsanddocuments-themes). 
1. Tap **[!UICONTROL Create]** and select **[!UICONTROL Theme]**. The Create Theme page with the fields required to create a theme appears. The Title and Name fields are mandatory:

    * **Title:** Specify a title of the theme. For example, **Global Theme.** The title helps you identify the theme from the list of themes.
    * **Name:** Specify the name of the theme. For example, **Global-Theme.** A node with the specified name is created in the repository. As you start typing a title, value for the name field is automatically generated. You can change the suggested value. The name field can include only alphanumeric characters, hyphens, and underscores. All the invalid inputs are replaced with a hyphen.

1. Tap **Create**. A theme is created and a dialog to open the form for editing appears. Tap **Open** to open the newly created theme in a new tab. The theme opens in theme editor. For styling, the theme editor uses an out-of-the-box adaptive form shipped with AEM Forms.

   For information about using theme editor UI, see [About the theme editor](/help/forms/using/themes.md#aboutthethemeeditor).

1. Tap **Theme Options** ![theme-options](assets/theme-options.png) > **Configure**. In the **Preview Form** field, select the **shipping-address-add-update-form** adaptive form, tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png), tap **Save**. Now, the theme editor is configured to use your own adaptive form instead of the default adaptive form. Tap **Cancel** to return to the theme editor.

   ![custom-theme](assets/custom-theme.png)

   **Figure:** *Theme editor with the shipping-address-add-update-form adaptive form*

   ![create-a-theme](assets/create-a-theme.png)

   **Figure:** *Adaptive form with the default form*

### Style header and footer {#style-header-and-footer}

Header and footer provide a consistent and distinctive look to an adaptive form. Generally, the header contains logo and name of the organization, the footer contains copyright information, and these remain identical across multiple forms of an organization. To style header and footer of the shipping-address-add-update-form adaptive form:

1. Navigate the **Header** &gt; **Text** option in the Selectors panel. The Selectors panel is on the left of the theme editor. If the panel is not visible, tap ![Toggle side panel](assets/toggle-side-panel.png) Toggle Side Panel.  

1. Set the following properties in the **Text** accordion and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png). 

   | Property |Value |
   |---|---|
   | Font Family |Arial |
   | Font Color |FFFFFF |
   | Font Size |54px |

1. Tap the header widget and tap **Header**. The options to style the Header widget appear on the left. Expand the **Dimensions & Position** accordion, set the **Height** to `120px`, and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).
1. Expand the Background accordion of the header widget, set the **Background Color** to `F6921E.`

   Hover over **Image & Gradient** &gt; **+ Add**, tap **Image**. Set the following properties and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

   | Property |Value |
   |---|---|
   | image |Upload the header-style.png. The image was downloaded in the [Before you start](/help/forms/using/style-your-adaptive-form.md#before-you-start) section. |
   | Position |Right Bottom |
   | Tiling |No Repeat |

1. In the theme editor, tap the logo in the header and tap **Header Logo**. Expand the Dimensions & Position accordion, set the following properties and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

<table> 
 <tbody> 
  <tr> 
   <td>Margin</td> 
   <td>Value</td> 
  </tr> 
  <tr> 
   <td>Margin</td> 
   <td> 
    <ul> 
     <li>Top: 1.5rem</li> 
     <li>Bottom: -35px</li> 
     <li>Left: 1rem<strong><br /> </strong></li> 
    </ul> <p><strong>Tip:</strong> Tap the <img src="assets/link.png"> link icon to provide different value to each field.<br /> </p> </td> 
  </tr> 
  <tr> 
   <td>Height</td> 
   <td>4.75rem</td> 
  </tr> 
 </tbody> 
</table>

1. Tap the footer widget and tap **Footer**. Expand the **Background** accordion, set the **Background Color** to `F6921E`, and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

### Style the data capture component and apply a background to the adaptive form {#style-the-data-capture-component-and-apply-a-background-to-the-adaptive-form}

You can use multiple components in an adaptive form to capture data. For example, text box and numeric box. You can provide identical style to all the data capture components or separate style for each component. In this tutorial, an identical style is applied to numeric boxes (Customer ID, ZIP Code) and text boxes (Customer ID, Name, Shipping Address, State, Email). To style the data capture components:

1. Tap the Customer ID field and tap the **Field Widget** option. Set the following properties and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

<table> 
 <tbody> 
  <tr> 
   <td>Accordion</td> 
   <td>Property</td> 
   <td>Value</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Color</td> 
   <td>A7A9AC</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Radius </td> 
   <td> 
    <ul> 
     <li>Top: 7px<br /> </li> 
     <li>Right: 7px<br /> </li> 
     <li>Bottom: 7px<br /> </li> 
     <li>Left: 7px<br /> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Family</td> 
   <td>Arial</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Color</td> 
   <td>939598<br /> </td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Size</td> 
   <td>18px</td> 
  </tr> 
  <tr> 
   <td>Dimensions and Position</td> 
   <td>Width</td> 
   <td>60%</td> 
  </tr> 
  <tr> 
   <td>Dimensions and Position</td> 
   <td>Margin</td> 
   <td> 
    <ul> 
     <li>Left: 10rem</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Tap on the empty area above the Customer ID field and tap **Responsive Panel Container**. Set the **Background** &gt; **Background Color** to F1F2F2. Tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

   ![](do-not-localize/responsive-panel-container.png)

### Style the buttons {#style-the-buttons}

You can use a custom theme to apply an identical style to all the buttons of the adaptive form and [inline styling](/help/forms/using/inline-style-adaptive-forms.md) to apply a style to a specific button. To style the buttons:

1. Tap the **Submit** button and tap the **Button** option. Set the following properties and tap ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png).

<table> 
 <tbody> 
  <tr> 
   <td>Accordion</td> 
   <td>Property</td> 
   <td>Value</td> 
  </tr> 
  <tr> 
   <td>Background</td> 
   <td>Background Color</td> 
   <td>F6921E</td> 
  </tr> 
  <tr> 
   <td>Border<br /> </td> 
   <td>Border Color</td> 
   <td>F6921E</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Radius </td> 
   <td> 
    <ul> 
     <li>Top: 7px<br /> </li> 
     <li>Right: 7px<br /> </li> 
     <li>Bottom: 7px<br /> </li> 
     <li>Left: 7px</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Text<br /> </td> 
   <td>Font Family</td> 
   <td>Arial</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Color</td> 
   <td>FFFFFF</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Size</td> 
   <td>18px</td> 
  </tr> 
 </tbody> 
</table>

1. [Apply the custom theme](/help/forms/using/style-your-adaptive-form.md#step-apply-a-theme-to-your-adaptive-form), Global Theme, to your adaptive form. If the style does not reflect on the adaptive form, clean the browser cache and try again.

   ![style-data-capture-components](assets/style-data-capture-components.png)

## Step 4: Style individual components {#step-style-individual-components}

Some styles apply to only a specific component. Such components are styled in adaptive forms editor.

1. Open the adaptive form for editing. [http://localhost:4502/editor.html/content/forms/af/shipping-address-add-update-form.html](http://localhost:4502/editor.html/content/forms/af/change-billing-shipping-address.html)
1. On the top bar, select the **Style** option.

   ![style-option](assets/style-option.png)

1. Tap the **Attach** button and tap the ![aem_6_3_edit](assets/aem_6_3_edit.png)icon. Set the following properties in the **Dimensions and Position** accordion:

   | Property |Value |
   |---|---|
   | Float |Left |
   | Width |10% |

1. Tap the **Government approved address proof** option and tap the ![aem_6_3_edit](assets/aem_6_3_edit.png)icon. Set the following properties:

<table> 
 <tbody> 
  <tr> 
   <td>Accordion</td> 
   <td>Property</td> 
   <td>Value</td> 
  </tr> 
  <tr> 
   <td>Dimensions &amp; Position</td> 
   <td>Float</td> 
   <td>Left</td> 
  </tr> 
  <tr> 
   <td>Dimensions &amp; Position</td> 
   <td>Width</td> 
   <td>73%</td> 
  </tr> 
  <tr> 
   <td>Dimensions &amp; Position</td> 
   <td>Padding</td> 
   <td> 
    <ul> 
     <li>Left: 10px</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Dimensions &amp; Position</td> 
   <td>Height</td> 
   <td>40px</td> 
  </tr> 
  <tr> 
   <td>Dimensions &amp; Position<br /> </td> 
   <td>Margin</td> 
   <td><br /> 
    <ul> 
     <li>Right: 2rem</li> 
     <li>Left: 10rem </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Background</td> 
   <td>Background Color</td> 
   <td>FFFFFF</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Width</td> 
   <td>1px</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Style</td> 
   <td>Solid</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Color</td> 
   <td>A7A9AC</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Radius</td> 
   <td>7px</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Family</td> 
   <td>Arial</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Color</td> 
   <td>BCBEC0</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Font Size</td> 
   <td>18px</td> 
  </tr> 
  <tr> 
   <td>Text</td> 
   <td>Line Height</td> 
   <td>2</td> 
  </tr> 
 </tbody> 
</table>

1. Tap the **Submit** button and tap the ![aem_6_3_edit](assets/aem_6_3_edit.png) icon. Set the following properties:

<table> 
 <tbody> 
  <tr> 
   <td>Accordion</td> 
   <td>Property</td> 
   <td>Value</td> 
  </tr> 
  <tr> 
   <td>Dimensions and Position</td> 
   <td>Float</td> 
   <td>Right</td> 
  </tr> 
  <tr> 
   <td>Dimensions and Position</td> 
   <td>Margin</td> 
   <td> 
    <ul> 
     <li>Top: 5rem</li> 
     <li>Right: 14rem</li> 
     <li>Bottom: 20px</li> 
     <li>Left: 20px<br /> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Background</td> 
   <td>Background Color</td> 
   <td>F6921E</td> 
  </tr> 
  <tr> 
   <td>Border</td> 
   <td>Border Color</td> 
   <td>F6921E</td> 
  </tr> 
 </tbody> 
</table>

   ![styled-adaptive-form-1](assets/styled-adaptive-form-1.png)

## Step 5: Bonus Section: Using web fonts in a custom theme {#step-bonus-section-using-web-fonts-in-a-custom-theme}

You can use various fonts to design an adaptive form. All the devices that the adaptive form is viewed on may not have the fonts used to design the adaptive form. You can use a web font service to deliver required fonts to the target device.

Adobe Typekit is a web fonts service. You can configure and use the service with adaptive forms. To use Adobe Typekit in an adaptive form:

>[!NOTE]
>
>![typekit-to-adobe-fonts](assets/typekit-to-adobe-fonts.png) Typekit is now called Adobe Fonts and is included with Creative Cloud and other subscriptions. [Learn more](https://fonts.adobe.com/).

1. Create an [Adobe Typekit](https://typekit.com/) account, create a kit, add font Myriad Pro to the kit, publish the kit, and obtain the Kit ID. It is required to use Adobe Typekit fonts (Web fonts) in an adaptive form. 
1. In the AEM Forms server, navigate to ![adobeexperiencemanager](assets/adobeexperiencemanager.png) **Adobe Experience Manager** > **Tools** ![hammer](assets/hammer.png) > **Deployment** > **Cloud Services**. On the Cloud Services page, navigate to **Third Party Services** > **Typekit**, and click **Configure** Now under Typekit. If a configuration is already available, click the + button to create a new instance.

   On the Create Configuration dialog, specify a **Title** for the configuration, and click **Create**. You are redirected to the configuration page. In the Edit Component dialog that appears, provide your **Kit ID** and click **OK**.

1. Configure your theme to use the TypeKit configuration. On the author instance, open **Global Theme** in the theme editor. In the theme editor, navigate to Theme Options ![theme-options](assets/theme-options.png) > Configure. In **Typekit Configuration** field, select the kit, and click **Save**.

   The fonts added to the Typekit are available for selection in the **Text** accordion of all the components.
