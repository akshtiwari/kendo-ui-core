---
title: Overview
page_title: ColorPalette Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Kendo UI ColorPalette HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: overview_colorpalettehelper_aspnetcore
position: 1
---

# ColorPalette HtmlHelper Overview

The ColorPalette renders colors by using sets of predefined colors (color presets) or by implementing a custom color palette.

The ColorPalette HtmlHelper extension is a server-side wrapper for the [Kendo UI ColorPalette](https://docs.telerik.com/kendo-ui/api/javascript/ui/colorpalette) widget. For more information on the ColorPalette HtmlHelper for ASP.NET MVC, refer to the [UI for ASP.NET MVC documentation](https://docs.telerik.com/aspnet-mvc/helpers/colorpalette/overview).

## Initializing the ColorPalette

The following example demonstrates how to define the ColorPalette by using the ColorPalette HtmlHelper.

```
    @(Html.Kendo().ColorPalette()
          .Name("colorpalette") //The name of the ColorPalette is mandatory. It specifies the "id" attribute of the widget.
          .Value("#ff0000") //Set the value of the ColorPalette.
    )
```

## Events

You can subscribe to all ColorPalette [events](https://docs.telerik.com/kendo-ui/api/javascript/ui/colorpalette#events).

### Handling by Handler Name

The following example demonstrates how to subscribe to events by a handler name.

```
    @(Html.Kendo().ColorPalette()
        .Name("colorpalette")
        .Events(e => e
            .Change("colorpalette_change")
        )
    )
    <script>
        function colorpalette_change(e) {
            // Handle the change event.
            var colorpalette = this;
            console.log(colorpalette.value());
        }
    </script>
```

### Handling by Template Delegate

The following example demonstrates how to subscribe to events by a template delegate.

```
    @(Html.Kendo().ColorPalette()
          .Name("colorpalette")
          .Events(e => e
              .Change(@<text>
                function(e) {
                    // Handle the change event inline.
                    console.log(e.sender.value());
                }
                </text>)
          )
    )
```

## Referencing Existing Instances

To reference an existing Kendo UI ColorPalette instance, use the [`jQuery.data()`](https://api.jquery.com/jQuery.data/) configuration option. Once a reference is established, use the [ColorPalette API](https://docs.telerik.com/kendo-ui/api/javascript/ui/colorpalette#methods) to control its behavior.

        // Place this after your Kendo UI ColorPalette for ASP.NET Core declaration.
        <script>
            $(function() {
                // The Name() of the ColorPalette is used to get its client-side instance.
                var colorpalette = $("#colorpalette").data("kendoColorPalette");
            });
        </script>

## See Also

* [Basic Usage of the ColorPalette HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/colorpicker/palette)
* [Using the Palette Presets in the ColorPalette HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/colorpicker/palette-presets)
* [JavaScript API Reference of the ColorPalette](https://docs.telerik.com/kendo-ui/api/javascript/ui/colorpalette)
