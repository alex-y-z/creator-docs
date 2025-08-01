---
title: Packages
description: Packages allow you to reuse single assets or asset hierarchies across experiences.
id: packages
---

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/AzKZy2BqIh8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe><br />

To keep assets organized and reusable across your team or across multiple projects, group your instances and convert them into reusable **packages**. Packages make the overall process of building worlds faster and more ergonomic, but they also help with consistency, deduplication, collaboration, and versioning:

- Easily [update all copies](#mass-updates) of a package to the latest version (or only [update specific copies](#update-outdated-copies)).
- Set packages to [automatically update](#automatic-updates) whenever there's a new version.
- Give collaborators **Edit** or **Use** permissions to the contents of a package.
- View the full version history for a package, compare versions, and restore old versions.

The most efficient workflow is to [create a package](#create-packages), [share it](#share-and-access-levels) with any collaborators, and [set it to auto-update](#automatic-updates). And you don't have to wait for a model to be "done" before using it in a package. Even if the package is a placeholder on top of a simple shape, you can use it to [greybox your environment](../../tutorials/curriculums/environmental-art/greybox-your-environment.md) and then have the placeholder copies automatically update as you publish more detailed versions.

## Create Packages

<Alert severity="warning">
If you want to create a package with restricted assets that you don't have [explicit permission](../../projects/assets/privacy.md#view-permissions) to use, you can still create the package but those specific restricted assets will **not** be visible or audible at runtime unless the experience itself has permission to use those assets.
</Alert>

You can create a package from any single object or any single parent and children branch of objects. If you want to create a package for a single object, add it to a `Class.Model` grouping first so that you can add, remove, or scale child objects within the package later without breaking the package.

To create a package:

1. In the **Explorer** window or 3D viewport, right-click the object(s) you want to turn into a package, then in contextual menu, select **Convert to Package**.
1. In the new window, fill in the package details. In particular, if you're working in a [group](../../projects/groups.md), set **Ownership** to the appropriate group in which you have permission to create/edit group experiences.

   <Alert severity="warning">
   Ownership transfers are **not** supported by the asset system, so carefully consider the owner when creating a package.
   </Alert>

1. Click **Submit**.
1. After the conversion completes, the object receives a "chain link" symbol in the **Explorer** window to identify it as a package. Additionally, you can see a new **PackageLink** object parented to the object.

   <img src="../../assets/studio/packages/PackageLink-Explorer.png" alt="A maple tree model in the Explorer window with the package icon next to it." width="215" />

1. **(Optional)** Select the **PackageLink** object and enable `AutoUpdate` in the **Properties** window. Note how the icon changes to indicate that the package is set to automatically update.

   <img src="../../assets/studio/packages/PackageLink-Explorer-Auto.png" alt="A maple tree model in the Explorer window with the auto-update package icon next to it." width="215" />

<Alert severity="error">
Don't delete or move the **PackageLink** object! Doing so for any package copy converts the copy back into a normal object and loses package capabilities, such as ability to update itself when there's a new version.
</Alert>

## Insert packages

To insert a package that doesn't already exist in the current place, you must **initially** insert it from the [Toolbox](../../projects/assets/toolbox.md):

- From **Inventory** ⟩ **My Packages** for packages that you've published to or obtained from the [Creator Store](../../production/creator-store.md), as well as packages that a connection owns and has given you [permissions](#share-and-access-levels) to use.
- From **Creations** ⟩ **Group Packages** for packages published by members of your [group](../../projects/groups.md) (including yourself).

<GridContainer numColumns="2">
  <figure>
    <img src="../../assets/studio/toolbox/Inventory-My-Packages.png" alt="A close up view of the Toolbox with both the Inventory tab and the assets dropdown menu highlighted." width="360" />
    <figcaption>Toolbox ⟩ Inventory ⟩ My Packages</figcaption>
  </figure>
  <figure>
    <img src="../../assets/studio/toolbox/Creations-Group-Packages.png" alt="A close up view of the Toolbox with the Creations tab highlighted." width="360" />
    <figcaption>Toolbox ⟩ Creations ⟩ Group Packages</figcaption>
  </figure>
</GridContainer>

Once you've inserted a package into a published place's data model, it appears in the [Asset Manager](../../projects/assets/manager.md) and remains there even if you later delete all copies of it.

<Alert severity="warning">
Be careful when inserting assets that you didn't create into your experiences, as they can contain malicious scripts. Save your experience first and then investigate any scripts within unfamiliar assets so that you can easily revert back to the place version.
</Alert>

## Publish package changes

You can publish any change to your package as a new version, making your updates available to other package copies throughout the place and across all experiences. It's **not** required to publish a modified package before publishing a place because the modified version is saved along with the place for future iteration.

To publish changes to a package:

1. In the **Explorer** window or 3D viewport, right-click the modified copy and select **Publish to Package**.
1. If a package copy has [auto-update](#automatic-updates) turned on, it immediately pulls in the updated version when you open the place that contains them. Other copies get a white dot on the package icon that indicates an update is available. You can [individually update](#update-outdated-copies) or [mass-update](#mass-updates) all copies.

   <img src="../../assets/studio/packages/Package-Update-Available.png" alt="Two packages in the Explorer set to auto-update, and one with an update available." width="215" />

1. **(Optional)** Add a description of your changes:

   1. Right-click the package and select **Package Details**.
   1. In the **Asset Configuration** window, select **Versions**.
   1. Under your most-recent change, select **Add**.
   1. Describe your changes, then click the **Submit** button.

## Update outdated copies

You can update outdated package copies to the most recent version, or you can continue to use the older version.

To update one or more package copies to the latest version:

1. In the **Explorer** window, locate outdated copies by the white dot on the package icon. You can also select the outdated copy in the 3D viewport, but it might be harder to find this way.

   <img src="../../assets/studio/packages/Package-Update-Available.png" alt="Two packages in the Explorer set to auto-update, and one with an update available." width="215" />

1. Right-click the outdated copy and select **Get Latest Package**. You can also select multiple packages, right-click, and **Get Latest For Selected Packages**.

### Mass updates

Extensive use of packages may result in many package copies across multiple places in an experience. In addition to [individual syncing](#update-outdated-copies) and [automatic updates](#automatic-updates), you can update all copies of a package through **mass updating**.

1. **(Recommended)** Close other Studio instances with any of the experience's places open; this prevents another unsaved instance of a place from potentially overwriting your updates.
1. In the **Explorer** window or 3D viewport, right-click the desired package and select **Update All**.
1. Choose all places in the experience or some subset of places and click **Update**.

   <img src="../../assets/studio/packages/Mass-Update.png" alt="A view of the mass update window, showing two places." width="500" />

   To prevent unintended overwrites, mass updating does not affect [modified](#modify-packages) versions of a package. After the mass update completes, Studio displays a warning with the number of packages that it did **not** update, if any.

<Alert severity="info">
Mass updating packages automatically **saves** the selected places but does not **publish** them.
</Alert>

### Automatic updates

To make syncing easier, you can set a package copy to update automatically whenever a newer version is published. Auto-update of the package copies will take place when a place is opened in Studio.

To automatically update package copies:

1. In the **Explorer** window, expand the package's hierarchy tree and select its **PackageLink** object.

   <img src="../../assets/studio/packages/PackageLink-Explorer.png" alt="A close up view of a packaged chandelier model in the Explorer window. The PackageLink object is highlighted." width="215" />

1. In the **Properties** window, enable the **AutoUpdate** property. If you have [nested packages](#nested-packages), this property only applies to the highest-level parent package, meaning automatic updates only occur when the **parent** package is updated.

<Alert severity="warning">
Automatic updating does not apply to [modified](#modifying-packages) package copies. Once you modify a package instance, its **AutoUpdate** property becomes disabled and is ignored.
</Alert>

## Share and access levels

You can grant permission to connections, experiences, groups, or specific group user roles so that they can freely use your packages in their creations. For more information on asset access, see [Asset privacy](privacy.md).

<Alert severity="warning">
If you share a package with restricted assets that you don't have [explicit permission](../../projects/assets/privacy.md#view-permissions) to use, you can still share the package but those specific restricted assets will **not** be visible or audible at runtime unless the connection, experience, or group has permission to use those assets.
</Alert>

<Tabs>
  <TabItem key = "1" label="To collaborators">

To change package permissions for a collaborator, such as a connection or group:

1. In the **Explorer** window, **Toolbox**, or **Asset Manager**, right-click the desired package and select **Package Details**.
1. In the **Asset Configuration** window, select **Permissions**.
1. Using the search bar, input and select a collaborator that you want to grant permission to use your package, then choose a permission level.

   <table>
   <thead>
   <tr>
   <th>Permission</th>
   <th>Description</th>
   </tr>
   </thead>
   <tbody>
   <tr>
   <td>**Use & View**</td>
   <td>The collaborator can use and view (but not edit) the current and previous package versions. Once you provide a collaborator with this ability, you cannot revoke access to a copy they already inserted into their experience; revoking access prevents reinsertion or package updates, but package copies in their data model remain intact.</td>
   </tr>
   <tr>
   <td>**Edit**</td>
   <td>The collaborator can use, view, and edit the current and previous package versions, including publishing changes to it.</td>
   </tr>
   </tbody>
   </table>

  </TabItem>
  <TabItem key = "2" label="To experiences">

To grant package access to an experience, the experience must be editable to either you or a group that you belong to in which you have the **Create and edit group experiences** role permission.

To change package permissions for an experience:

1. Navigate to the [Creator Dashboard](https://create.roblox.com/dashboard/creations).
1. In the upper tab bar, select **Development Items**, then click **Models & Packages**.
1. Select the package you want your experience to have permission to use. The package's **Configure** page displays.
1. In the package's left-hand navigation, select **Permissions**. The package's **Permissions** page displays.
1. From the **Experiences** tab, click the **Add experiences** button.
1. Type the experience's universeID into the **Enter Universe IDs** input, then click the **Add** button. The experience displays beneath the input with its access visible.

   <Alert severity="info">
   If you want to give multiple experiences permission to use your restricted access at the same time, you can enter multiple universeIDs as long as you separate them with a comma.
   </Alert>

1. Click the **Done** button to finalize your package asset access permissions.

  </TabItem>
</Tabs>

## Modify Packages

You can edit packages and their children just like other objects. Modifying packages disables auto-update until you publish or revert the changes.

<img src="../../assets/studio/packages/Modify-Notification.png" alt="The pop-up notice that you cannot update a modified package until you publish or revert your changes." width="500" />

Most edits flag the package as modified, although the following changes are **not** considered package modifications:

- Changing the **name** of the root node.
- Changing the **position** or **rotation** of the root node of a package that is a `Class.BasePart`, `Class.Model`, or `Class.GuiObject`.
- Changing the **Enabled** property of a root node `Class.GuiObject` such as a `Class.ScreenGui`, `Class.SurfaceGui`, or `Class.BillboardGui`.
- Changing a part reference of a `Class.Weld` inside the package that references an instance outside of the package.

Once modified, packages with unpublished changes get a modified icon in the [Explorer](../../studio/explorer.md) window:

<img src="../../assets/studio/packages/Modify-Notification.png" alt="The Explorer window with an icon that identifies unpublished package changes." width="500" />

### Add or update configurations

You can include [instance attributes](../../studio/properties.md#instance-attributes) at the root of a package to customize its behavior, for example the max speed of a packaged vehicle or the debounce time for a packaged button.

When you publish a package, the current set of attributes/values will become the package's **default configurations**. On any given copy of a package, configurations are shown in **bold italics** and those attribute values can be changed on a per-instance basis. When package copies are [updated](#update-outdated-copies), modified configuration values will be preserved, while other attributes will be updated to the latest default value.

<img src="../../assets/studio/packages/Package-Configured-Attributes.png" width="506" alt="The Attributes section of the Properties window. Two properties are highlighted as having their default values while two other italicized properties are highlighted to show they have been configured." />

<Alert severity="info">
Currently the only way to handle configuration values is to add scripts in the package which read and apply behavior based on the configuration at runtime.
</Alert>

<Alert severity="info">
If you simply want to update the default **values** for configurations, you can change those attribute values and republish the package (the package will **not** be flagged as modified in this case). If you want to publish other modifications but not change the default configuration values, you should publish on a package without any value changes, or revert the configurations to their defaults before you publish.
</Alert>

### Nested packages

You can nest packages inside of other packages to maintain and collaborate on complex hierarchies, such as a series of vehicle mechanics which can be modified independently of the vehicle's parent package. This example shows a car package that contains four copies of the same wheel package:

<img src="../../assets/studio/packages/Nested-Packages.png" alt="An expanded hierarchy in the Explorer window showing how packages can contain packages." width="414" />

<Alert severity="warning">
If you modify a nested package, both the nested package **and** the parent package are considered as modified. You must [publish changes](#publish-package-changes) to any **nested** package before you're allowed to publish changes to its **parent** package, since publishing the parent would mark it as current/unmodified and conflict with the nested package's modifications.
</Alert>

### Package scripts

Each script within an **unmodified** package is read-only and shows a notification on the top with a hyperlink to unlock the script.

<img src="../../assets/studio/packages/Script-Unlock-Link.png" alt="A script tab with a yellow notification that you can click to modify the script that's within an unmodified package." width="800" />

Clicking the hyperlink:

- Flags the package as modified regardless of whether you edit the script.
- Removes the notification/hyperlink from **other** scripts within the package.

Once the package is published and moved to an **unmodified** state, the scripts under it become read-only with a hyperlink to modify.

## Revert package changes

Instead of undoing an entire series of package changes one by one, you can [revert unpublished changes](#revert-unpublished-changes) in one action, restore a package to a previous [version](#restore-to-version), or revert changes to specific [configurations](#revert-configurations).

### Revert unpublished changes

To undo an entire series of **unpublished** changes:

1. In the **Explorer** window, locate modified copies by the exclamation point next to their names. You can also select modified copies in the 3D viewport, which might be easier.

1. Right-click a single modified copy and select **Undo Changes to Package**, or select multiple copies (at least one of them modified), right-click, and select **Undo Changes to Selected Packages**.

### Restore to version

To restore a package to a **previously published** version:

1. In the **Explorer** window, 3D viewport, **Toolbox**, or **Asset Manager**, right-click the desired package and select **Package Details**.
1. In the **Asset Configuration** window, select **Versions**. The window displays details for each published version, including the date and time of publication, along with any descriptions of the changes.
1. Click the checkmark next to the version you want to restore and click **Submit**.

   <img src="../../assets/studio/packages/Versions.png" alt="The pop-up window for a chandelier asset. It displays multiple versions." width="800" />

<Alert severity="warning">
Reverting changes to a package does not reset the configuration to the default. See [Reverting Configuration](#revert-configuration).
</Alert>

### Revert configurations

To revert any [configuration](#add-or-update-configurations) attribute to its default, select the **Reset** option from the gear menu in the **Attributes** section of the **Properties** window.

<img src="../../assets/studio/packages/Package-Configured-Attributes-Reset.png" alt="The Attributes section of the Properties window. The gear menu is expanded and the Reset menu item is highlighted." width="346" />

## Compare package versions

When a package has multiple versions, you can compare changes between versions using the diff viewer, which is helpful for reviewing package updates, comparing your local changes against the latest version, and checking the content of past versions before restoring.

The tool has a package hierarchy menu that indicates all added, removed, or modified instances between versions using corresponding icons, with the following tabs available:

- **Visual Overview** shows the visual differences of the 3D rendering under different camera positions. It's the default view for packages with a 3D object (models, parts) as the root object, and it's currently only available for the root object.

   <img src="../../assets/studio/packages/visual-diff.png" alt="An example of the Visual Overview tab in the diff viewer. One version of a building displays on the left-hand side, and another on the right-hand side." width="100%" />

- **Properties** shows changes of properties and attributes. It's the default view for packages with a non-3D object (scripts, lights, 2D objects) as the root object, and it's available for all instances in a package.

   <img src="../../assets/studio/packages/properties-diff.png" alt="An example of the Properties tab in the diff viewer. Modified properties in different versions are highlighted." width="100%" />

- **Script** shows line-by-line script differences. It's available for packages containing scripts, regardless of whether the script is the root object or not.

   <img src="../../assets/studio/packages/script-diff.png" alt="An example of the Script tab in the diff viewer. Modified script lines in different versions are highlighted." width="100%" />

To compare package versions:

1. In the **Explorer** window or 3D viewport, right-click the target package and select **Compare Package Versions**.
1. By default, the window compares changes between your local copy and the latest version. Use the two dropdown menus to compare different versions.

   <img src="../../assets/studio/packages/version-selector.png" alt="A close up view of an example diff viewer. The compare settings are highlighted." width="850" />

   <Alert severity="warning">
   Some older versions might be incompatible with the package diff tool.
   </Alert>

1. After selecting versions:

   - To compare the visual renderings of the root model, if applicable, select the **Visual Overview** tab and adjust the camera control for your desired angle. Controls are synchronized across views:

     - Pan the camera using left mouse clicks.
     - Rotate the camera using right mouse clicks.
     - Zoom in and out the camera with the mouse wheel.
     - Recenter using the keyboard shortcut `-F`.

   - To compare properties and attributes of an instance, select the instance and the **Properties** tab.

   - To compare script differences, if applicable, select any script to open the **Script** tab for line-by-line changes between your selected versions, similar to source control applications.

     <Alert severity="warning">
     This tool only allows you to compare script changes between the current version and the latest published or local version, without indicating the collaborators who made the change.
     </Alert>

Alternatively, you can open the script diff tool directly:

1. In the **Explorer** window or 3D viewport, right-click the target package, which must either be a script or contain scripts, and select **View Script Changes**.
1. In the diff tab that opens, compare all changes of the selected script between the current package copy and the latest published or local version.
