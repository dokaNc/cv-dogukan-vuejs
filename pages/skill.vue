<template>
    <div>
        <langageAndTool />
    </div>
</template>

<script>
import langageAndTool from '../components/cv/langageAndTool.vue'
import cvJson from '../assets/cv.json'

export default {
    name: 'skill',

    data() {
        return {
            cv: cvJson
        }
    },

    components: {
        langageAndTool
    }
}
</script>

<style>

</style>