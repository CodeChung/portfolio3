<template>
    <div class="portfolio">
        <h1>Port<span style="color:#bfd5ff;">folio</span></h1>
        <p>proyects</p>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: 'Portfolio',
            meta: [
                {
                    hid: 'portfolio',
                    name: 'portfolio',
                    content: 'Whoa check out Harrys projects'
                }
            ]
        }
    }
}
</script>

<style>
.portfolio {
    padding-top: 30px;
    max-width: 90%;
    margin: 0 auto;
}
</style>