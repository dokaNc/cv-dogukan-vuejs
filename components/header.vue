<template>
    <div>
        <v-container>
            <v-row>
                <v-col cols="12" lg="8">
                    <h1 class="my-10">{{ title }}</h1>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
    name: "headerComp",
    props: {
        title: String
    }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500&family=Montserrat:wght@300;500;700&display=swap');

h1 {
    font-family: 'Cinzel', serif;
    font-weight: 500;
    font-size: 50px;
    line-height: 1;
}
</style>>