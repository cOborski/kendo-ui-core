---
title: Templates
page_title: Templates | Telerik UI MultiSelect HtmlHelper for ASP.NET Core
description: "Use templates and customize the rendering of the items, tags, and the popup header of the Telerik UI MultiSelect HtmlHelper for ASP.NET Core (MVC 6 or ASP.NET Core MVC)."
slug: htmlhelpers_multiselect_templates_aspnetcore
position: 4
---

# Templates

The MultiSelect provides full control over the way items, tags, or a pop-up header is rendered through the Kendo UI for jQuery templates.

## Basic Usage

The following example demonstrates how to customize the MultiSelect by referencing a script tag by its `id`.

    <!-- Template -->
    <script id="itemTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#, CustomerID: #:data.CustomerID#
    </script>

    <!-- MultiSelect initialization -->
    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .ItemTemplateId("itemTemplate") //Reference to the template
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

The following example demonstrates how to customize the MultiSelect by declaring an inline string.

    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .ItemTemplate("<span><h3>#: data.ContactName #</h3><p>#: data.CompanyName #</p></span>")
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

## Item Template

The item template manages the way the list items of a MultiSelect are rendered.

The following example demonstrates how to define an item template and how to evaluate it against the `dataItem`.

    <!-- Template -->
    <script id="itemTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#, CustomerID: #:data.CustomerID#
    </script>

    <!-- MultiSelect initialization -->
    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .ItemTemplateId("itemTemplate") // Reference to the template.
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

## Tag Template

The tag template manages the way the tag of a MultiSelect is rendered.

The following example demonstrates how to define a tag template.

    <!-- Template -->
    <script id="tagTemplate" type="text/x-kendo-template">
        ContactName: #:data.ContactName#
    </script>

    <!-- MultiSelect initialization -->
    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .TagTemplateId("tagTemplate") // Reference to the template.
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

## Header Template

The header template manages the way the pop-up header of a MultiSelect is rendered.

The following example demonstrates how to define a header template.

    <!-- Template -->
    <script id="headerTemplate" type="text/x-kendo-template">
        <strong>Header</strong>
    </script>

    <!-- MultiSelect initialization -->
    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .HeaderTemplateId("headerTemplate") // Reference to the template.
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

## Footer Template

The footer template manages the way the pop-up footer of a MultiSelect is rendered. The footer is re-rendered on every change of the DataSource. The context of the template is the widget itself.

The following example demonstrates how to define a footer template.

    <!-- Template -->
    <script id="footerTemplate" type="text/x-kendo-template">
        Total <strong>#: instance.dataSource.total() #</strong> items found
    </script>

    <!-- MultiSelect initialization -->
    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .FooterTemplateId("footerTemplate") // Reference to the template.
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

## No-Data Templates

The MultiSelect displays `noDataTemplate` in the popup when the data source is empty.

The following example demonstrates how to define a `noDataTemplate` template.

    <!-- Template -->
    <script id="noDataTemplate" type="text/x-kendo-template">
        <strong>No Data!</strong>
    </script>

    <!-- MultiSelect initialization -->
    @(Html.Kendo().MultiSelect()
        .Name("customers")
        .DataTextField("ContactName")
        .DataValueField("CustomerID")
        .NoDataTemplateId("noDataTemplate") // Reference to the template.
        .DataSource(source =>
        {
            source.Read(read =>
            {
                read.Action("Customers_Read", "MultiSelect");
            });
        })
    )

## See Also

* [Customizing Templates in the MultiSelect HtmlHelper for ASP.NET Core (Demo)](https://demos.telerik.com/aspnet-core/multiselect/template)
* [API Reference of the MultiSelect HtmlHelper for ASP.NET Core](/api/multiselect)
