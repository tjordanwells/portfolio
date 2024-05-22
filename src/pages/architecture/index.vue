<template>
    <v-container>
        <div>
            <v-img
                class="mx-auto"
                :src="sketch_src"
                aspect-ratio="1"
                :width="400"
            />
        </div>
        <Projects :projects="arch_projects" scrim_color="gray" :cover=true />
    </v-container>
</template>

<script>
import { projects } from '@/data/architecture.js'
import Projects from '@/components/Projects.vue'
export default {
    components: { Projects },
    setup () {
        const sketch_src = projects.sketch_src
        const arch_projects = projects.projects

        return {
            sketch_src,
            arch_projects
        }
    }
}
</script>
