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
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'pdfInput',
    data() {
        return {
            inputString: ''
        }
    }
}
</script>

<style scoped>

</style>