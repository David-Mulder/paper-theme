Styling
===
The biggest difficulty is styling, because the way Polymer and the shadow DOM works it's incredibly hard to style elements that are hidden in the shadow DOM, as is the case for the cells. Dynamically setting up mixins isn't possible either however, so in the end the following compromise was reached:

Header cell and Row cell styling
---
It is possible to define a css string that will be applied to the header cell and all cells in a column like

	<paper-datatable-column [...] style="color:green;" cell-style="color:red;"></paper-datatable-column>

Which would make the header `green` and the content in each cell in the column `red`. This is especially useful to set a `min-width` on the header. There is also a convenience attribute `align='center'` to center columns (both the header and cells) and a convenience attribute `width` to set the minimum width.

Tip: Check the `theming.html` demo for a live demonstration.

<paper-datatable>
===

 Custom property | Description | Default
 ----------------|-------------|----------
 `--paper-datatable-divider-color` | divider color between rows | `--divider-color`
 `--paper-datatable-row-selection-color` | divider color between rows | `--paper-grey-100`
 `--paper-datatable-row-hover-color` | color of hovered row | `--paper-grey-200`
 `--paper-datatable-header-checkbox-color` | checkbox color | `--primary-text-color`

Mixins
---

 Mixin | Description
 ------|-------------
 `--paper-datatable-column-header` | column header style applied to text headers
 `--paper-datatable-cell` | applied to all data cells
 `--paper-datatable-cell-last` | applied to the last cell of each row (used to increase the `padding-right` if you overwrite it in `--paper-datatable-cell`)
 `--paper-datatable-column-header-sorted` | applied to the sort icon
 `--paper-datatable-column-header-sort-icon-hover` | applied to the sort icon when hovered
 `--paper-datatable-array-item` | oly works when using the proper Shadow DOM and is applied to columns using the `array-display-prop` attribute.
 `--paper-datatable-class-1` | only works when using the proper Shadow DOM and is applied to any content in cells with `class='class-1'`.
 `--paper-datatable-class-2` | only works when using the proper Shadow DOM and is applied to any content in cells with `class='class-2'`.
 `--paper-datatable-class-3` | only works when using the proper Shadow DOM and is applied to any content in cells with `class='class-3'`.
 `--paper-datatable-class-4` | only works when using the proper Shadow DOM and is applied to any content in cells with `class='class-4'`.
 `--paper-datatable-class-5` | only works when using the proper Shadow DOM and is applied to any content in cells with `class='class-5'`.

<paper-datatable-card>
===
Variables
---
 Custom property | Description | Default
 ----------------|-------------|----------
 `--paper-datatable-divider-color` | divider color is used to draw the bottom line | --divider-color
 `--paper-datatable-selection-toolbar-color` | color of selected toolbar, should be 50 of the secondary color | --paper-pink-50
 `--paper-datatable-navigation-bar-text-color` | color of text in navigation bar | 

Mixins
---

 Mixin | Description
 ------|-------------
 `--paper-datatable-card` | applied to the main card
 `--paper-datatable-navigation-bar` | applied to the bottom bar containing the navigation
