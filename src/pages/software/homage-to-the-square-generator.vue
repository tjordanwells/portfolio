<template>
    <v-container>
        <div>
            <div class="my-16 py-16">
                <v-row>
                    <v-col>
                        <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/software">Back to Software</v-btn>
                    </v-col>
                </v-row>
                <v-row>
                    <v-col xs="12" sm="12" md="6">
                        <v-row>
                            <v-col cols="12" class="text-center hel-neue-light text-h4 mt-16">
                                <p>HOMAGE TO THE SQUARE GENERATOR</p>
                                <p class="text-h6 hel-neue-light py-4">PERSONAL – 2022</p>
                            </v-col>
                        </v-row>
                        <v-row class="text-center" justify="center">
                            <v-col cols="12" class="text-uppercase hel-neue text-subtitle-1">Technologies</v-col>
                            <v-col cols="12">
                                <v-chip
                                    v-for="(t, i) in square.tech"
                                    class="ma-2 text-uppercase hel-neue-light text-subtitle-2"
                                    label
                                    variant="outlined"
                                    :key="i"
                                >
                                    {{ t }}
                                </v-chip>
                            </v-col>
                        </v-row>
                        <v-row>
                            <v-col cols="12" class="text-subtitle-1 hel-neue">
                                {{ square?.desc }}
                            </v-col>
                        </v-row>
                    </v-col>
                    <v-col xs="12" sm="12" md="6">
                        <v-img
                            :src="square?.images?.site"
                        />
                        <div class="d-flex justify-center hel-neue-light">
                            <a class="black" :href="square?.link_href" target="_blank">{{ square.link_text }}</a>
                        </div>
                    </v-col>
                </v-row>
            </div>
        </div>
    </v-container>
</template>

<script>
import SoftwareTemplate from '@/components/SoftwareTemplate.vue';
import { projects } from '@/data/software.js'

export default {
    components: { SoftwareTemplate },
    setup() {
        const square = projects.projects[4];

        return { square }
    }
}
</script>

<style>
  .black {
        color: black;
    }
</style>
