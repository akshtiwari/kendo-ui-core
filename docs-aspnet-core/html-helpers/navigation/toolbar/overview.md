---
title: Overview
page_title: ToolBar Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Kendo UI ToolBar HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/html-helpers/toolbar
slug: htmlhelpers_toolbar_aspnetcore
position: 1
---

# ToolBar HtmlHelper Overview

The [ToolBar](http://docs.telerik.com/kendo-ui/controls/navigation/toolbar/overview) is designed to hold different types of controls such as buttons, button groups, toggle buttons, split buttons, and other customized elements.

The ToolBar HtmlHelper extension is a server-side wrapper for the [Kendo UI ToolBar](http://demos.telerik.com/kendo-ui/toolbar/index) widget. For more information on the ToolBar HtmlHelper, refer to the [UI for ASP.NET MVC documentation](http://docs.telerik.com/aspnet-mvc/helpers/toolbar/overview).

## Initializing the ToolBar

The following example demonstrates how to define the ToolBar by using the ToolBar HtmlHelper.

```Razor
    @(Html.Kendo().ToolBar()
        .Name("ToolBar")
        .Items(items => {
            items.Add().Type(CommandType.Button).Text("Button");
            items.Add().Type(CommandType.Button).Text("Toggle Button").Togglable(true);
            items.Add().Type(CommandType.SplitButton).Text("Insert").MenuButtons(menuButtons =>
            {
                menuButtons.Add().Text("Insert above").Icon("insert-up");
                menuButtons.Add().Text("Insert between").Icon("insert-middle");
                menuButtons.Add().Text("Insert below").Icon("insert-down");
            });
        })
    )
```
```Controller
    public class ToolBarController : Controller
    {
        public ActionResult Index()
        {
            return View();
        }
    }
```

## Basic Configuration

The following example demonstrates the basic configuration of the ToolBar HtmlHelper.

```
    @(Html.Kendo().ToolBar()
        .Name("ToolBar")
        .Items(items => {
            items.Add().Type(CommandType.Button).Text("Button 1").Id("button1").Click("buttonClickHandler");
            items.Add().Type(CommandType.Button).Text("Button 2").Id("button2").Click("buttonClickHandler");
            items.Add().Type(CommandType.Separator);
            items.Add().Type(CommandType.Button).Togglable(true).Text("Toggle 1").Id("toggle1").Toggle("buttonToggleHandler");
            items.Add().Type(CommandType.Button).Togglable(true).Text("Toggle 2").Id("toggle2").Toggle("buttonToggleHandler");
            items.Add().Type(CommandType.Separator);
            items.Add().Template("<input id='dropdown' style='width: 150px;' />").Overflow(ShowInOverflowPopup.Never);
            items.Add().Type(CommandType.SplitButton).Text("Split Button").Id("mainButton").Click("splitButtonClickHandler").MenuButtons(menuButtons =>
            {
                menuButtons.Add().Text("Action 1").Id("action1");
                menuButtons.Add().Text("Action 2").Id("action2");
                menuButtons.Add().Text("Action 3").Id("action3");
            });
            items.Add().Type(CommandType.Separator);
            items.Add().Type(CommandType.ButtonGroup).Buttons(buttons =>
            {
                buttons.Add().Text("Radio 1").Id("radio1").Togglable(true).Group("radio").Toggle("buttonToggleHandler");
                buttons.Add().Text("Radio 2").Id("radio2").Togglable(true).Group("radio").Toggle("buttonToggleHandler");
                buttons.Add().Text("Radio 3").Id("radio3").Togglable(true).Group("radio").Toggle("buttonToggleHandler");
            });
            items.Add().Type(CommandType.Button).Text("Overflow button").Id("overflowButton").Overflow(ShowInOverflowPopup.Always);
        })
        .Events(e => e.Click("onClick").Toggle("onToggle").Open("onOpen").Close("onClose").OverflowOpen("onOverflowOpen").OverflowClose("onOverflowClose"))
    )

    <script type="text/javascript">
        $(function() {
    	    // Initialize a DropDownList in the template of a ToolBar item.
    		$("#dropdown").kendoDropDownList({
                optionLabel: "Paragraph",
                dataTextField: "text",
                dataValueField: "value",
                dataSource: [
                    { text: "Heading 1", value: 1 },
                    { text: "Heading 2", value: 2 },
                    { text: "Heading 3", value: 3 },
                    { text: "Title", value: 4 },
                    { text: "Subtitle", value: 5 },
                ]
            });

            // The Name() of the ToolBar is used to get its client-side instance.
            var toolbar = $("#ToolBar").data("kendoToolBar");
        });
    </script>
```


## Spacer

The `Spacer` command type moves the tools that are declared after it to the right side of the ToolBar.

The following example demonstrates how to define a spacer.

###### Example

```
    @(Html.Kendo().ToolBar()
        .Name("ToolBar")
        .Items(items => {
            items.Add().Type(CommandType.Button).Text("Button 1").Id("button1");
            items.Add().Type(CommandType.Spacer);
            items.Add().Type(CommandType.Button).Text("Button 2").Id("button2");
        })
    )
```

You can use multiple spacers to create an equal amount of space between several tools.

###### Example

```
    @(Html.Kendo().ToolBar()
        .Name("ToolBar")
        .Items(items => {
            items.Add().Type(CommandType.Button).Text("Button 1").Id("button1");
            items.Add().Type(CommandType.Spacer);
            items.Add().Type(CommandType.Button).Text("Button 2").Id("button2");
            items.Add().Type(CommandType.Spacer);
            items.Add().Type(CommandType.Button).Text("Button 3").Id("button3");
        })
    )
```

## Events

For a complete example on basic ToolBar events, refer to the [demo on using the events of the ToolBar](https://demos.telerik.com/aspnet-core/toolbar/events).

## See Also

* [Basic Usage of the ToolBar HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/toolbar)
* [Using the API of the ToolBar HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/toolbar/api)
* [JavaScript API Reference of the ToolBar](http://docs.telerik.com/kendo-ui/api/javascript/ui/toolbar)
