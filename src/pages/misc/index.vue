<template>
    <v-container>
        <div>
            <v-img class="mx-auto" :src="header_src" aspect-ratio="1" :width="400" />
        </div>
        <Projects :projects="misc_projects" scrim_color="#343546" />
    </v-container>
</template>

<script>
import { projects } from '@/data/misc.js'
import Projects from '@/components/Projects.vue'

export default {
    components: { Projects },
    setup() {
        const header_src = projects.header_src
        const misc_projects = projects.projects

        return {
            header_src,
            misc_projects
        }
    }
}
</script>
