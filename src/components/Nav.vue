<template>
    <div class="hel-neue-light px-8 py-2">
        <v-sheet class="d-flex">
            <div class="text-h5 hel-neue-thin ma-2 pa-2 me-auto name-text"
              @click="() => toMain()"
            >
                JORDAN WELLS
            </div>
            <div class="d-flex align-center">
                <v-btn variant="plain" :ripple="false" size="large" to="/resume">
                    RESUME
                </v-btn>
            </div>
            <div class="d-flex align-center">
                <v-btn variant="plain" :ripple="false" size="large" to="/software">
                    SOFTWARE
                </v-btn>
            </div>
            <div class="d-flex align-center">
                <v-btn variant="plain" :ripple="false" size="large" to="/architecture">
                    ARCHITECTURE
                </v-btn>
            </div>
            <div class="d-flex align-center">
                <v-btn variant="plain" :ripple="false" size="large" to="/misc">
                    MISC.
                </v-btn>
            </div>
        </v-sheet>
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
import { useRouter } from 'vue-router'

export default {
    setup () {
        const state = reactive({
        })

        const router = useRouter()
        const toMain = () => router.push('/');
    
        return {
            ...toRefs(state),
            toMain
        }
    }
}
</script>

<style lang="scss" scoped>
    .name-text {
        cursor: pointer;
    }
</style>