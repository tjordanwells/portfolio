<template>
    <v-container>
        <div>
            <SoftwareTemplate :project="nice_price" :carousel_height="'700px'" />
        </div>
    </v-container>
</template>

<script>
import SoftwareTemplate from '@/components/SoftwareTemplate.vue';
import { projects } from '@/data/software.js'

export default {
    components: { SoftwareTemplate },
    setup() {
        const nice_price = projects.projects[1];

        return { nice_price }
    }
}
</script>

<style lang="scss" scoped></style>