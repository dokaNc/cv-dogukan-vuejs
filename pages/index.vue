<template>
    <div>
        <presentation
        :firstName="cv.firstName" 
        :lastName="cv.lastName" 
        :title="cv.title" 
        :aboutMe="cv.aboutMe" 
        :softSkills="cv.softSkills"
        />
    </div>
</template>

<script>
import presentation from '../components/cv/presentation';
import cvJson from '../assets/cv.json'

export default {
    name: 'index',

    data() {
        return {
            cv: cvJson
        }
    },

    components: {
        presentation
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;500&family=Montserrat:wght@300;500;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;700&display=swap');

p {
    font-family: 'Montserrat', sans-serif;
}

/* font-family: 'Cinzel', serif; */
/* font-family: 'Montserrat', sans-serif; */


</style>