<template>
    <v-container class="my-12">
        <v-row justify="center">
            <v-col cols="9">
                <div class="text-left">
                    <span class="text-h4 hel-neue-light mb-12">WORK</span>
                </div>
                <v-timeline class="pt-12">
                    <v-timeline-item
                        v-for="n in resume.work"
                        :key="n"
                        class="px-2"
                        hide-dot
                    >
                    <template v-slot:opposite>
                        <div
                        class="hel-neue text-caption"
                        v-text="n.date"
                        ></div>
                    </template>
                      <v-row>
                        <v-col class="pb-0" cols="12">
                            <span class="hel-neue-bold text-overline">{{ n.title }}</span>
                        </v-col>
                        <v-col class="pt-0 pb-0" cols="12">
                            <span class="hel-neue text-caption">{{ n.company }}</span>
                        </v-col>
                        <v-col class="pb-2" cols="12">
                            <span class="hel-neue text-body-2">{{ n.desc }}</span>
                        </v-col>
                        <v-col v-if="n?.tech && n?.tech.length > 0" class="px-0" cols="12">
                            <v-chip
                                v-for="(t, i) in n.tech"
                                class="ma-2 text-caption hel-neue-light"
                                label
                                variant="outlined"
                                size="small"
                                :key="i"
                            >
                                {{ t }}
                            </v-chip>
                        </v-col>
                      </v-row>
                    </v-timeline-item>
                  </v-timeline>
            </v-col>
        </v-row>
        <v-row class="py-16" justify="center">
            <v-col cols="9">
                <div class="text-left pt-16">
                    <span class="text-h4 hel-neue-light pb-12">EDUCATION</span>
                </div>
                <v-timeline
                    align-top
                    density="compact"
                    class="pt-12"
                >
                    <v-timeline-item
                        v-for="n in resume.education"
                        :key="n"
                        class="px-2"
                        hide-dot
                    >
                      <v-row>
                        <v-col class="pb-0" cols="12">
                            <span class="hel-neue-bold text-overline">{{ n.degree }}</span>
                        </v-col>
                        <v-col class="pt-0 pb-0" cols="12">
                            <span class="hel-neue text-caption">{{ n.date }}</span>
                        </v-col>
                        <v-col class="pb-0" cols="12">
                            <span class="hel-neue text-body-2">{{ n.desc }}</span>
                        </v-col>
                      </v-row>
                    </v-timeline-item>
                  </v-timeline>
            </v-col>
        </v-row>
        <v-row class="py-16" justify="center">
            <v-col cols="9">
                <div class="text-left pt-16">
                    <span class="text-h4 hel-neue-light pb-12">VOLUNTEER</span>
                </div>
                <v-timeline
                    align-top
                    density="compact"
                    class="pt-12"
                >
                    <v-timeline-item
                        v-for="n in resume.volunteer"
                        :key="n"
                        class="px-2"
                        hide-dot
                    >
                      <v-row>
                        <v-col class="pb-0" cols="12">
                            <span class="hel-neue-bold text-overline">{{ n.org }}</span>
                        </v-col>
                        <v-col class="pt-0 pb-0" cols="12">
                            <span class="hel-neue text-caption">{{ n.date }}</span>
                        </v-col>
                        <v-col class="pb-0" cols="12">
                            <span class="hel-neue text-body-2">{{ n.desc }}</span>
                        </v-col>
                      </v-row>
                    </v-timeline-item>
                  </v-timeline>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import { resume } from '@/data/resume.js'

export default {
    setup () {
        return {
            resume
        }
    }
}
</script>
