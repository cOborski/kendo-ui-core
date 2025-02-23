---
title: Overview
page_title: Calendar Overview | Telerik UI for ASP.NET Core HtmlHelpers
description: "Learn the basics when working with the Telerik UI Calendar HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: overview_calendarhelper_aspnetcore
position: 1
---

# Calendar HtmlHelper Overview

The Telerik UI Calendar HtmlHelper for ASP.NET Core is a server-side wrapper for the Kendo UI Calendar widget.

The Calendar renders a graphical calendar that provides navigation and selection functionalities.

* [Demo page for the Calendar](https://demos.telerik.com/aspnet-core/calendar/index)

## Initializing the Calendar

The following example demonstrates how to define the Calendar by using the Calendar HtmlHelper.

```
    @(Html.Kendo().Calendar()
        .Name("calendar") // The name of the Calendar is mandatory. It specifies the "id" attribute of the widget.
        .Min(new DateTime(2010, 1, 1, 10, 0, 0)) // Set the min time of the Calendar.
        .Max(new DateTime(2020, 1, 1, 20, 0, 0)) // Set the min date of the Calendar.
        .Value(DateTime.Now) // Set the value of the Calendar.
    )
```

## Events

You can subscribe to all Calendar events. For a complete example on basic Calendar events, refer to the [demo on using the events of the Calendar](https://demos.telerik.com/aspnet-core/calendar/events).

### Handling by Handler Name

The following example demonstrates how to subscribe to events by a handler name.

```
    @(Html.Kendo().Calendar()
      .Name("calendar")
      .Events(e => e
          .Change("calendar_change")
          .Navigate("calendar_navigate")
      )
    )
    <script>
        function calendar_navigate(e) {
            // Handle the navigate event.
            var calendar = e.sender;
        }

        function calendar_change(e) {
            // Alerts the selected date with kendo.alert().
            var calendar = e.sender;
            kendo.alert(calendar.value());
        }
    </script>
```

### Handling by Template Delegate

The following example demonstrates how to subscribe to events by a template delegate.

```
    @(Html.Kendo().Calendar()
      .Name("calendar")
      .Events(e => e
          .Change(@<text>
            function(e) {
              // Handle the change event inline.
              console.log(e.sender.value());
            }
          </text>)
          .Navigate(@<text>
            function(e) {
              // Handle the navigate event inline.
              console.log(e.sender);
            }
            </text>)
      )
    )
```

## Referencing Existing Instances

To reference an existing Telerik UI Calendar instance, use the [`jQuery.data()`](https://api.jquery.com/jQuery.data/) configuration option. Once a reference is established, use the [Calendar API](/api/calendar) to control its behavior.

```
    // Place this after your Telerik UI Calendar for ASP.NET Core declaration.
    <script>
         $(function() {
            // The Name() of the Calendar is used to get its client-side instance.
            var calendar = $("#calendar").data("kendoCalendar");
         });
    </script>
```

## See Also

* [Basic Usage of the Calendar HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/calendar/index)
* [Using the API of the Calendar HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/calendar/api)
* [API Reference of the Calendar HtmlHelper for ASP.NET Core](/api/calendar)
