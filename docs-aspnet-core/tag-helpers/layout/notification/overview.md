---
title: Overview
page_title: Notification Overview | Telerik UI for ASP.NET Core Tag Helpers
description: "Learn the basics when working with the Kendo UI Notification tag helper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/notification, /aspnet-core/helpers/tag-helpers/notification
slug: taghelpers_notification_aspnetcore
position: 1
---

# Notification Tag Helper Overview

The [Notification](http://docs.telerik.com/kendo-ui/controls/layout/notification/overview) provides a styled UI widget with arbitrary content which can provide information to the user on various occasions.

The Notification tag helper extension is a server-side wrapper for the [Kendo UI Notification](http://demos.telerik.com/kendo-ui/notification/index) widget and enables you to configure the Kendo UI Notification widget in ASP.NET Core applications.

## Initializing the Notification

The following example demonstrates how to define the Notification by using the Notification tag helper.

        <kendo-notification name="notification" auto-hide-after="0"></kendo-notification>

## Basic Configuration

The Notification tag helper configuration options are passed as attributes of the tag and through nested tags.

```cshtml

	@(Html.Kendo().Notification()
		.Name("notification")
		.Position(p => p.Pinned(true).Top(30).Right(30))
		.Stacking(NotificationStackingSettings.Down)
		.AutoHideAfter(0)
		.Templates(t =>
		{
			t.Add().Type("info").ClientTemplateID("emailTemplate");
			t.Add().Type("error").ClientTemplateID("errorTemplate");
			t.Add().Type("upload-success").ClientTemplateID("successTemplate");
		})
		.Animation(a => a.Open(e => e.Duration(500)).Close(e => e.Duration(0)))
	)

```
```tagHelper

	<kendo-notification name="notification"
				        stacking="NotificationStackingSettings.Down"
				        auto-hide-after="0">
		<position pinned="true" top="30" right="30" />
		<templates>
			<notification-template type="info" template-id="emailTemplate" />
			<notification-template type="error" template-id="errorTemplate" />
			<notification-template type="upload-success" template-id="successTemplate" />
		</templates>
		<popup-animation>
			<open duration="500" />
			<close duration="0" />
		</popup-animation>
	</kendo-notification>
```

## See Also

* [Basic Usage of the Notification Tag Helper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/notification/tag-helper)
* [JavaScript API Reference of the Notification](http://docs.telerik.com/kendo-ui/api/javascript/ui/notification)
