---
title: Keyboard Navigation
page_title: Keyboard Navigation | Kendo UI MultiViewCalendar Tag for ASP.NET Core
description: "Use the Kendo UI MultiViewCalendar keyboard navigation."
slug: keyboard_navigation_multiviewcalendar_taghelper_aspnetcore
position: 8
---

# Keyboard Navigation

The keyboard navigation of the MultiViewCalendar is always available.

The MultiViewCalendar supports the following keyboard shortcuts:

| Shortcut            | Description                                  |
|:---                 |:---                                          |
| `Up Arrow`          | Highlights the same day from the previous week.  |
| `Down Arrow`        | Highlights the same day from the next week.      |
| `Left Arrow`        | Highlights the previous day.                     |
| `Right Arrow`       | Highlights the next day.                         |
| `Enter`             | Selects the focused date.                    |
| `Home`              | Focuses the first date in the month.         |
| `End`               | Focuses the last date in the month.          |
| `Ctrl`+`Up Arrow`   | Navigates to the previous view.                  |
| `Ctrl`+`Down Arrow` | Navigates to the next view.                      |
| `Ctrl`+`Down Left`  | Navigates to the previous month.                 |
| `Ctrl`+`Down Right` | Navigates to the next month.                     |

```tagHelper

    <kendo-multiviewcalendar name="multiviewcalendar" selectable="multiple">        
    </kendo-multiviewcalendar>

```
```Razor

        @(Html.Kendo().MultiViewCalendar()
            .Name("MultiViewCalendar")
            .Selectable("multiple")
        )
```

## See Also

* [JavaScript API Reference of the MultiViewCalendar](http://docs.telerik.com/kendo-ui/api/javascript/ui/multiviewcalendar)
