---
title: Multiple Views
page_title: Multiple Views | Kendo UI MultiViewCalendar HtmlHelper for ASP.NET Core
description: "Control the visible date ranges in the Kendo UI MultiViewCalendar and manage the number of its horizontally rendered views."
slug: multiple_views_multiviewcalendar_htmlhelper_aspnetcore
position: 3
---

# Multiple Views

The Kendo UI MultiViewCalendar allows you to define the number of views and months that are displayed at a time.

In some scenarios it might be necessary to display more than two months. This is especially helpful when performing range selection between months.

```Razor
        @(Html.Kendo().NumericTextBox()
            .Name("numberOfViews")
            .RestrictDecimals(true)
            .Decimals(0)
            .Min(2)
            .Max(10)
            .Value(2)
            .Format("{0:n0}")
        )
        @(Html.Kendo().Button()
            .Name("numberOfViewsBtn")
            .Content("Apply Changes")
            .Events(ev => ev.Click("click"))
        )
        @(Html.Kendo().MultiViewCalendar()
                .Name("multiViewCalendar")
        )

        <script>
            function click() {
                var numberOfViews = $("#numberOfViews").data().kendoNumericTextBox.value();
                if (numberOfViews > 0) {
                    $("#multiViewCalendar").data().kendoMultiViewCalendar.setOptions({ numberOfVies: numberOfViews });
                }
            }
        </script>
```

## See Also

* [Multiple Views in the MultiViewCalendar HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/multiviewcalendar/multiple-views)
* [View Selection in the MultiViewCalendar HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/multiviewcalendar/view-selection)
* [JavaScript API Reference of the MultiViewCalendar](http://docs.telerik.com/kendo-ui/api/javascript/ui/multiviewcalendar)
