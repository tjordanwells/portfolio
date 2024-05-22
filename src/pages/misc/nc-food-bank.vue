<template>
    <v-container class="py-16">
        <v-row>
            <v-col>
                <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/misc">Back to Misc.</v-btn>
            </v-col>
        </v-row>
        <v-row class="py-16 text-h3 hel-neue-light text-center">
            <v-col cols="12">
                <p>{{ ncfb?.title }}</p>
                <p class="text-h5 py-4">{{ ncfb?.role }}</p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-8" justify="center">
            <v-col cols="12" md="6">
                <p class="text-body-1 hel-neue">
                    {{ ncfb?.desc }}
                </p>
            </v-col>
        </v-row>
        <v-row>
            <v-col cols="12">
                <v-row>
                    <v-col class="d-flex align-center justify-center" cols="1">
                        <v-icon v-show="slide !== 0" class="icon-btn" icon="mdi-arrow-left" size="large"
                            @click="slide = Math.max(slide - 1, 0)" />
                    </v-col>
                    <v-col>
                        <v-carousel height="1000" hide-delimiters :show-arrows="false" v-model="slide">
                            <template v-for="(p, i) in ncfb?.images?.pages" :key="i">
                                <v-carousel-item :value="i" cover>
                                    <v-sheet class="d-flex fill-height justify-center align-center">
                                        <v-img :src="p" width="100%" height="100%" />
                                    </v-sheet>
                                </v-carousel-item>
                            </template>
                        </v-carousel>
                    </v-col>
                    <v-col class="d-flex align-center justify-center" cols="1">
                        <v-icon v-show="slide < length" class="icon-btn" icon="mdi-arrow-right" size="large"
                            @click="slide = Math.min(slide + 1, length)" />
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { reactive, toRefs } from 'vue'

import { projects } from '@/data/misc';

export default {
    setup() {
        const ncfb = projects.projects[1]
        const length = ncfb?.images?.pages.length - 1

        const state = reactive({
            slide: 0
        })

        return { ncfb, ...toRefs(state), length }
    }
}
</script>
