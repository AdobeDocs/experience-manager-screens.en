---
title: Developing a Custom Component for AEM Screens
description: Learn how to create a custom component for AEM Screens.
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: developing
targetaudience: target-audience new
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: d14f8c55-dc09-4ac9-8d75-bafffa82ccc0
---
# Developing a Custom Component for AEM Screens {#developing-a-custom-component-for-aem-screens}

The following tutorial walks through the steps to create a custom component for AEM Screens. AEM Screens reuses many existing design patterns and technologies of other AEM products. The tutorial highlights differences and special considerations when developing for AEM Screens.

## Overview {#overview}

This tutorial is intended for developers who are new to AEM Screens. In this tutorial, a simple "Hello World" component is built for a Sequence channel in AEM Screens. A dialog box lets authors update the displayed text.

![overviewhellow](assets/overviewhellow.png)

## Prerequisites {#prerequisites}

To complete this tutorial the following is needed:

1. [AEM 6.5](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/release-notes/release-notes) plus Latest Screens Feature Pack.

1. [AEM Screens Player](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/configuring-screens-introduction)
1. Local Development Environment

The tutorial steps and screenshots are performed using **CRXDE-Lite**. IDEs can also be used to complete the tutorial. More information on using an IDE to develop [with AEM can be found here.](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup)


## Project Setup {#project-setup}

A Screens project's source code is typically managed as a multi-module Maven project. To expedite the tutorial, a project was pre-generated using the [AEM Project Archetype 13](https://github.com/adobe/aem-project-archetype). More details on [creating a project with Maven AEM Project Archetype can be found here](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/project-setup).

1. Download and install the following packages using [CRX Package Manager](http://localhost:4502/crx/packmgr/index.jsp):

   [Get File](assets/base-screens-weretail-runuiapps-001-snapshot.zip)

   [Get File](assets/base-screens-weretail-runuicontent-001-snapshot.zip)
   **Optionally** If working with Eclipse or another IDE, download the below source package. Deploy the project to a local AEM instance by using the Maven command:

   **`mvn -PautoInstallPackage clean install`**

   Start HelloWorld SRC Screens `We.Retail` Run Project.

   [Get File](assets/src-screens-weretail-run.zip)

1. In [CRX Package Manager](http://localhost:4502/crx/packmgr/index.jsp), verify that the following two packages are installed:

    1. **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip**
    1. **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip**

   ![Screens We.Retail Run Ui.Apps and Ui.Content packages installed by way of CRX Package Manager](assets/crx-packages.png)

   Screens `We.Retail` Run `Ui.Apps` and `Ui.Content` packages installed by way of CRX Package Manager.

1. The **screens-weretail-run.ui.apps** package installs code beneath `/apps/weretail-run`.

   This package contains the code responsible for rendering custom components for the project. This package includes component code and any JavaScript or CSS needed. This package also embeds **screens-weretail-run.core-0.0.1-SNAPSHOT.jar** that contains any Java&trade; code needed by the project.

   >[!NOTE]
   >
   >In this tutorial, no Java&trade; code is written. If more complex business logic is needed, back-end Java&trade; can be created and deployed using the Core Java&trade; bundle.

   ![Representation of the ui.apps code in CRXDE Lite](assets/uipps-contents.png)

   Representation of the ui.apps code in CRXDE Lite

   The **Hello World** component is just a placeholder. Over the course of the tutorial, functionality is added allowing an author to update the message displayed by the component.

1. The **screens-weretail-run.ui.content** package installs code beneath:

    * `/conf/we-retail-run`
    * `/content/dam/we-retail-run`
    * `/content/screens/we-retail-run`

   This package contains the starting content and configuration structure needed for the project. **`/conf/we-retail-run`** contains all configurations for the `We.Retail` Run project. **`/content/dam/we-retail-run`** includes starting digital assets for the project. **`/content/screens/we-retail-run`** contains the Screens content structure. The content of all of these paths is updated primarily in AEM. To promote consistency between environments (local, Dev, Stage, Prod) often a base content structure is saved in source control.

1. **Navigate to the AEM Screens > `We.Retail` Run project:**

   From the AEM Start Menu, click the Screens icon. Verify the `We.Retail` Run Project is seen.

   ![we-retaiul-run-starter](assets/we-retaiul-run-starter.png)

## Create the Hello World Component {#hello-world-cmp}

The Hello World component is a simple component that lets a user input a message to be displayed on the screen. The component is based on the [AEM Screens Component Template: https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template).

AEM Screens has some interesting constraints that are not necessarily true for traditional WCM Sites components.

* Most Screens components must run in full screen on the target digital signage devices
* Most Screens components must be embeddable in the sequence channels to generate slideshows
* Authoring should allow editing individual components in a sequence channel, so rendering them fullscreen is out of the question

1. In **CRXDE-Lite** `http://localhost:4502/crx/de/index.jsp` (or IDE of choice) navigate to `/apps/weretail-run/components/content/helloworld.`

   Add the following properties to the `helloworld` component:

   ```
       jcr:title="Hello World"
       sling:resourceSuperType="foundation/components/parbase"
       componentGroup="We.Retail Run - Content"
   ```

   ![Properties for /apps/weretail-run/components/content/helloworld](assets/2018-04-28_at_4_23pm.png)

   Properties for /apps/weretail-run/components/content/helloworld

   The **Hello World** component extends the **foundation, components, parbase** component so it can properly be used inside a Sequence channel.

1. Create a file beneath `/apps/weretail-run/components/content/helloworld` named `helloworld.html.`

   Populate the file with the following:

   ```xml
   <!--/*

    /apps/weretail-run/components/content/helloworld/helloworld.html

   */-->

   <!--/* production: preview authoring mode + unspecified mode (i.e. on publish) */-->
   <sly data-sly-test.production="${wcmmode.preview || wcmmode.disabled}" data-sly-include="production.html" />

   <!--/* edit: any other authoring mode, i.e. edit, design, scaffolding, etc. */-->
   <sly data-sly-test="${!production}" data-sly-include="edit.html" />
   ```

   Screens components require two different renderings depending on which [authoring mode](https://experienceleague.adobe.com/en/docs/experience-manager-64/authoring/authoring/author-environment-tools) is being used:

    1. **Production**: Preview or Publish mode (wcmmode=disabled)
    1. **Edit**: used for all other authoring modes, that is, edit, design, scaffolding, developer...

   `helloworld.html`acts as a switch, checking which authoring mode is active and redirecting to another HTL script. A common convention used by screens components is to have an `edit.html` script for Edit mode and a `production.html` script for Production mode.

1. Create a file beneath `/apps/weretail-run/components/content/helloworld` named `production.html.`

   Populate the file with the following:

   ```xml
   <!--/*
    /apps/weretail-run/components/content/helloworld/production.html

   */-->

   <div data-duration="${properties.duration}" class="cmp-hello-world">
    <h1 class="cmp-hello-world__message">${properties.message}</h1>
   </div>
   ```

   The above is the production markup for the Hello World component. A `data-duration` attribute is included since the component is used on a Sequence channel. The `data-duration` attribute is used by the Sequence channel to know for how long a sequence item is to be displayed.

   The component renders a `div` and an `h1` tag with text. `${properties.message}` is a portion of HTL script that outputs the contents of a JCR property that is named `message`. A dialog box is created later that allows a user to enter a value for the `message` property text.

   Also note that BEM (Block Element Modifier) notation is used with the component. BEM is a CSS coding convention that makes it easier to create reusable components. BEM is the notation used by [AEM's Core Components](https://github.com/adobe/aem-core-wcm-components/wiki/CSS-coding-conventions). <!-- DEAD LINK More info can be found at: [https://getbem.com/](https://getbem.com/) -->

1. Create a file beneath `/apps/weretail-run/components/content/helloworld` named `edit.html.`

   Populate the file with the following:

   ```xml

   <!--/*

    /apps/weretail-run/components/content/helloworld/edit.html

   */-->

   <!--/* if message populated */-->
   <div
    data-sly-test.message="${properties.message}"
    class="aem-Screens-editWrapper cmp-hello-world">
    <p class="cmp-hello-world__message">${message}</p>
   </div>

   <!--/* empty place holder */-->
   <div data-sly-test="${!message}"
        class="aem-Screens-editWrapper cq-placeholder cmp-hello-world"
        data-emptytext="${'Hello World' @ i18n, locale=request.locale}">
   </div>
   ```

   The above is the edited markup for the Hello World component. The first block displays an edited version of the component if the dialog message has been populated.

   The second block is rendered if no dialog box message has been entered. The `cq-placeholder` and `data-emptytext` render the label ***Hello World*** as a place holder in that case. The string for the label can be internationalized using i18n to support authoring in multiple locales.

1. **Copy Screens Image Dialog to be used for the Hello World component.**

   It is easiest to start from an existing dialog box and then make modifications.

    1. Copy the dialog box from: `/libs/screens/core/components/content/image/cq:dialog`
    1. Paste the dialog box beneath `/apps/weretail-run/components/content/helloworld`

   ![copy-image-dialog](assets/copy-image-dialog.gif)

1. **Update the Hello World dialog box to include a tab for message.**

   Update the dialog so that it matches the following. The JCR node structure of the final dialog is presented below in XML:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:cq="https://www.day.com/jcr/cq/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0" xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
       jcr:primaryType="nt:unstructured"
       jcr:title="Hello World"
       sling:resourceType="cq/gui/components/authoring/dialog">
       <content
           jcr:primaryType="nt:unstructured"
           sling:resourceType="granite/ui/components/coral/foundation/tabs"
           size="L">
           <items jcr:primaryType="nt:unstructured">
               <message
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Message"
                   sling:resourceType="granite/ui/components/coral/foundation/fixedcolumns">
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/coral/foundation/container">
                           <items jcr:primaryType="nt:unstructured">
                               <message
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/textfield"
                                   fieldDescription="Message for component to display"
                                   fieldLabel="Message"
                                   name="./message"/>
                           </items>
                       </column>
                   </items>
               </message>
               <sequence
                   jcr:primaryType="nt:unstructured"
                   jcr:title="Sequence"
                   sling:resourceType="granite/ui/components/coral/foundation/fixedcolumns">
                   <items jcr:primaryType="nt:unstructured">
                       <column
                           jcr:primaryType="nt:unstructured"
                           sling:resourceType="granite/ui/components/coral/foundation/container">
                           <items jcr:primaryType="nt:unstructured">
                               <duration
                                   jcr:primaryType="nt:unstructured"
                                   sling:resourceType="granite/ui/components/coral/foundation/form/numberfield"
                                   defaultValue=""
                                   fieldDescription="Amount of time the image is shown in the sequence, in milliseconds"
                                   fieldLabel="Duration (milliseconds)"
                                   min="0"
                                   name="./duration"/>
                           </items>
                       </column>
                   </items>
               </sequence>
           </items>
       </content>
   </jcr:root>

   ```

   The text field for the Message is saved to a property named `message` and that the number field for the Duration is saved to a property named `duration`. These two properties are both referenced in `/apps/weretail-run/components/content/helloworld/production.html` by HTL as `${properties.message}` and `${properties.duration}`.

   ![Hello World - completed dialog](assets/2018-04-29_at_5_21pm.png)

   Hello World - completed dialog

## Create Client-Side Libraries {#clientlibs}

Client-Side Libraries provide a mechanism to organize and manage CSS and JavaScript files necessary for an AEM implementation. 

AEM Screens components are rendered differently in Edit mode vs. Preview-Production mode. Two client libraries are created: one for Edit mode, and the second for Preview-Production.

1. Create a folder for client-side libraries for the Hello World component.

   Beneath `/apps/weretail-run/components/content/helloworld`, create a folder named `clientlibs`.

   ![2018-04-30_at_1046am](assets/2018-04-30_at_1046am.png)

1. Beneath the `clientlibs` folder, create a node named `shared` of type `cq:ClientLibraryFolder`.

   ![2018-04-30_at_1115am](assets/2018-04-30_at_1115am.png)

1. Add the following properties to the shared client library:

    * `allowProxy` | Boolean | `true`

    * `categories`| String[] | `cq.screens.components`

   ![Properties for /apps/weretail-run/components/content/helloworld/clientlibs/shared](assets/2018-05-03_at_1026pm.png)

   Properties for /apps/weretail-run/components/content/helloworld/clientlibs/shared

   The categories property is a string that identifies the client library. The cq.screens.componentscategory is used in both Edit and Preview-Production mode. Therefore, any CSS or JS defined in the sharedclientlib is loaded in all modes.

   As a best practice, any paths directly to `/apps` in a production environment should never be exposed. The allowProxy property ensures the client library CSS and JS is referenced through a prefix of `/etc.clientlibs`. 

1. Create file named `css.txt` beneath the shared folder.

   Populate the file with the following:

   ```
   #base=css

   styles.less

   ```

1. Create a folder named `css` beneath the `shared` folder. Add a file named `style.less` beneath the `css` folder. The structure of the client libraries should now look like this:

   ![2018-04-30_at_3_11pm](assets/2018-04-30_at_3_11pm.png)

   Instead of writing CSS directly, this tutorial uses LESS. [LESS](https://lesscss.org/) is a popular CSS pre-compiler that supports CSS variables, mixins, and functions. AEM client libraries natively support LESS compilation. You can use Sass or other pre-compilers, but you must compile them outside of AEM.

1. Populate `/apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less` with the following:

   ```css
   /**
       Shared Styles
      /apps/weretail-run/components/content/helloworld/clientlibs/shared/css/styles.less

   **/

   .cmp-hello-world {
       background-color: #fff;

    &__message {
     color: #000;
     font-family: Helvetica;
     text-align:center;
    }
   }
   ```

1. Copy and paste the `shared` client library folder to create a client library that is named `production`.

   ![Copy the shared client library to create a new production client library](assets/copy-clientlib.gif)

   Copy the shared client library to create a production client library.

1. Update the `categories` property of the production client library to be `cq.screens.components.production.`

   Doing so ensures that the styles are only loaded when in Preview-Production mode.

   ![Properties for /apps/weretail-run/components/content/helloworld/clientlibs/production](assets/2018-04-30_at_5_04pm.png)

   Properties for `/apps/weretail-run/components/content/helloworld/clientlibs/production`.

1. Populate `/apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less` with the following:

   ```css
   /**
       Production Styles
      /apps/weretail-run/components/content/helloworld/clientlibs/production/css/styles.less

   **/
   .cmp-hello-world {

       height: 100%;
       width: 100%;
       position: fixed;

    &__message {

     position: relative;
     font-size: 5rem;
     top:25%;
    }
   }
   ```

   The above styles display the message centered in the middle of the screen, but only in Production mode.

A third client library category: `cq.screens.components.edit` could be used to add Edit-only specific styles to the component.

| Clientlib Category |Usage |
|---|---|
| `cq.screens.components` |Styles and scripts that are shared between both edit and production modes |
| `cq.screens.components.edit` |Styles and scripts that are only used in edit mode |
| `cq.screens.components.production` |Styles and scripts that are only used in production mode |

## Create a Design Page {#design-page}

AEM Screens uses [static Page Templates](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/platform/templates/page-templates-static) and [Design configurations](https://experienceleague.adobe.com/en/docs/experience-manager-64/authoring/siteandpage/default-components-designmode) for global changes. Design configurations are frequently used to configure allowed components for the Parsys on a channel. A best practice is to store these configurations in an app-specific way.

Below a `We.Retail` Run Design page is created that stores all configurations specific to the `We.Retail` Run project.

1. In **CRXDE Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs`, navigate to `/apps/settings/wcm/designs`.
1. Create a node beneath the designs folder, named `we-retail-run` with a type of `cq:Page`.
1. Beneath the `we-retail-run` page, add another node named `jcr:content` of type `nt:unstructured`. Add the following properties to the `jcr:content` node:

   | Name |Type |Value |
   |---|---|---|
   | `jcr:title` |String |`We.Retail` Run |
   | `sling:resourceType` |String |`wcm`, `core`, `components`, `designer` |
   | `cq:doctype` |String |html_5 |

   ![Design Page at /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1219pm.png)

   Design Page at `/apps/settings/wcm/designs/we-retail-run`.

## Create a Sequence Channel {#create-sequence-channel}

The Hello World component is for use on a Sequence channel. To test the component, a new Sequence channel is created.

1. From the AEM Start Menu, navigate to **Screens** > **`We.Retail` Run** > and click **Channels**.

1. Click the **Create** button

   1. Choose **Create Entity**

   ![2018-04-30_at_5_18pm](assets/2018-04-30_at_5_18pm.png)

1. In the Create wizard:

1. Template Step - choose **Sequence Channel**

   1. Properties Step

    * Basic Tab > Title = **Idle Channel**
    * Channel Tab > check **Make channel online**

   ![idle-channel](assets/idle-channel.gif)

1. Open the page properties for the Idle Channel. 
1. Update the Design field so that it points to `/apps/settings/wcm/designs/we-retail-run`, the design page created in the previous section.

   ![Design config /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1240pm.png)

   Design config pointing to /apps/settings/wcm/designs/we-retail-run

1. Edit the newly created Idle Channel so you can open it.

1. Switch the page mode to **Design** Mode.

   1. Click the **wrench** Icon in the Parsys so you can configure the allowed components.

   1. Click the **Screens** group and the **`We.Retail` Run - Content** group.

   ![2018-04-30_at_5_43pm](assets/2018-04-30_at_5_43pm.png)

1. Switch the page mode to **Edit**. The Hello World component can now be added to the page and combined with other Sequence channel components.

   ![2018-04-30_at_5_53pm](assets/2018-04-30_at_5_53pm.png)

1. In **CRXDE Lite** `http://localhost:4502/crx/de/index.jsp#/apps/settings/wcm/designs/we-retail-run/jcr%3Acontent/sequencechannel/par`, navigate to `/apps/settings/wcm/designs/we-retail-run/jcr:content/sequencechannel/par`. Notice the `components` property now includes `group:Screens`, `group:We.Retail Run - Content`.

   ![Design configuration under /apps/settings/wcm/designs/we-retail-run](assets/2018-05-07_at_1_14pm.png)

   Design configuration under /apps/settings/wcm/designs/we-retail-run

## Template for Custom Handlers {#custom-handlers}

If your custom component uses external resources such as assets (images, videos, fonts, and icons), specific asset renditions, or client-side libraries (css and js), these resources are not automatically added to the offline configuration. The reason is because only the HTML markup is bundled by default.

To let you customize and optimize the exact assets that are downloaded to the player, Adobe offers an extension mechanism. This mechanism is for custom components to expose their dependencies to the offline caching logic in AEM Screens.

The section below showcases the template for custom offline resource handlers. It also shows the minimum requirements in the `pom.xml` for that specific project.

```java
package …;

import javax.annotation.Nonnull;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Reference;
import org.apache.felix.scr.annotations.Service;
import org.apache.sling.api.resource.Resource;
import org.apache.sling.api.resource.ResourceUtil;
import org.apache.sling.api.resource.ValueMap;

import com.adobe.cq.screens.visitor.OfflineResourceHandler;

@Service(value = OfflineResourceHandler.class)
@Component(immediate = true)
public class MyCustomHandler extends AbstractResourceHandler {

 @Reference
 private …; // OSGi services injection

 /**
  * The resource types that are handled by the handler.
  * @return the handled resource types
  */
 @Nonnull
 @Override
 public String[] getSupportedResourceTypes() {
     return new String[] { … };
 }

 /**
  * Accept the provided resource, visit and traverse it as needed.
  * @param resource The resource to accept
  */
 @Override
 public void accept(@Nonnull Resource resource) {
     ValueMap properties = ResourceUtil.getValueMap(resource);
     
     /* You can directly add explicit paths for offline caching using the `visit`
        method of the visitor. */
     
     // retrieve a custom property from the component
     String myCustomRenditionUrl = properties.get("myCustomRenditionUrl", String.class);
     // adding that exact asset/rendition/path to the offline manifest
     this.visitor.visit(myCustomRenditionUrl);
     
     
     /* You can delegate handling for dependent resources so they are also added to
        the offline cache using the `accept` method of the visitor. */
     
     // retrieve a referenced dependent resource
     String referencedResourcePath = properties.get("myOtherResource", String.class);
     ResourceResolver resolver = resource.getResourceResolver();
     Resource referencedResource = resolver.getResource(referencedResourcePath);
     // let the handler for that resource handle it
     if (referencedResource != null) {
         this.visitor.accept(referencedResource);
     }
   }
}
```

The following code provides the minimum requirements in the `pom.xml` for that specific project:

```css
   <dependencies>
        …
        <!-- Felix annotations -->
        <dependency>
            <groupId>org.apache.felix</groupId>
            <artifactId>org.apache.felix.scr.annotations</artifactId>
            <version>1.9.0</version>
            <scope>provided</scope>
        </dependency>

        <!-- Screens core bundle with OfflineResourceHandler/AbstractResourceHandler -->
        <dependency>
            <groupId>com.adobe.cq.screens</groupId>
            <artifactId>com.adobe.cq.screens</artifactId>
            <version>1.5.90</version>
            <scope>provided</scope>
        </dependency>
        …
      </dependencies>
```

**NOTE** : If there is AEM as a Cloud Service, use below dependency in the `pom.xml` for that specific project.

```css
   <dependencies>
        …
        <!-- AEM Screens SDK API with OfflineResourceHandler/AbstractResourceHandler -->
        <dependency>
            <groupId>com.adobe.aem</groupId>
            <artifactId>aem-screens-sdk-api</artifactId>
            <version>1.0.8</version>
        </dependency>
        …
      </dependencies>
```

## Putting it all together {#putting-it-all-together}

The below video shows the finished component and how it can be added to a Sequence channel. The Channel is then added to a Location display and ultimately assigned to a Screens player.

>[!VIDEO](https://video.tv.adobe.com/v/22385?quaity=9)

## Other considerations for custom components embedding other pages or fragments {#additional-considerations}

 If your custom component is meant to include other pages or Experience Fragments, and you want changes in the embedded content automatically picked up by the player&mdash;without republishing the channel&mdash;consider these two constraints:

 1. Instead of directly extending `foundation/components/parbase`, you'd have to extend either `screens/core/components/content/page` or `screens/core/components/content/experiencefragment`
 2. The name of the property you use to reference the embedded content must be `pagePath`.

 Using those two Screens core components also comes with the added benefit that they can take care of bundling some of the dependencies you need (client-side libraries, fonts, and so on). This functionality is done by way of their offline configuration options in the component dialog box. It then reduces the responsibility of any custom offline handler that you would have to use for it. It can sometimes even completely remove the need to use one in the first place.
 
## Finished Code {#finished-code}

Below is the finished code from the tutorial. The **screens-weretail-run.ui.apps-0.0.1-SNAPSHOT.zip** and **screens-weretail-run.ui.content-0.0.1-SNAPSHOT.zip** are the compiled AEM packages. The **SRC-screens-weretail-run-0.0.1.zip **is the uncompiled source code that can be deployed using Maven.

[Get File](assets/screens-weretail-runuiapps-001-snapshot.zip)

[Get File](assets/screens-weretail-runuicontent-001-snapshot.zip)

[Get File](assets/screens-weretail-run.zip)
