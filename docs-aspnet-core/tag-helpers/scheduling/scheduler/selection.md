---
title: Selection
page_title: Selection | Telerik UI Scheduler Tag Helper for ASP.NET Core
description: "Enable the selection of events in the Telerik UI Scheduler tag helper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: selection_scheduler_aspnetcore
position: 2
---

# Selection

The Scheduler supports enables the user to select events.

By default, the `selectable` option is disabled.

```cshtml
        @(Html.Kendo().Scheduler<Kendo.Mvc.Examples.Models.Scheduler.TaskViewModel>()
        .Name("scheduler")
        .Height(600)
        .Selectable(true)
        )
```
```tagHelper
        <kendo-scheduler name="scheduler" height="600" selectable="true">
        </kendo-scheduler>
```

## See Also

* [API Reference of the Scheduler Helper for ASP.NET Core](/api/scheduler)
