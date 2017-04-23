# vue-qrcode-component
Vue component that generates a QR code from a given string.

## Installation

Install the package: 
```
// Using NPM
npm install vue-qrcode-component

// or Yarn
yarn add vue-qrcode-component
```
Then register the component:
```js
import Vue from 'vue'
import VueQRCodeComponent from 'vue-qrcode-component'
Vue.component('qr-code', VueQRCodeComponent)
```
Now you can use it as
```html
<qr-code id="my-qrcode" text="Text to transform"></qr-code>
```

## Usage

These are the component props:
```js
id: {type: String, required: true},
text: {type: String, required: true},
size: {type: Number, required: false, default: 256},
colorDark: {type: String, required: false, default: '#000000'},
colorLight: {type: String, required: false, default: '#FFFFFF'}
```
A **unique id is required** for a `document.getElementById('id')` operation. A **text is also required**, cause the generated QR code will represent that text.

You can also change the size in _px_ of the QR code (256px by default) and their colors (traditional black & white by default).

### Example

We will generate a QR code that gives an URL to this repo on decode. It measures 500x500 px, uses a yellow color for the code and a blue color for the background.

```html
<qr-code 
    id="my-qr-code" 
    text="https://github.com/gerardreches/vue-qrcode-component"
    size="500"
    colorDark="#f1c40f"
    colorLight="#3498db">
</qr-code>
```

## Help

Feel free to open an issue if you have any problem using this component.
