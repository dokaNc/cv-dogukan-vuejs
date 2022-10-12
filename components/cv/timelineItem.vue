<template>
    <div>
        <v-timeline-item 
            class="mb-7 pointer"
            :color="isActive ? '#9836F4' : '#ffffff'"
            @click.native.stop="handleDot()"
            small
        >
            <v-card 
                rounded="lg" 
                class="pa-2" 
                :class="{ 'card-blur': isActive }"
            >
                <v-card-title>
                {{ experience.companyName }}
                </v-card-title>
                <v-card-subtitle>
                {{ experience.title }}
                </v-card-subtitle>
                <v-card-text class="py-0">
                à <span>{{ experience.city }}, {{ experience.country }}</span>
                </v-card-text>
                <v-card-text>
                {{ experience.work }}
                </v-card-text>
                <v-card-text class="d-sm-flex align-center">
                <v-chip-group class="mr-auto">
                    <v-chip
                        v-for="tags in experience.tags"
                        :key="tags"
                        small
                        outlined 
                    >
                    {{ tags }}
                    </v-chip>
                </v-chip-group>
                <v-chip
                    color="#9836F4" 
                    small 
                    outlined
                >
                    {{ experience.job }}
                </v-chip>
                </v-card-text>
            </v-card>  
        </v-timeline-item>
    </div>
</template>

<script>
export default {
    name: 'timelineItem',

    data() {
      return {
        isActive: false
      }
    },

    props: {
        experience: Object
    },

    methods: {
      handleDot() {
        !this.isActive ? this.isActive = true : this.isActive = false
      }
    }
}
</script>

<style lang="css" scopped>
  .v-card__text span {
    font-weight: 500;
  }

  .card-blur {
    filter: blur(2px) !important
  }

  .pointer {
    cursor: pointer;
  }
</style>