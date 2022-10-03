<template>
  <div>
    <v-card-text 
    class="d-flex align-center pb-0"
    :class="{ 'active-text': skills.isActive}">
        <v-avatar  size="24" class="mr-2">
            <img
            :alt="skills.name" 
            :src="skills.src"
            :class="{ 'active-img': skills.isActive }"
            >
        </v-avatar>
        {{ skills.name }}
    </v-card-text>
  </div>
</template>

<script>
export default {
    name: "skillsText",

    props: {
        skills: Object
    }
}
</script>

<style lang="css" scoped>
    .active-text {
        font-weight: bold;
    }
    .active-img {
        filter: invert(73%) sepia(84%) saturate(1212%) hue-rotate(90deg) brightness(89%) contrast(104%) !important;
    }
</style>