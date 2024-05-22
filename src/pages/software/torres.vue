<template>
    <v-container>
        <div>
            <SoftwareTemplate :project="torres" :carousel_height="'800px'" />
        </div>
    </v-container>
</template>

<script>
import SoftwareTemplate from '@/components/SoftwareTemplate.vue';
import { projects } from '@/data/software.js'

export default {
    components: { SoftwareTemplate },
    setup() {
        const torres = projects.projects[2];

        return { torres }
    }
}
</script>

<style lang="scss" scoped>

</style>