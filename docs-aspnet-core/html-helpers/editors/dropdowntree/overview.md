---
title: Overview
page_title: DropDownTree Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Kendo UI DropDownTree HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/html-helpers/dropdowntree
slug: htmlhelpers_dropdowntree_aspnetcore
position: 1
---

# DropDownTree HtmlHelper Overview

The [DropDownTree](http://docs.telerik.com/kendo-ui/controls/editors/dropdowntree/overview) widget represents an editor of hierarchical data, rendered in a tree-like structure, which provides multiple selection option and custom nodes.

As of the Kendo UI R2 2018, the DropDownTree is available in the Telerik UI for ASP.NET Core suite. The DropDownTree HtmlHelper extension is a server-side wrapper for the [Kendo UI DropDownTree](http://demos.telerik.com/kendo-ui/dropdowntree/index) widget. For more information on the DropDownTree HtmlHelper for ASP.NET MVC, refer to the [UI for ASP.NET MVC documentation](https://docs.telerik.com/aspnet-mvc/helpers/dropdowntree/overview).

## Initializing the DropDownTree

The following example demonstrates how to define the DropDownTree by using the DropDownTree HtmlHelper.

```Razor
    @(Html.Kendo().DropDownTree()
        .Name("dropdowntree")
        .DataTextField("Name")
        .DataSource(dataSource => dataSource
            .Read(read => read
                .Action("Read_DropDownTreeData", "DropDownTree")
            )
        )
    )
```
```Controller
    public class DropDownTreeController : Controller
    {
        public IActionResult Index()
        {
            return View();
        }

        public static IList<HierarchicalViewModel> GetHierarchicalData()
        {
            var result = new List<HierarchicalViewModel>()
            {
                new HierarchicalViewModel() { ID = 1, ParentID = null, HasChildren = true, Name = "Parent item" },
                new HierarchicalViewModel() { ID = 2, ParentID = 1, HasChildren = true, Name = "Parent item" },
                new HierarchicalViewModel() { ID = 3, ParentID = 1, HasChildren = false, Name = "Item" },
                new HierarchicalViewModel() { ID = 4, ParentID = 2, HasChildren = false, Name = "Item" },
                new HierarchicalViewModel() { ID = 5, ParentID = 2, HasChildren = false, Name = "Item" }
            };

            return result;
        }

        public IActionResult Read_DropDownTreeData(int? id)
        {
            var result = GetHierarchicalData()
                .Where(x => id.HasValue ? x.ParentID == id : x.ParentID == null)
                .Select(item => new {
                    id = item.ID,
                    Name = item.Name,
                    expanded = item.Expanded,
                    imageUrl = item.ImageUrl,
                    hasChildren = item.HasChildren
                });

            return Json(result);
        }
    }
```

## Basic Configuration

The following example demonstrates the basic configuration of the DropDownTree HtmlHelper and how to get the DropDownTree instance.

    @(Html.Kendo().DropDownTree()
        .Name("dropdowntree")
        .Checkboxes(true)
        .DataTextField("Name")
        .DataSource(dataSource => dataSource
            .Read(read => read
                .Action("Employees", "DropDownTree")
            )
        )

    )

    <script type="text/javascript">
        $(function () {
            // The Name() of the DropDownTree is used to get its client-side instance.
            var dropdowntree = $("#dropdowntree").data("kendoDropDownTree");
            console.log(dropdowntree);
        });
    </script>

## Events

For a complete example on basic DropDownTree events, refer to the [demo on using the events of the DropDownTree](https://demos.telerik.com/aspnet-core/dropdowntree/events).

## See Also

* [Basic Usage of the DropDownTree HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/dropdowntree/index)
* [Using the API of the DropDownTree HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/dropdowntree/api)
* [JavaScript API Reference of the DropDownTree](http://docs.telerik.com/kendo-ui/api/javascript/ui/dropdowntree)
