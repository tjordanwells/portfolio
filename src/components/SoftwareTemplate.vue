<template>
    <div class="my-16 py-16">
        <v-row>
            <v-col>
                <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/software">Back to Software</v-btn>
            </v-col>
        </v-row>
        <v-row>
            <v-col xs="12" sm="12" md="6">
                <v-row>
                    <v-col cols="12">
                        <v-img class="mx-auto" :src="project.images?.main?.src" width="30%" cover :aspect-ratio="1" />
                    </v-col>
                </v-row>
                <v-row class="text-center" justify="center">
                    <v-col cols="12" class="text-uppercase hel-neue text-subtitle-1">Technologies</v-col>
                    <v-col cols="12">
                        <v-chip v-for="(t, i) in project.tech" class="ma-2 text-uppercase hel-neue-light text-subtitle-2"
                            label variant="outlined" :key="i">
                            {{ t }}
                        </v-chip>
                    </v-col>
                </v-row>
                <v-row>
                    <v-col cols="12" class="hel-neue text-subtitle-1 pa-16">
                        {{ project.desc }}
                    </v-col>
                </v-row>
            </v-col>
            <v-col class="d-flex align-start justify-center" cols="1">
                <v-icon v-show="slide !== 0" class="icon-btn" icon="mdi-arrow-left" size="x-large"
                    @click="slide = Math.max(slide - 1, 0)" />
            </v-col>
            <v-col>
                <v-carousel :height="carousel_height" width="100%" hide-delimiters :show-arrows="false" v-model="slide">
                    <template v-for="(image, i) in project.images">
                        <v-carousel-item v-if="i !== 'main'" :key="i" :value="i" height="100%" width="100%">
                            <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                <v-img :src="image?.src" width="100%" height="100%" />
                            </v-sheet>
                        </v-carousel-item>
                    </template>
                </v-carousel>
                <div v-if="project?.link_href" class="d-flex justify-center hel-neue-light">
                    <a class="black" :href="project?.link_href" target="_blank">{{ project.link_text }}</a>
                </div>
            </v-col>
            <v-col class="d-flex align-end justify-center" cols="1">
                <v-icon v-show="slide < length" class="icon-btn" icon="mdi-arrow-right" size="x-large"
                    @click="slide = Math.min(slide + 1, length)" />
            </v-col>
        </v-row>
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'

export default {
    props: ['project', 'carousel_height'],
    setup(props) {
        const project = props.project
        const carousel_height = props.carousel_height
        const state = reactive({
            slide: 0
        })

        const keys_array = Object.keys(project.images)
        const length = keys_array.length - 2

        return { ...toRefs(state), project, carousel_height, length }
    }
}
</script>

<style lang="scss" scoped>
.black {
    color: black;
}

.icon-btn {
    cursor: pointer;
}
</style>