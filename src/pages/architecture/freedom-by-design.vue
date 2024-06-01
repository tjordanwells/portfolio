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
                <p>{{ fbd_obj?.title }}</p>
                <p class="text-h5 pt-4">{{ fbd_obj?.role }} – {{ fbd_obj?.class }}</p>
                <p class="text-caption">
                    <a href="https://design.ncsu.edu/academics/arch/research/freedom-design/"
                        target="_blank">https://design.ncsu.edu/academics/arch/research/freedom-design/</a>
                </p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-8" justify="center">
            <v-col cols="12" md="6">
                <p class="text-body-1 hel-neue my-6">{{ fbd_obj?.desc }}</p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="my-16">
            <v-col cols="12" md="6">
                <v-row>
                    <v-col>
                        <v-img :src="fbd_obj?.images?.photo_1?.flickr" width="100%" height="100%" />
                        <div class="text-caption text-uppercase hel-neue-light text-center">{{
                            fbd_obj?.images?.photo_1?.title }}</div>
                    </v-col>
                </v-row>
            </v-col>
            <v-col cols="12" md="6">
                <v-row>
                    <v-col>
                        <v-img :src="fbd_obj?.images?.photo_2?.flickr" width="100%" height="100%" />
                        <div class="text-caption text-uppercase hel-neue-light text-center">{{
                            fbd_obj?.images?.photo_2?.title }}</div>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { projects } from '@/data/architecture';

export default {
    setup() {
        const fbd_obj = projects.projects[5]

        return { fbd_obj }
    }
}
</script>

<style>
a {
    color: black;
}
</style>