---
title: Grouping
page_title: Grouping | Kendo UI DropDownList HtmlHelper for ASP.NET Core
description: "Learn how to group data in the Kendo UI DropDownList HtmlHelper for ASP.NET Core works."
slug: htmlhelpers_dropdownlist_grouping_aspnetcore
position: 3
---

# Grouping Overview

The DropDownList enables you to bind it to a grouped data source.

To group the data, define a group `datasource` expression which uses a custom DataSource configuration, and specify the field by which the DropDownList will be grouped. For a runnable example, refer to the [demo on grouping in the DropDownList](https://demos.telerik.com/aspnet-core/dropdownlist/grouping).

> The data source sorts the grouped data either in ascending or descending order. To persist a specific group order, use the [server grouping feature](http://docs.telerik.com/kendo-ui/api/javascript/data/datasource#configuration-serverGrouping). To define the `serverGrouping` option, use the `ServerGrouping` method of the DataSource.

The following example demonstrates how to group the data in the DropDownList by country.

    ```
    @(Html.Kendo().DropDownList()
        .Name("customers")
        .DataSource(source =>  source
            .Custom()
            .Group(g => g.Add("Country", typeof(string)))
            .Transport(transport => transport
                .Read(read =>
                {
                    read.Action("Grouping_GetCustomers", "DropDownList");
                }))
            )
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
    )
    ```

## See Also

* [Grouping by the DropDownList HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/dropdownlist/grouping)
* [JavaScript API Reference of the DropDownList](http://docs.telerik.com/kendo-ui/api/javascript/ui/dropdownlist)
