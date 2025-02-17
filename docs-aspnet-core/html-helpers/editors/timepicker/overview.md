---
title: Overview
page_title: TimePicker Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Kendo UI TimePicker HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: overview_timepickerhelper_aspnetcore
position: 1
---

# TimePicker HtmlHelper Overview

The Kendo UI TimePicker enables users to select time values from a predefined list or enter new ones.

The TimePicker HtmlHelper extension is a server-side wrapper for the [Kendo UI TimePicker](https://demos.telerik.com/kendo-ui/timepicker/index) widget. For more information on the TimePicker HtmlHelper for ASP.NET MVC, refer to the [UI for ASP.NET MVC documentation](https://docs.telerik.com/aspnet-mvc/helpers/timepicker/overview).

## Initializing the TimePicker

The following example demonstrates how to how to define the TimePicker by using the TimePicker HtmlHelper.

```
    @(Html.Kendo().TimePicker()
        .Name("timepicker") // The name of the TimePicker is mandatory. It specifies the "id" attribute of the widget.
        .Value(DateTime.Now) // Set the value of the TimePicker.
    )
```

## Events

You can subscribe to all TimePicker [events](https://docs.telerik.com/kendo-ui/api/javascript/ui/timepicker#events). For a complete example on basic TimePicker events, refer to the [demo on using the events of the TimePicker](https://demos.telerik.com/aspnet-core/timepicker/events).

### Handling by Handler Name

The following example demonstrates how to subscribe to events by a handler name.

```
    @(Html.Kendo().TimePicker()
          .Name("timepicker")
          .Events(e => e
                .Open("timepicker_open")
                .Close("timepicker_close")
                .Change("timepicker_change")
          )
    )
    <script>
        function timepicker_open(e) {
            // Handle the open event.
        }

        function timepicker_close(e) {
            // Handle the close event.
        }

        function timepicker_change(e) {
            // Handle the change event.
        }
    </script>
```

### Handling by Template Delegate

The following example demonstrates how to subscribe to events by a template delegate.

```
    @(Html.Kendo().TimePicker()
          .Name("timepicker")
          .Events(e => e
              .Open(@<text>
                function(e) {
                    // Handle the open event inline.
                }
              </text>)
              .Change(@<text>
                function(e) {
                    // Handle the change event inline.
                }
                </text>)
          )
    )
```

## Referencing Existing Instances

To reference an existing Kendo UI TimePicker instance, use the [`jQuery.data()`](https://api.jquery.com/jQuery.data/) configuration option. Once a reference is established, use the [TimePicker API](https://docs.telerik.com/kendo-ui/api/javascript/ui/timepicker#methods) to control its behavior.

```
    // Place this after your Kendo UI TimePicker for ASP.NET Core declaration.
    <script>
        $(function() {
            // The Name() of the TimePicker is used to get its client-side instance.
            var timepicker = $("#timepicker").data("kendoTimePicker");
        });
    </script>
```

## See Also

* [Basic Usage by the TimePicker HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/timepicker)
* [Using the API of the TimePicker HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/timepicker/api)
* [JavaScript API Reference of the TimePicker](http://docs.telerik.com/kendo-ui/api/javascript/ui/timepicker)
