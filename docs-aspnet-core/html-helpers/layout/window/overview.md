---
title: Overview
page_title: Window Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Kendo UI Window HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/html-helpers/window
slug: htmlhelpers_window_aspnetcore
position: 1
---

# Window HtmlHelper Overview

The [Window](http://docs.telerik.com/kendo-ui/controls/layout/window/overview) displays content in a modal or non-modal HTML window.

By default, the user can move, resize, and close a Window. Its content can also be defined either as static HTML or dynamically loaded through AJAX.

The Window HtmlHelper extension is a server-side wrapper for the [Kendo UI Window](http://demos.telerik.com/kendo-ui/window/index) widget. For more information on the Window HtmlHelper for ASP.NET MVC, refer to the [UI for ASP.NET MVC documentation](http://docs.telerik.com/aspnet-mvc/helpers/window/overview).

## Initializing the Window

The following example demonstrates how to define the Window by using the Window HtmlHelper.

```Razor
 @(Html.Kendo().Window()
    .Name("window")
    .Title("Window title")
    .Content(@<text>
            Static content of the Window.
    </text>)
)
```
```Controller
    public class WindowController  : Controller
    {
        public IActionResult Index()
        {
            return View();
        }
    }
```

## Basic Configuration

The Window provides default configuration options that can be set during initialization such as height and width, user actions, draggable behavior, initial position, and so on.

The following example demonstrates the basic configuration of the Window HtmlHelper.

    @(Html.Kendo().Window()
        .Name("window")
        .Width(500)
        .Height(300)
        .Title("Window title")
        .Visible(true)
        .Actions(actions => actions.Refresh().Minimize().Maximize().Close())
        .LoadContentFrom("AjaxContent", "Window")
        .Draggable(false)
        .Resizable(false)
    )

    <script type="text/javascript">
        $(function() {
            // The Name() of the Window is used to get its client-side instance.
            var dialog = $("#window").data("kendoWindow");
        });
    </script>

## Functionality and Features

* [Dimensions]({% slug htmlhelpers_window_dimensions_aspnetcore %})
* [Positioning]({% slug htmlhelpers_window_positioning_aspnetcore %})
* [Constraining the position]({% slug htmlhelpers_window_constrain_aspnetcore %})
* [Loading content]({% slug htmlhelpers_window_loadingcontent_aspnetcore %})
* [Using iframe]({% slug htmlhelpers_window_iframe_aspnetcore %})
* [Integration with forms]({% slug htmlhelpers_window_forms_aspnetcore %})

## Events

You can subscribe to all Window [events](/api/Kendo.Mvc.UI.Fluent/WindowEventBuilder). For a complete example on basic Window events, refer to the [demo on using the events of the Window](https://demos.telerik.com/aspnet-core/window/events).

### Handling by Handler Name

The following example demonstrates how to subscribe to events by handler name.

    @(Html.Kendo().Window()
        .Name("window")
        .Events(e => e
            .Open("window_open")
            .Close("window_close")
        )
    )
    <script>
        function window_open() {
            // Handle the open event.
        }

        function window_close() {
            // Handle the close event.
        }
    </script>


### Handling by Template Delegate

The following example demonstrates how to subscribe to events by using a template delegate.

    @(Html.Kendo().Window()
        .Name("window")
        .Events(e => e
            .Open(@<text>
                function() {
                    // Handle the open event inline.
                }
            </text>)
            .Close(@<text>
                function() {
                    // Handle the close event inline.
                }
            </text>)
        )
    )

## See Also

* [Basic Usage of the Window HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/window/index)
* [Using the API of the Window HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/window/api)
* [JavaScript API Reference of the Window](http://docs.telerik.com/kendo-ui/api/javascript/ui/window)
