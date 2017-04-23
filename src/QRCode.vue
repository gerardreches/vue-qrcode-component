
<template>
    <div :id="id"></div>
</template>

<script>
    import QRCode from 'qrcode-js-package/qrcode.js'
    export default {

        props: {
            id: {type: String, required: true},
            text: {type: String, required: true},
            size: {type: Number, required: false, default: 256},
            colorDark: {type: String, required: false, default: '#000000'},
            colorLight: {type: String, required: false, default: '#FFFFFF'}
        },

        data() {
            return{
                qrCode: {}
            }
        },

        mounted() {
            this.qrCode = new QRCode(document.getElementById(this.id), {
                text: this.text,
                width: this.size,
                height: this.size,
                colorDark : this.colorDark,
                colorLight : this.colorLight,
                correctLevel : QRCode.CorrectLevel.H
            });
        },

        methods: {
            clear: function () {
                this.qrCode.clear();
            },
            makeCode: function (text) {
                this.qrCode.makeCode(text);
            }
        }
    }
</script>