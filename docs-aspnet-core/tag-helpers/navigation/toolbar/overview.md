---
title: Overview
page_title: ToolBar Overview | Telerik UI for ASP.NET Core Tag Helpers
description: "Learn the basics when working with the Telerik UI ToolBar tag helper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
previous_url: /aspnet-core/helpers/toolbar, /aspnet-core/helpers/tag-helpers/toolbar
slug: taghelpers_toolbar_aspnetcore
position: 1
---

# ToolBar Tag Helper Overview

The Telerik UI ToolBar tag helper for ASP.NET Core is a server-side wrapper for the Kendo UI ToolBar widget.

The ToolBar is designed to hold different types of controls such as buttons, button groups, toggle buttons, split buttons, and other customized elements.

* [Demo page for the ToolBar](https://demos.telerik.com/aspnet-core/toolbar/tag-helper)

## Initializing the ToolBar

The following example demonstrates how to define the ToolBar by using the ToolBar tag helper.

    <kendo-toolbar name="ToolBar">
        <toolbar-items>
            <item type="CommandType.Button" text="Button 1" />
            <item type="CommandType.Separator" />
            <item type="CommandType.Button" text="Button 2" />
        </toolbar-items>
    </kendo-toolbar>

## Basic Configuration

The ToolBar tag helper configuration options are passed as attributes of the tag.

The following example demonstrates the basic configuration of the ToolBar tag helper.

```tagHelper

    <kendo-toolbar name="ToolBar">
        <toolbar-items>
            <item type="CommandType.Button" text="Button" />
            <item type="CommandType.Button" text="Toggle Button" togglable="true" />
            <item type="CommandType.SplitButton" text="Insert">
                <menu-buttons>
                    <toolbar-button text="Insert above" icon="insert-up" />
                    <toolbar-button text="Insert between" icon="insert-middle" />
                    <toolbar-button text="Insert below" icon="insert-down" />
                </menu-buttons>
            </item>
            <item type="CommandType.Separator" />
            <item template="<label for='dropdown'>Format:</label>" />
            <item template="<input id='dropdown' style='width: 150px;' />"     overflow="ShowInOverflowPopup.Never" />
            <item type="CommandType.Separator" />
            <item type="CommandType.ButtonGroup">
                <buttons>
                    <toolbar-button text="Left" togglable="true" group="text-align" icon="align-left"     />
                    <toolbar-button text="Center" togglable="true" group="text-align"     icon="align-center" />
                    <toolbar-button text="Right" togglable="true" group="text-align"     icon="align-right" />
                </buttons>
            </item>
            <item type="CommandType.Button" text="Action" overflow="ShowInOverflowPopup.Always"/>
            <item type="CommandType.Button" text="Another Action"     overflow="ShowInOverflowPopup.Always"/>
            <item type="CommandType.Button" text="Something else here"     overflow="ShowInOverflowPopup.Always"/>
        </toolbar-items>
    </kendo-toolbar>

    <script>
        $(document).ready(function () {
            // Initialize a DropDownList in a template of the ToolBar item.
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
```cshtml

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
            items.Add().Type(CommandType.Separator);
            items.Add().Template("<label for='dropdown'>Format:</label>");
            items.Add().Template("<input id='dropdown' style='width: 150px;' />").Overflow    (ShowInOverflowPopup.Never);
            items.Add().Type(CommandType.Separator);
            items.Add().Type(CommandType.ButtonGroup).Buttons(buttons =>
            {
                buttons.Add().Text("Left").Togglable(true).Group("text-align").Icon("align-left");
                buttons.Add().Text("Center").Togglable(true).Group("text-align").Icon("align-center");
                buttons.Add().Text("Right").Togglable(true).Group("text-align").Icon("align-right");
            });
            items.Add().Type(CommandType.ButtonGroup).Buttons(buttons =>
            {
                buttons.Add().Text("Bold").Togglable(true).Icon("bold");
                buttons.Add().Text("Italic").Togglable(true).Icon("italic");
                buttons.Add().Text("Underline").Togglable(true).Icon("underline");
            });
            items.Add().Type(CommandType.Button).Text("Action").Overflow(ShowInOverflowPopup.Always);
            items.Add().Type(CommandType.Button).Text("Another Action").Overflow    (ShowInOverflowPopup.Always);
            items.Add().Type(CommandType.Button).Text("Something else here").Overflow    (ShowInOverflowPopup.Always);
        })
    )

    <script>
        $(document).ready(function () {
            // Initialize a DropDownList in a template of the ToolBar item.
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

## See Also

* [Basic Usage of the ToolBar Tag lHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/toolbar/tag-helper)
* [API Reference of the ToolBar Helper for ASP.NET Core](/api/toolbar)
