---
title: Overview
page_title: Tooltip Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Kendo UI Tooltip HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/html-helpers/tooltip
slug: htmlhelpers_tooltip_aspnetcore
position: 1
---

# Tooltip HtmlHelper Overview

The [Tooltip](http://docs.telerik.com/kendo-ui/controls/layout/tooltip/overview) displays a popup hint for a given html element. Its content can be defined either as static text, or loaded dynamically via AJAX.

The Tooltip HtmlHelper extension is a server-side wrapper for the [Kendo UI Tooltip](http://demos.telerik.com/kendo-ui/tooltip/index) widget. For more information on the Tooltip HtmlHelper for ASP.NET MVC, refer to the [UI for ASP.NET MVC documentation](http://docs.telerik.com/aspnet-mvc/helpers/tooltip/overview).

## Initializing the Tooltip

The following example demonstrates how to define the Tooltip by using the Tooltip HtmlHelper.

```
   <span id="tooltip" class="k-button wider">Hover me!</span>

    @(Html.Kendo().Tooltip()
        .For("#tooltip")
        .Position(TooltipPosition.Top)
        .Content("Hello!")
    )
```

## Basic Configuration

The following example demonstrates the basic configuration of the Tooltip HtmlHelper.

```
    <span id="tooltip" class="k-button wider">
      <а href="#">Hover me</a>
    </span>

    @(Html.Kendo().Tooltip()
        .For("#tooltip")
        .Position(TooltipPosition.Top)
        .Content("Hello!")
        .Width(120)
        .AutoHide(false)
        .Filter("a")
        .Events(events => events.Hide("onHide").Show("onShow"))
    )

    <script type="text/javascript">
        $(function () {
            // The Name() of the Tooltip is used to get its client-side instance.
            var tooltip = $("#tooltip").data("kendoTooltip");
            console.log(tooltip);
        });
    </script>

```

## Events

For a complete example on basic Tooltip events, refer to the [demo on using the events of the Tooltip](https://demos.telerik.com/aspnet-core/tooltip/events).

## See Also

* [Basic Usage of the Tooltip HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/tooltip)
* [Using the API of the Tooltip HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/tooltip/api)
* [JavaScript API Reference of the Tooltip](http://docs.telerik.com/kendo-ui/api/javascript/ui/tooltip)
