<template>
    <v-container class="py-16">
         <v-row>
            <v-col>
                <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/architecture">Back to Architecture</v-btn>
            </v-col>
        </v-row>
        <v-row class="py-16 text-h3 hel-neue-light text-center">
                <v-col cols="12">
                    BLOCKFEST
                </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-8" justify="center">
            <v-col cols="12" md="6">
                <p v-for="(d, i) in desc_array" class="text-body-1 hel-neue my-6" :key="i">{{ d }}</p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="my-16">
            <v-col cols="12" md="6">
                <v-row>
                    <v-col class="d-flex align-end justify-center" cols="1">
                        <v-icon v-show="slide_boards !== 0" class="icon-btn" icon="mdi-arrow-left" size="large" @click="slide_boards = Math.max(slide_boards - 1, 0)" />
                    </v-col>
                    <v-col>
                        <v-carousel
                            height="400px"
                            hide-delimiters
                            :show-arrows="false"
                            v-model="slide_boards"
                        >
                            <v-carousel-item :value="0" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.board_1"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                            <v-carousel-item :value="1" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.board_2"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                            <v-carousel-item :value="2" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.board_3"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                        </v-carousel>
                    </v-col>
                    <v-col class="d-flex align-end justify-center" cols="1">
                        <v-icon v-show="slide_boards < 2" class="icon-btn" icon="mdi-arrow-right" size="large" @click="slide_boards = Math.min(slide_boards + 1, 2)" />
                    </v-col>
                </v-row>
            </v-col>
            <v-col cols="12" md="6">
                <v-row>
                    <!-- <v-col class="d-flex align-end justify-center" cols="1">
                        <v-icon v-show="slide_models !== 0" class="icon-btn" icon="mdi-arrow-left" size="large" @click="slide_models = Math.max(slide_models - 1, 0)" />
                    </v-col> -->
                    <v-col>
                        <v-carousel
                            height="400px"
                            hide-delimiters
                            :show-arrows="false"
                            v-model="slide_models"
                            cycle
                            :interval="4000"
                        >
                            <v-carousel-item :value="0" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.main"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                            <v-carousel-item :value="1" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.model_2"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                            <v-carousel-item :value="2" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.model_3"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                            <v-carousel-item :value="3" cover>
                                <v-sheet class="d-flex fill-height justify-center align-center" height="100%">
                                    <v-img
                                        :src="blockfest_obj?.images?.model_4"
                                        width="100%"
                                        height="100%"
                                    />
                                </v-sheet>
                            </v-carousel-item>
                        </v-carousel>
                    </v-col>
                    <!-- <v-col class="d-flex align-end justify-center" cols="1">
                        <v-icon v-show="slide_models < 3" class="icon-btn" icon="mdi-arrow-right" size="large" @click="slide_models = Math.min(slide_models + 1, 3)" />
                    </v-col> -->
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { reactive, toRefs } from 'vue'

import { projects } from '@/data/architecture';

export default {
    setup () {
        const blockfest_obj = projects.projects[3]

        const desc_array = blockfest_obj.desc.split('>')

        const state = reactive({
            slide_boards: 0,
            slide_models: 0
        })

        return { blockfest_obj, desc_array, ...toRefs(state) }
    }
}
</script>
