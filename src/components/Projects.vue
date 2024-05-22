<template>
    <div class="mb-16">
        <v-row class="h-50">
            <v-col cols="12" class="text-h4 hel-neue-light text-uppercase py-12">
                Projects
            </v-col>
            <v-col
              xl="4"
              lg="4"
              md="6"
              sm="12"
              v-for="(p, i) in projects"
              :key="`project-${i}`"
            >
                <v-hover open-delay="100">
                    <template v-slot:default="{ props: hoverProps, isHovering }">
                        <div :key="i">
                            <router-link :to="p.route">
                                <v-img
                                    v-bind="hoverProps"
                                    class="mx-auto pointer"
                                    :src="p.images?.main?.src"
                                    width="100%"
                                    :cover="cover"
                                    :aspect-ratio="1"
                                >
                                    <v-slide-x-transition mode="in-out" :hide-on-leave="true">
                                        <v-overlay
                                            :model-value="isHovering ? isHovering : false"
                                            class="align-end justify-center"
                                            contained
                                            :scrim="scrim_color"
                                        >
                                            <p class="text-body-1 text-white text-uppercase hel-neue-medium pb-6">{{ p.title }}</p>
                                        </v-overlay>
                                    </v-slide-x-transition>
                                </v-img>
                            </router-link>
                        </div>
                    </template>
                </v-hover>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    props: ['projects', 'cover', 'scrim_color'],
    setup (props) {
        const projects = props.projects
        const scrim_color = props.scrim_color
        const cover = props.cover

        return { projects, scrim_color, cover }
    }
}
</script>

<style>
    .no-underline {
        color: black;
        text-decoration: none; /* no underline */
    }

    .pointer {
        cursor: pointer;
    };
</style>
