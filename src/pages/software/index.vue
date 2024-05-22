<template>
    <v-container>
        <div>
            <v-img class="mx-auto" :src="art_src" aspect-ratio="1" :width="400" />
        </div>
        <Projects :projects="software_projects" scrim_color="#ca96c4" />
    </v-container>
</template>

<script>
import { projects } from '@/data/software.js'
import Projects from '@/components/Projects.vue'
export default {
    components: { Projects },
    setup() {
        const art_src = projects.art_src
        const software_projects = projects.projects

        return {
            art_src,
            software_projects
        }
    }
}
</script>
