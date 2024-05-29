<template>
    <v-container class="py-16">
        <v-row>
            <v-col>
                <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/architecture">Back to
                    Architecture</v-btn>
            </v-col>
        </v-row>
        <v-row class="py-16 text-h3 hel-neue-light text-center">
            <v-col cols="12">
                MAP DIAGRAMS
            </v-col>
        </v-row>
        <v-row v-for="(m, i) in map_object?.images" class="py-8" :key="i">
            <v-col>
                <div v-motion-fade-visible-once>
                    <v-img class="mx-auto" cover :src="m?.flickr" aspect-ratio="1" :width="700" />
                </div>
            </v-col>
            <v-col cols="12" md="4">
                <v-spacer></v-spacer>
                <p class="text-h4 hel-neue-light">{{ m.title }}</p>
                <div class="text-body-1 hel-neue my-8">{{ m.desc }}</div>
            </v-col>
        </v-row>
        <v-divider class="my-16" />
        <v-row class="mt-16">
            <v-col>
                <p class="text-h4 hel-neue-light">Historic Timelapse of Dix Park</p>
                <div class="text-body-1 hel-neue my-8">Synthetic animation of the historic development of Raleigh, North
                    Carolina, focusing on The Grove at Dorothea Dix Park.</div>
                <p class="text-caption hel-neue">Research and diagrams in collaboration with Tanighya Alvin and Daniel Boney
                </p>
                <p class="text-caption hel-neue">Music Credit: Forevertime Journeys by naran ratan</p>
            </v-col>
            <v-col>
                <div>
                    <vueVimeoPlayer :player-height="height" :player-width="width"
                        video-url="https://player.vimeo.com/video/948504001" :key="key" />
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { computed, watch, ref } from 'vue'
import { useDisplay } from 'vuetify'
import { vueVimeoPlayer } from 'vue-vimeo-player'

import { projects } from '@/data/architecture'

export default {
    components: { vueVimeoPlayer },
    setup() {
        const map_object = projects.projects[4]

        const { name } = useDisplay();

        const key = ref(0)

        const forceRerender = () => {
            key.value += 1;
        };

        const height = computed(() => {
            switch (name.value) {
                case 'xs': return 320
                case 'sm': return 480
                case 'md': return 480
                case 'lg': return 640
                case 'xl': return 640
                case 'xxl': return 640
            }
            return undefined
        })
        const width = computed(() => {
            switch (name.value) {
                case 'xs': return 350
                case 'sm': return 600
                case 'md': return 800
                case 'lg': return 1280
                case 'xl': return 1280
                case 'xxl': return 1280
            }
            return undefined
        })

        watch(height, () => {
            forceRerender();
        })

        return {
            map_object,
            height,
            width,
            key,
            name
        }
    }
}
</script>
