<template>
    <v-container>
        <div>
            <SoftwareTemplate :project="ecology_coffee" :carousel_height="'100%'" />
        </div>
    </v-container>
</template>

<script>
import SoftwareTemplate from '@/components/SoftwareTemplate.vue';
import { projects } from '@/data/software.js'

export default {
    components: { SoftwareTemplate },
    setup() {
        const ecology_coffee = projects.projects[3];

        return { ecology_coffee }
    }
}
</script>

<style lang="scss" scoped></style>