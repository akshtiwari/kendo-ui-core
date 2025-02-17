---
title:  Binding to Remote Data
page_title: Binding to Remote Data | Kendo UI Menu HtmlHelper for ASP.NET Core
description: "Learn how to bind to remote data with Kendo UI Menu HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: htmlhelpers_menu_bindingremotedata_aspnetcore
position: 3
---

# Binding to Remote Data

Remote data binding enables you to bind the Menu to a server end-point that returns the items collection for the Menu.

The Menu supports remote data binding as of the Kendo UI R2 2019 release.

1. Implement an action method in your controller that returns the collection for the Menu.

    ```
    public JsonResult GetCategories()
    {
        SampleEntities northwind = new SampleEntities();

        var result = northwind.Categories.Select((category) =>
            new
            {
                Name = category.CategoryName,
                Products = northwind.Products
                    .Where((product) => product.CategoryID == category.CategoryID)
                    .Select((product)=> new { Name = product.ProductName })
            }
        );

        return Json(result, JsonRequestBehavior.AllowGet);
    }
    ```

1. Use the DataSource to configure the action URL to the end-point. Set up the `DataTextField` to define the field which will be bound to the text of the items. If the children items are not in an items field, configure the Model with the corresponding field that holds the children collection.

    ```Razor
        @(Html.Kendo().Menu()
            .Name("menu")
            .DataTextField("Name")
            .DataSource(dataSource => dataSource
                .Model(model => model.Children("Products"))
                .Read(read => read
                    .Action("GetCategories", "Menu")
                )
            )
        )
    ```

## See Also

* [Remote Data Binding by the Menu HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/menu/remote-data-binding)
* [JavaScript API Reference of the Menu](http://docs.telerik.com/kendo-ui/api/javascript/ui/menu)
