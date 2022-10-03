<template>
  <div>
    <v-container>
        <v-row>
            <v-col cols="12">
                <v-autocomplete
                v-model="input"
                label="Vérifier la compatibilité entre votre projet et mes skills ..."
                :items="langageAndTool"
                item-text="name"
                chips
                clearable
                deletable-chips
                filled
                multiple
                small-chips
                solo-inverted
                background-color="#1E1E1E"
                @input="matchSkill"
                >
                </v-autocomplete>
            </v-col>
            <v-col cols="12" md="6">
                <v-card rounded="lg" class="pa-5">
                    <v-card-subtitle class="pb-0">
                        <v-alert
                        class="mb-0"
                        dense
                        outlined
                        text
                        type="success"
                        >
                        Compatibilité à <strong>20%</strong>
                        </v-alert>
                    </v-card-subtitle>
                    <v-card-title>
                        Langages de Programmation
                    </v-card-title>
                    <v-divider class="mx-4" />
                    <skillsText
                    v-for="(item, i) in items.langage" 
                    :key="i"
                    :skills="item"
                    />
                </v-card>
            </v-col>
            <v-col cols="12" md="6">
                <v-card rounded="lg" class="pa-5">
                    <v-card-title>
                        Logiciels et Outils 
                    </v-card-title>
                    <v-divider class="mx-4" />
                    <skillsText
                    v-for="(item, i) in items.tool" 
                    :key="i"
                    :skills="item"
                    />
                </v-card>
            </v-col>
        </v-row>
    </v-container>
  </div>
</template>

<script>
import skillsText from './skillsText'

export default {
    name: 'langageAndTool',

    data() {
        return {
            input: '',
            items: {
                'langage': [
                    {name: 'Php', src: require('@/assets/icon/langage/php.svg')},
                    {name: 'Symfony', src: require('@/assets/icon/langage/symfony.svg')},
                    {name: 'JavaScript', src: require('@/assets/icon/langage/javascript.svg')},
                    {name: 'Vue Js', src: require('@/assets/icon/langage/vuejs.svg')},
                    {name: 'Nuxt Js', src: require('@/assets/icon/langage/nuxtjs.svg')},
                    {name: 'React Js', src: require('@/assets/icon/langage/reactjs.svg')},
                    {name: 'WordPress', src: require('@/assets/icon/langage/wordpress.svg')},
                    {name: 'MySQL', src: require('@/assets/icon/langage/mysql.svg')},
                    {name: 'PostgreSQL', src: require('@/assets/icon/langage/postgresql.svg')}
                ],
                'tool': [
                    {name: 'Git', src: require('@/assets/icon/tool/git.svg')},
                    {name: 'GitHub', src: require('@/assets/icon/tool/github.svg')},
                    {name: 'Docker', src: require('@/assets/icon/tool/docker.svg')},
                    {name: 'Linux', src: require('@/assets/icon/tool/linux.svg')},
                    {name: 'VSCode', src: require('@/assets/icon/tool/vscode.svg')},
                    {name: 'Photoshop', src: require('@/assets/icon/tool/photoshop.svg')},
                    {name: 'Illustrator', src: require('@/assets/icon/tool/illustrator.svg')},
                    {name: 'After Effects', src: require('@/assets/icon/tool/ae.svg')},
                ]
            }
        }
    },

    methods: {
        consoleLog() {
            // console.log('console log bro', this.input)
            console.log('console log bro' , this.langageAndTool[0])
        },

        matchSkill() {
            for (let i=0; i < this.langageAndTool.length; i++) {
                console.log(i)
            }
            // const filter = this.langageAndTool.filter(data => console.log(data))
            // console.log(this.langageAndTool)
            // console.log(this.input)
        }
    },

    computed: {
        langageAndTool() {
            return this.items.langage.concat(this.items.tool)
        },
    },

    components: {
        skillsText
    }
}
</script>

<style scoped>
 .v-card__title {
    word-break: break-word;
 }

 .v-card__text {
    font-weight: 500;
 }
</style>