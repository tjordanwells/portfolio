<template>
    <v-container class="py-16">
        <v-row>
            <v-col>
                <v-btn class="hel-neue-light" variant="plain" :ripple="false" to="/architecture">Back to Architecture</v-btn>
            </v-col>
        </v-row>
        <v-row class="py-16 text-h3 hel-neue-light text-center">
            <v-col cols="12">
                <p>HIGGINS HALL INSERTION, PRATT INSTITUTE</p>
                <p class="text-h5 py-4">STEVEN HOLL ARCHITECTS – BROOKLYN, NY – 2005</p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="mb-8" justify="center">
            <v-col cols="12" md="6">
                <p class="text-body-1 hel-neue">
                    {{ higgins_project?.desc }}
                </p>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12" md="6">
                <v-img
                    class="mx-auto"
                    aspect-ratio="1"
                    :width="800"
                    :src="higgins_project?.images?.plan"
                />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{ higgins_project?.images?.plan?.title }}</div>
            </v-col>
            <v-col cols="12" md="6">
                <v-img
                class="mx-auto"
                aspect-ratio="1"
                :width="800"
                :src="higgins_project?.images?.section?.src"
                />
                <div class="text-caption text-uppercase hel-neue-light text-center">{{ higgins_project?.images?.section?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once class="my-16 pt-8">
            <v-col cols="12" sm="6" md="3">
                <v-img
                    class="mx-auto"
                    aspect-ratio="1"
                    position="center"
                    :width="250"
                    :src="higgins_project?.images?.diagram_4"
                />
                <div class="text-caption text-uppercase hel-neue-light text-center mt-8">{{ higgins_project?.images?.diagram_4?.title }}</div>
            </v-col>
            <v-col cols="12" sm="6" md="3">
                <v-img
                    class="mx-auto"
                    aspect-ratio="1"
                    position="center"
                    :width="250"
                    :src="higgins_project?.images?.diagram_1"
                />
                <div class="text-caption text-uppercase hel-neue-light text-center mt-8">{{ higgins_project?.images?.diagram_1?.title }}</div>
            </v-col>
            <v-col cols="12" sm="6" md="3">
                <v-img
                    class="mx-auto"
                    aspect-ratio="1"
                    position="center"
                    :width="250"
                    :src="higgins_project?.images?.diagram_2"
                />
                <div class="text-caption text-uppercase hel-neue-light text-center mt-8">{{ higgins_project?.images?.diagram_2?.title }}</div>
            </v-col>
            <v-col cols="12" sm="6" md="3">
                <v-img
                    class="mx-auto"
                    aspect-ratio="1"
                    position="center"
                    :width="250"
                    :src="higgins_project?.images?.diagram_3"
                />
                <div class="text-caption text-uppercase hel-neue-light text-center mt-8">{{ higgins_project?.images?.diagram_3?.title }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12" class="mt-16 py-16">
                <v-img
                    class="mx-auto"
                    position="center bottom"
                    :width="850"
                    :src="higgins_project?.images?.ps_collage"
                />
                <div class="text-body-2 text-uppercase hel-neue-light text-center">{{ higgins_project?.images?.ps_collage?.title }}</div>
                <div class="text-subtitle-2 hel-neue-light text-center mt-8">{{ higgins_project?.images?.ps_collage?.desc }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12" class="mt-16 py-16">
                <v-img
                    class="mx-auto"
                    position="center bottom"
                    :width="850"
                    :src="higgins_project?.images?.exterior"
                />
                <div class="text-body-2 text-uppercase hel-neue-light text-center mt-8">{{ higgins_project?.images?.exterior?.title }}</div>
                <div class="text-subtitle-2 hel-neue-light text-center mt-8">{{ higgins_project?.images?.exterior?.desc }}</div>
            </v-col>
        </v-row>
        <v-row v-motion-fade-visible-once>
            <v-col cols="12" class="mt-16 py-16">
                <v-img
                    class="mx-auto"
                    position="center bottom"
                    :width="850"
                    :src="higgins_project?.images?.main"
                />
                <div class="text-body-2 text-uppercase hel-neue-light text-center mt-8">{{ higgins_project?.images?.main?.title }}</div>
                <div class="text-subtitle-2 hel-neue-light text-center mt-8">{{ higgins_project?.images?.main?.desc }}</div>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { projects } from '@/data/architecture';

export default {
    setup () {
        const higgins_project = projects.projects[2]

        return { higgins_project }
    }
}
</script>
