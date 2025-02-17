---
title: Overview
page_title: TreeMap Overview | Telerik UI for ASP.NET Core Tag Helpers
description: "Learn the basics when working with the Kendo UI TreeMap tag helper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: taghelpers_treemap_aspnetcore
previous_url: /aspnet-core/helpers/tag-helpers/treemap
position: 1
---

# TreeMap Tag Helper Overview

The Kendo UI TreeMap displays hierarchical data in a traditional tree structure.

The TreeMap tag helper extension is a server-side wrapper for the [Kendo UI TreeMap](https://demos.telerik.com/kendo-ui/treemap/index) widget and enables you to configure the Kendo UI TreeMap widget in ASP.NET Core applications.

## Initializing the TreeMap

The following example demonstrates how to define the TreeMap by using the TreeMap tag helper.

    <kendo-treemap datasource-id="dataSource" name="treeMap" text-field="name" value-field="value"></kendo-treemap>

    <script>
        var dataSource = new kendo.data.HierarchicalDataSource({
            data: [{
                name: "foo",
                value: 1
            }]
        });
    </script>

## Binding to Remote Data

You can also bind the `DataSource` to remote data. The following example demonstrates how to bind the Kendo UI TreeMap tag helper to a remote service.

```tagHelper
    <kendo-treemap name="treemap" text-field="name" value-field="value">
        <hierarchical-datasource>
            <transport>
                <read url="/treemap/_populationusa" />
            </transport>
            <schema>
                <hierarchical-model children="items"></hierarchical-model>
            </schema>
        </hierarchical-datasource>
    </kendo-treemap>

```
```cshtml
    @(Html.Kendo().TreeMap()
        .Name("treeMap")
        .DataSource(dataSource => dataSource
            .Read(read => read
                .Action("_PopulationUSA", "TreeMap")
            )
            .Model(m => m.Children("Items"))
        )
        .ValueField("Value")
        .TextField("Name")
        .HtmlAttributes(new { style = "height:600px; font-size: 12px;" })
    )
```

## See Also

* [Basic Usage of the TreeMap Tag Helper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/treemap/tag-helper)
* [JavaScript API Reference of the Kendo UI TreeMap](https://docs.telerik.com/kendo-ui/api/javascript/dataviz/ui/treemap)
