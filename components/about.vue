<template>
    <div>
        <v-container fluid>
            <v-row class="white" align="center">
                <v-col class="pa-0" cols="12" md="6">
                    <v-img :src="require('../static/profil.jpg')" height="450">
                    </v-img>
                </v-col>
                <v-col class="white" cols="12" md="6">
                    <div class="black--text mx-16 py-7">
                        <h2 class="mb-2">Bonjour !</h2>
                        <p class="text-uppercase">{{ aboutMe }}</p>
                        <v-btn elevation="2">Contactez-moi</v-btn>
                    </div>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
    name: "AboutComp",
    props: {
        aboutMe: String,
    },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500&family=Montserrat:wght@300;500;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500&display=swap');

h2 {
    font-family: 'Cinzel', serif;
    font-weight: 700;
    font-size: 45px;
}  

p {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
    width: 80%;
}

.v-btn {
    font-family: 'Montserrat', sans-serif;
    font-weight: 500;
}
</style>