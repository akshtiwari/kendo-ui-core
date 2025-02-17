---
title: Hint
page_title: Hint | Kendo UI Sortable for ASP.NET Core
description: "Disable the hint in the Kendo UI Sortable HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: hint_sortable_aspnetcore
position: 2
---

# Hint

By default, the Sortable renders a hint.  

To disable that behavior, set the hint to an empty function by using [`jQuery.noop`](http://api.jquery.com/jQuery.noop/).

```
    @(Html.Kendo().Sortable()
        .For("#sortable")
        .HintHandler("noHint")
    )

    <script>
        var noHint = $.noop;
    </script>
```

## See Also

* [JavaScript API Reference of the Sortable](http://docs.telerik.com/kendo-ui/api/javascript/ui/sortable)
