---
title: Overview
page_title: ColorPicker Overview | Telerik UI for ASP.NET Core Tag Helpers
description: "Learn the basics when working with the Kendo UI ColorPicker tag helper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/colorpicker, /aspnet-core/helpers/tag-helpers/colorpicker
slug: taghelpers_colorpicker_aspnetcore
position: 1
---

# ColorPicker Tag Helper Overview

The ColorPicker enables the user to select and submit color values.

The ColorPicker tag helper extension is a server-side wrapper for the [Kendo UI ColorPicker](https://demos.telerik.com/kendo-ui/colorpicker/index) widget and enables you to configure the Kendo UI ColorPicker widget in ASP.NET Core applications.

## Initializing the ColorPicker

The following example demonstrates how to define the ColorPicker by using the ColorPicker tag helper.

        <kendo-colorpicker name="picker">
			<messages apply="Change" cancel="Close" />
		</kendo-colorpicker>

## Basic Configuration

The ColorPicker tag helper configuration options are passed as attributes of the tag and through nested tags (`<messages>`).

```cshtml

        @(Html.Kendo().ColorPicker()
			.Name("picker")
			.Value("#fff")
			.Messages(m => m.Apply("Change").Cancel("Close"))
			.Events(events => events.Select("preview"))
		)
```
```tagHelper

        <kendo-colorpicker name="picker" value="#fff" on-select="preview">
            <messages apply="Change" cancel="Close" />
        </kendo-colorpicker>
```

The ColorPalette tag helper configuration options are passed as attributes of the tag and through nested tags (`<tile-size>`).

```cshtml

        @(Html.Kendo().ColorPalette()
			.Name("palette")
			.Columns(4)
			.TileSize(s => s.Width(34).Height(19))
			.Palette(new string[] {
				"#f0d0c9", "#e2a293", "#d4735e", "#65281a",
				"#eddfda", "#dcc0b6", "#cba092", "#7b4b3a",
				"#fcecd5", "#f9d9ab", "#f6c781", "#c87d0e",
				"#e1dca5", "#d0c974", "#a29a36", "#514d1b",
				"#c6d9f0", "#8db3e2", "#548dd4", "#17365d"
			})
			.Events(events => events.Change("preview"))
		)
```
```tagHelper

		@{
			string[] colorPickerPalette = new string[] {
                                        "#f0d0c9", "#e2a293", "#d4735e", "#65281a",
                                        "#eddfda", "#dcc0b6", "#cba092", "#7b4b3a",
                                        "#fcecd5", "#f9d9ab", "#f6c781", "#c87d0e",
                                        "#e1dca5", "#d0c974", "#a29a36", "#514d1b",
                                        "#c6d9f0", "#8db3e2", "#548dd4", "#17365d"
                                    };
		}
        <kendo-colorpalette name="palette" columns="4" on-change="preview" palette-colors="colorPickerPalette">
			<tile-size height="19" width="34" />
		</kendo-colorpalette>
```

## See Also

* [Basic Usage of the ColorPicker Tag Helper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/colorpicker/tag-helper)
* [JavaScript API Reference of the ColorPicker](https://docs.telerik.com/kendo-ui/api/javascript/ui/colorpicker)
