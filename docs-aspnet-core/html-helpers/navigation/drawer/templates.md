---
title: Templates
page_title: Templates | Kendo UI Drawer HtmlHelper for ASP.NET Core
description: "Use the available templates of the Kendo UI Drawer HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: templates_drawer_aspnetcore
position: 4
---

# Templates

To distinguish the items within the template when the user interacts with the Drawer, add the `data-role="drawer-item"` attribute to each item HTML template.

If you wish to add a separator between the drawer items use the `data-role="drawer-separator"` attribute.

The Kendo UI Drawer widget provides the following configurable templates:
* The main `Template()` method.
* The `Mini(m=>m.Template("<div>Mini Template</div>"))` template.

You can add icons with a span with the `k-icon` class combined with the desired [web font icons](https://docs.telerik.com/kendo-ui/styles-and-layout/icons-web#list-of-font-icons) class. To ensure that the icons and text have a sufficient padding, wrap the item template text in a span with class `k-item-text`.

    @"<ul>
        <li data-role='drawer-item'>
          <span class='k-icon k-i-eye'></span>
          <span class='k-item-text'>See More</span>
        </li>
    </ul>"

## See Also

* [JavaScript API Reference of the Drawer](https://docs.telerik.com/kendo-ui/api/javascript/ui/drawer)
