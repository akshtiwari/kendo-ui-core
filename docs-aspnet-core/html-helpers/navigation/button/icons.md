---
title: Icon Button
page_title: Icon Button | Kendo UI Button HtmlHelper for ASP.NET Core
description: "Accommodate an icon and enhance the meaning of the text content of the Kendo UI Button HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: icons_button_aspnetcore
position: 2
---

# Icon Button

The Button can accommodate an icon which enhances the meaning of the text content.

The Button HtmlHelper provides the following methods for configuring icons:
* `Icon()`
* `SpriteCssClass()`
* `ImageUrl()`

Use only one of them with a particular Button instance. If you define multiple properties, only one of them will be obeyed according to the order stated above.

The `Icon()` method displays the appropriate [Kendo UI font icon](https://docs.telerik.com/kendo-ui/styles-and-layout/icons-web) as a content of a `<spn> :before` pseudo element. The Button enables you to completely omit any text to be specified for its contents.

```
@(Html.Kendo().Button()
	.Name("textButton")
	.Icon("delete")
)
```

The `SpriteCssClass()` method displays the icon as a background of a `span` element instead.

```
@(Html.Kendo().Button()
	.Name("textButton")
	.Content("Sample Button")
	.SpriteCssClass("myDeleteIcon")
)
```

Image icons are applied by using the `ImageUrl()` method and are displayed as an `img` element.

```
@(Html.Kendo().Button()
	.Name("textButton")
	.Content("Sample Button")
	.ImageUrl("url/to/myDeleteIcon.png")
)
```

## See Also

* [Adding Images to the Button HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/button/images)
* [JavaScript API Reference of the Button](http://docs.telerik.com/kendo-ui/api/javascript/ui/button)
