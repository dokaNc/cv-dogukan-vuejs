<template>
  <div>
    <v-container>
        <v-row>
            <v-col cols="12" md="12">
                <h1>Je me présente 👋</h1>
            </v-col>
            <v-col cols="12">
                <v-card rounded="lg" class="pa-5">
                    <v-card-title>
                        {{ firstName }} {{ lastName }}
                    </v-card-title>
                    <v-card-subtitle>
                        {{ title }}
                    </v-card-subtitle>
                    <v-card-text class="py-2" v-for="item in lineBreakAbout" :key="item">
                        {{ item }}
                    </v-card-text>
                    <v-card-text class="d-sm-flex align-center">
                        <v-chip-group class="mr-auto">
                            <v-chip
                                color="#9836F4"
                                v-for="(item, i) in softSkills"
                                :key="i"
                                small
                                outlined
                            >
                            {{ item }}
                            </v-chip>
                        </v-chip-group>

                        <v-avatar size="18">
                            <img alt="flag-fr" src="../../static/flags/fr.svg">
                        </v-avatar>
                        <v-avatar size="18" class="ml-2">
                            <img alt="flag-gb" src="../../static/flags/gb.svg">
                        </v-avatar>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
    name: 'presentation',

    props: {
        firstName: String,
        lastName: String,
        title: String,
        aboutMe: String,
        softSkills: Array
    },

    computed: {
        lineBreakAbout() {
            return this.aboutMe.split('. ')
        }
    }
}
</script>

<style>

</style>