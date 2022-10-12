<template>
  <div>
    <v-container>
        <v-row>
            <v-col cols="12">
                <h1>Expériences Développeur 🌐</h1>
            </v-col>
            <v-col cols="12">
                <timeline :cv="cv.experience.developpeur"></timeline>
            </v-col>
        </v-row>
    </v-container>
  </div>
</template>

<script>
import cvJson from '../assets/cv.json'
import timeline from '../components/cv/timeline'

export default {
    name: 'experience',

    data() {
        return {
            cv: cvJson
        }
    },

    components: {
      timeline
    }
}
</script>

<style>
</style>