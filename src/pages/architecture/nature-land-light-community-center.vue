<template>
    <v-container class="py-16">
        <v-row v-motion-fade-visible-once>
            <v-col>
                <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/architecture">Back to
                    Architecture</v-btn>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="py-16 text-h3 hel-neue-light text-center">
            <v-col cols="12">
                <p>{{ nature_land_light?.title }}</p>
                <p class="text-h5 py-4">{{ nature_land_light?.role }} – {{ nature_land_light?.class }}</p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-8" justify="center">
            <v-col cols="12" md="6">
                <p class="text-body-1 hel-neue">
                    {{ nature_land_light?.desc }}
                </p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-16">
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="700" :src="nature_land_light?.images?.parti_sketch?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.parti_sketch?.title }}</div>
            </v-col>
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="700" :src="nature_land_light?.images?.site?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.site?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="800" :src="nature_land_light?.images?.ground_plan?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.ground_plan?.title }}</div>
            </v-col>
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="800" :src="nature_land_light?.images?.axonometric?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.axonometric?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once align="center">
            <v-col cols="8">
                <v-img class="mx-auto" aspect-ratio="1" height="100%"
                    :src="nature_land_light?.images?.section_persp?.src" />
            </v-col>
            <v-col cols="4">
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.section_persp?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="nature_land_light?.images?.int_1?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.int_1?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="nature_land_light?.images?.int_2?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.int_2?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="nature_land_light?.images?.main?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    nature_land_light?.images?.main?.title }}</div>

            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { projects } from '@/data/architecture';

export default {
    setup() {
        const nature_land_light = projects.projects[1]

        return { nature_land_light }
    }
}
</script>
