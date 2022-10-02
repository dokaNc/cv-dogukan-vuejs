<template>
    <div>
        <cardPresentation
        :firstName="cv.firstName" 
        :lastName="cv.lastName" 
        :title="cv.title" 
        :aboutMe="cv.aboutMe" 
        :softSkills="cv.softSkills"
        />
    </div>
</template>

<script>
import cardPresentation from '../components/cv/cardPresentation';
import cvJson from '../assets/cv2.json'

export default {
    name: 'CvPage',

    data() {
        return {
            cv: cvJson
        }
    },

    components: {
        cardPresentation
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