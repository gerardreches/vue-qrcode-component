
<template>
    <div id="qr-code"></div>
</template>

<script>
    import QRCode from 'qrcode-js-package/qrcode.js'
    export default {

        props: {
            text: {type: String, required: true},
            width: Number,
            height: Number,
            colorDark: String,
            colorLight: String
        },

        data() {
            return{
                qrcode: {}
            }
        },

        mounted() {
            this.qrcode = new QRCode(document.getElementById('qr-code'), {
                text: this.text,
                width: this.width,
                height: this.height,
                colorDark : "#000000",
                colorLight : "#ffffff",
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