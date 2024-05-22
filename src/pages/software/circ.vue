<template>
    <v-container>
        <div>
            <SoftwareTemplate :project="circ" :carousel_height="'1200px'" />
        </div>
    </v-container>
</template>

<script>
import SoftwareTemplate from '@/components/SoftwareTemplate.vue';
import { projects } from '@/data/software.js'

export default {
    components: { SoftwareTemplate },
    setup () {
        const circ = projects.projects[0];

        return { circ }
    }
}
</script>

<style lang="scss" scoped>

</style>