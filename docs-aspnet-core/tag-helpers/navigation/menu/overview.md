---
title: Overview
page_title: Menu Overview | Telerik UI for ASP.NET Core Tag Helpers
description: "Learn the basics when working with the Telerik UI Menu tag helper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: taghelpers_menu_aspnetcore
previous_url: /aspnet-core/helpers/tag-helpers/menu
position: 1
---

# Menu Tag Helper Overview

The Telerik UI Menu tag helper for ASP.NET Core is a server-side wrapper for the Kendo UI Menu widget.

The Menu displays hierarchical data as a multi-level menu. It provides rich styling for unordered lists of items, and can be used for both navigation and execution of JavaScript commands.

* [Demo page for the Menu](https://demos.telerik.com/aspnet-core/menu/tag-helper)

## Initializing the Menu

The following example demonstrates how to define the Menu by using the Menu tag helper.

		<kendo-menu name="menu">
		</kendo-menu>

## Basic Configuration

To pass the Menu items collection, either:

* Use the nested `<items>` tag, or
* Add `<li>` tags. This approach will not include the `menu-item` tag helper attributes.

```tagHelper
<kendo-menu name="menu">
    <items>
        <menu-item text="Home"></menu-item>
        <menu-item text="Second Page"></menu-item>
    </items>
</kendo-menu>
```
```tagHelper-li
<kendo-menu name="menu">
    <li>Home</li>
    <li>Second Page</li>
</kendo-menu>
```
```cshtml
@(Html.Kendo().Menu()
		.Name("menu")
		.Items(items => {
				items.Add().Text("Home");
				items.Add().Text("Second Page");
		})
)
```

To further configure the Menu tag helper, use its other options&mdash;`<open-on-click>`, `<popup-animation>`, and `<scrollable>`.

```tagHelper
<kendo-menu name="menu">
    <items>
        <menu-item text="Home"></menu-item>
        <menu-item text="Second Page"></menu-item>
    </items>
    <open-on-click enabled="true" root-menu-items="true" sub-menu-items="false" />
    <popup-animation>
        <open duration="500" />
        <close duration="300" />
    </popup-animation>
    <scrollable enabled="false" />
</kendo-menu>
```
```cshtml
@(Html.Kendo().Menu()
    .Name("menu")
    .Items(items => {
        items.Add().Text("Home");
        items.Add().Text("Second Page");
    })
    .OpenOnClick(open => open.RootMenuItems(true).SubMenuItems(false))
    .Animation(animation =>
        animation.Open(open => open.Duration(500))
                 .Close(close => close.Duration(300))
    )
    .Scrollable(true)
)
```

## Functionality and Features

The Menu provides options for [setting up its items]({% slug items_menu_aspnetcore %}).

## See Also

* [Basic Usage of the Menu Tag Helper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/menu/tag-helper)
* [API Reference of the Menu Helper for ASP.NET Core](/api/menu)
