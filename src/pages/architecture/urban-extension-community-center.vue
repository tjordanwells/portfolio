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
                <p>{{ urban_ext?.title }}</p>
                <p class="text-h5 py-4">{{ urban_ext?.role }} – {{ urban_ext?.class }}</p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-8" justify="center">
            <v-col cols="12" md="6">
                <p class="text-body-1 hel-neue">
                    {{ urban_ext?.desc }}
                </p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-16">
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="700" :src="urban_ext?.images?.parti?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.parti?.title }}</div>
            </v-col>
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="700" :src="urban_ext?.images?.context?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.context?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="urban_ext?.images?.site?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center mt-16">{{
                    urban_ext?.images?.site?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="800" :src="urban_ext?.images?.level_2?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.level_2?.title }}</div>
            </v-col>
            <v-col cols="12" md="6">
                <v-img class="mx-auto" aspect-ratio="1" :width="800" :src="urban_ext?.images?.level_3?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.level_3?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="urban_ext?.images?.main?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.main?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="urban_ext?.images?.exterior?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.exterior?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="urban_ext?.images?.model_1?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.model_1?.title }}</div>

            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="urban_ext?.images?.model_2?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.model_2?.title }}</div>

            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12">
                <v-img class="mx-auto" aspect-ratio="1" :width="1000" :src="urban_ext?.images?.model_3?.src" />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{
                    urban_ext?.images?.model_3?.title }}</div>

            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { projects } from '@/data/architecture';

export default {
    setup() {
        const urban_ext = projects.projects[0]

        return { urban_ext }
    }
}
</script>
