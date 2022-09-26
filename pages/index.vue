<template>
  <div>
    <headerComp :title="cv.title"/>
    <aboutComp :aboutMe="cv.aboutMe"/>
  </div>
</template>

<script>
import aboutComp from '../components/about';
import headerComp from '../components/header'
import cvData from '../assets/cv.json';

export default {
  name: 'IndexPage',

  data() {
    return {
      cv: cvData
    }
  },

  components: {
    aboutComp,
    headerComp
  }
}
</script>