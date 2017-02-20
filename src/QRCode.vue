
<template>
    <div :id="id"></div>
</template>

<script>
    import QRCode from 'qrcode-js-package/qrcode.js'
    export default {

        props: {
            id: {type: String, required: true},
            text: {type: String, required: true},
            size: Number,
            colorDark: String,
            colorLight: String
        },

        data() {
            return{
                qrcode: {}
            }
        },

        mounted() {
            this.qrcode = new QRCode(document.getElementById(this.id), {
                text: this.text,
                width: typeof this.size !== "undefined" ? this.size : 256,
                height: typeof this.size !== "undefined" ? this.size : 256,
                colorDark : typeof this.colorDark !== "undefined" ? this.colorDark : "#000000",
                colorLight : typeof this.colorLight !== "undefined" ? this.colorLight : "#ffffff",
                correctLevel : QRCode.CorrectLevel.H
            });
        },

        methods: {
            clear: function () {
                this.qrcode.clear();
            },
            makeCode: function (text) {
                this.qrcode.makeCode(text);
            }
        }
    }
</script>