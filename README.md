# CKEditor5 - Custom CKEditor5 build for React

## Description
This is a custom build editor, based on the Classic editor build from CKEditor5. It contains a list of available plugins, that can be easily customized and used in your React project.

## Available plugins
Here is a [list](https://ckeditor.com/docs/ckeditor5/latest/installation/getting-started/predefined-builds.html#list-of-plugins-included-in-the-ckeditor-5-predefined-builds) of the currently available plugins in this editor from which you can choose and use, based on your needs:
- Autoformat
- BasicStyles
- BlockQuote
- CloudServices
- CodeBlock
- EditorClassic
- Essentials
- Font
- Heading
- Image
- Indent
- Link
- List
- MediaEmbed
- Paragraph
- PasteFromOffice
- SourceEditing
- Table
- Typing
- Undo

## Installation
In order to use CKEditor5, we need to install two packages. Open a terminal in your project and run the following commands to install both of them:

1. Official [CKEditor 5](https://ckeditor.com/docs/ckeditor5/latest/installation/integrations/react.html) rich text editor component for React
`npm i @ckeditor/ckeditor5-react`

2. This custom build of the CKEditor5 for React
`npm i react-ckeditor5-custom`

## Usage
Once we have both of the needed packages installed, we can start implementing the editor into our project. 

This is one simple example of how the editor could be used in our project.
It will show only the specified features in the editor's toolbar, in the same order and grouped based on the '|' symbol.
```js
import React from 'react'
import { CKEditor } from  '@ckeditor/ckeditor5-react'
import  Editor  from  'react-ckeditor5-custom'

const MyApp = () => {
	return (
		<>
			<CKEditor
				editor={Editor}
				config={{
					toolbar: [
						'undo', 'redo', '|', 
						'fontSize', 'fontColor', 'fontBackgroundColor', '|', 
						'bold', 'italic', 'underline'
					]
				}}
				data={'This is my content'}
				onChange={(event) => {
					console.log(event)
				}}
			/>
		</>
	)
}
export default MyApp
```

If we want our editor to include all of the available features, then we just use the editor without specifically configuring the toolbar. Simply leave it out. Please note, that this will add all of the features, in a predefined order by the editor.
```js
...
    <CKEditor
	    editor={Editor}
	    data={'This is my content'}
	    onChange={(event) => {
		    console.log(event)
	    }}
    />
...
```

In the case that we want to use most of the available features, except for a few, we can simply remove them.
```js
...
	<CKEditor
		editor={Editor}
		config={{
			toolbar: {
				removeItems: ['bold', 'fontColor', 'imageUpload']
			}
		}}
		data={'This is my content'}
		onChange={(event) => {
			console.log(event)
		}}
	/>
...
```
For more ways to customize your editor, please visit the official [CKEditor5](https://ckeditor.com/docs/ckeditor5/latest/index.html) documentation.

## Component properties
To see the details about all of the component's properties, please visit this link from the official [CKEditor5](https://ckeditor.com/docs/ckeditor5/latest/installation/integrations/react.html#component-properties) documentation. Go through all of them and read them carefully, so you can further customize the editor based on your requirements.

## Editing the toolbar
In order to add / remove features from the toolbar, we can specify which features we want to include by adding them to the toolbar list in the configuration. If we want to show all available features, we can leave out the toolbar list.
<br>Check out the official documentation for more [features](https://ckeditor.com/docs/ckeditor5/latest/features/index.html).

Here is the list of all currently available features that can be used:
```js
toolbar: [
    'undo', 'redo', 'fontFamily','fontSize', 'fontColor',   'fontBackgroundColor', 'bold', 'italic', 'underline',   'strikethrough', 'link', 'imageUpload', 'insertTable', 'blockQuote', 'bulletedList', 'numberedList', 'outdent', 'indent', 'mediaEmbed', 'codeBlock', 'subscript', 'superscript', 'strikethrough', 'code', 'sourceEditing'
]
```
## Adding or removing plugins
TODO

## Rebuilding editor
TODO 

## License
Licensed under the terms of the [MIT License](http://en.wikipedia.org/wiki/MIT_License). For full details about the license, please check the `LICENSE.md` file or visit [CKEditor5's](https://ckeditor.com/docs/ckeditor5/latest/support/licensing/license-and-legal.html) page.

## Screenshots
![Editor1](https://i.postimg.cc/ZRF9HYjJ/Editor1.png)
![Editor2](https://i.postimg.cc/fyzVr4gm/Editor2.png)
![Editor3](https://i.postimg.cc/mkmPxd0q/Editor3.png)
![Editor4](https://i.postimg.cc/44P7hdm5/Editor4.png)
