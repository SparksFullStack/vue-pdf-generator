<template>
    <section class="hero is-primary is-fullheight">
        <div class="hero-body">
            <div class="container">
                <div class="columns is-centered">
                    <div class="column is-4-widescreen is-5-desktop is-6-tablet">
                        <div class="box">
                            <div class="field has-text-centered">
                                <h1 class="is-size-2">PDF Testing</h1>
                            </div>
                            <div class="field">
                                <textarea v-model="inputString" name="pdfText" id="pdfText" cols="30" rows="10" class="textarea" placeholder="PDF text..."></textarea>
                            </div>
                            <div class="field">
                                <button @click="handleRenderPdf" class="button is-info generator-buttons">Generate!</button>
                                <button @click="handleOpenPdf" class="button is-4 generator-buttons generator-buttons__margin-left">Print</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
/* eslint-disable */
const pdfMake = require('pdfmake/build/pdfmake.js');
const pdfFonts = require('pdfmake/build/vfs_fonts.js');
pdfMake.vfs = pdfFonts.pdfMake.vfs;

export default {
    name: 'pdfInput',
    data() {
        return {
            inputString: '',
            newPdf: undefined
        }
    },
    created() {
        console.log('pdfMake', pdfMake);
    },
    methods: {
        handleRenderPdf() {
            const documentDefinition = { content: { text: this.inputString } };
            this.newPdf = pdfMake.createPdf(documentDefinition);
            alert('A new PDF has been generated');
        },
        handleOpenPdf() {
            if (!this.newPdf) {
                alert('Please generate a PDF before trying to open')
            } else {
                this.newPdf.open();
            }
        }
    }
}
</script>

<style scoped>
    .generator-buttons {
        width: 100px;
    }

    .generator-buttons__margin-left {
        margin-left: 10px;
    }
</style>