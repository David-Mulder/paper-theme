# paper-datatable

A [material design implementation of a data table](https://www.google.com/design/spec/components/data-tables.html). Let's call this a pretty solid beta.

 - Documentation can be found here: http://david-mulder.github.io/paper-datatable/components/paper-datatable/
 - Demos can be found here: http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/

[![http://david-mulder.github.io/paper-datatable/components/paper-datatable/docs/screenshot.png](http://david-mulder.github.io/paper-datatable/components/paper-datatable/docs/screenshot.png)](http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/complex-paper-datatable-card.html)

## Features

 - Custom `<template>`'ing of every cell.

		<paper-datatable-column header="Page" property="page">
			<template>
				<span>{{value}}</span>
			</template>
		</paper-datatable-column>

 - Two way binding directly into the `paper-datatable`

		<paper-datatable-column header="Page" property="page">
			<template>
				<paper-input value="{{value}}">
			</template>
		</paper-datatable-column>
 - Extremely simple to set up ([simple demo](http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/simple.html))
 - Pretty good styling support ([demo](http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/theming.html))
 - Pagination and external data sources ([demo](http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/users-card.html))
 - Supporting both inline editing and in Material Design dialogs.
 - ~~Add new items on the fly ([unpolished demo](http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/paper-datatable-card.html))~~
 - [Delightful details](https://www.google.com/design/spec/animation/delightful-details.html) in sorting and partial selections. If you have ideas for more: let me know.
 - Usable on mobile. Only tested on Chrome for Android, and it's not great, but it doesn't overflow or overlap anything.

## Installation

The element can be installed using bower using

    bower install --save paper-datatable

**Important:** If you wish to use `<paper-datatable-card>` you need the paper elements listed in `devDependencies` as well. They are not listed as normal dependencies to prevent them from being pulled in on production if you do not need them.

## Usage

Honestly, the best thing you can do right now is simply check out [the demos](http://david-mulder.github.io/paper-datatable/components/paper-datatable/demo/). Either way, there are two main elements in this component:

 - `<paper-datatable>` generates the basic datatable
 - `<paper-datatable-card>` wraps the `<paper-datatable>` and simplifies the creation of features like pagination, etc.

And you can find the full documentation [here](http://david-mulder.github.io/paper-datatable/components/paper-datatable/)

### `<paper-datatable>` example

```html
<paper-datatable data="{{data}}">
  <!-- a plaintext sortable column -->
  <paper-datatable-column header="Title" property="title" sortable></paper-datatable-column>
  <!-- an editable column -->
  <paper-datatable-column header="Author" property="title" editable></paper-datatable-column>
  <!-- a custom column -->
  <paper-datatable-column header="Page" property="page">
	<template>
	  <!--
		this template is used for every cell in this column, you have access to:
		 - `{{value}}`: The value of the current property (`data.n.page`)
		 - `{{item}}`: The value of the current item (`data.n`)
	  -->
	  <paper-input value="{{value}}">
	</template>
  </paper-datatable-column>
</paper-datatable>
```

## License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License version 3 of the License as published by
the Free Software Foundation.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

This project uses a fair share license construction, if you wish to use this project commercially you will likely want to
continue reading [here](https://github.com/David-Mulder/fair-share-license/blob/master/CONTRIBUTING.md). If you wish to
donate please contact me personally.

## Contributing

I absolutely HATE rejecting pull requests, so let me just outline some advice:

 1. If you are planning on doing anything except a quick fix, it's a wise idea to open an issue first with your plans. That
    way we can talk it through and check whether it might not already be easily possible and whether it fits with the
    spirit of the component (I try to keep everything pretty declarative, generic and Polymer-y).
 2. You absolutely *must* make every feature you work on at least a separate commit and ideally a separate pull request.
    This both makes it clearer to me what is what, makes it easier to pull only the relevant parts and prevents situations
    where I can't give credits to the good parts, because of the bad parts.
 3. You have to explicitly agree in your pull request to the terms described in the
    [fair share license construction](https://github.com/David-Mulder/fair-share-license/blob/master/CONTRIBUTING.md).