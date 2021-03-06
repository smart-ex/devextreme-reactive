# Grid Reference

The Grid is a root container component designed to process and display data specified via the `rows` property. You can configure columns using the `columns` property. The Grid's functionality (data visualization and data processing) is implemented in several plugins specified as child components. See the [plugins concept](../README.md#plugins-overview) for details.

## User reference

### Properties

Name | Type | Default | Description
-----|------|---------|------------
rows | Array&lt;any&gt; | | An array containing custom data. A user defines the access to this data. Refer to [Data Accessors](../guides/data-accessors.md) for details.
columns | Array&lt;[Column](#column)&gt; | | Specifies for which row fields columns are created.
getRowId? | (row: any) => number &#124; string | | Specifies the function used to get a unique row identifier.
getCellValue? | (row: any, columnName: string) => any | | Specifies the function used to get a cell's value.
rootComponent | ComponentType&lt;[Grid.RootProps](#gridrootprops)&gt; | | A component that renders the grid root layout.

## Interfaces

### Column

Defines the column configuration object. Used to display data stored in a row.

Field | Type | Description
------|------|------------
name | string | Specifies the column name or the name of a row field whose value the column displays. If the column name does not match any field name, specify the `getCellValue` function.
title? | string | Specifies the column title.
getCellValue? | (row: any, columnName: string) => any | Specifies the function used to get the column value for a given row.

### Grid.RootProps

Describes properties passed to a component that renders the grid root layout.

Field | Type | Description
------|------|------------
children? | ReactNode | A React node to be placed in the root layout.

## Plugin Components

Name | Properties | Description
-----|------------|------------
Grid.Root | [Grid.RootProps](#gridrootprops) | A component that renders the grid root layout.

If you specify additional properties, they are added to the component's root element.

## Plugin Developer Reference

### Exports

Name | Plugin | Type | Description
-----|--------|------|------------
rows | Getter | Array&lt;any&gt; | Grid rows.
getRowId | Getter | (row: any) => number &#124; string | A function used to get a unique row identifier.
columns | Getter | Array&lt;[Column](#column)&gt; | Grid columns.
getCellValue | Getter | (row: any, columnName: string) => any | A function used to get a given row's column value.
root | Template | Object? | A template that renders the grid root layout.
header | Template | Object? | A template that renders the grid header.
body | Template | Object? | A template that renders the grid body.
footer | Template | Object? | A template that renders the grid footer.
