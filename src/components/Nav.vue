<template>
    <v-row class="pa-6" align="center">
        <v-col class="text-h5 hel-neue-thin ma-2 pa-2 me-auto name-text" @click="() => toMain()">
            JORDAN WELLS
        </v-col>
        <v-col v-if="smAndDown">
            <v-dialog v-model="dialog" transition="dialog-bottom-transition" fullscreen>
                <template v-slot:activator="{ props: activatorProps }">
                    <div class="text-right">
                        <v-icon v-bind="activatorProps" icon="mdi-menu" />
                    </div>
                </template>

                <v-card>
                    <v-toolbar color="white">
                        <v-spacer />
                        <v-btn class="name-text" icon="mdi-close" @click="dialog = false"></v-btn>
                    </v-toolbar>
                    <v-list class="hel-neue-light">
                        <v-list-item v-for="(n, i) in nav_items" :title="n.title" :key="i" link :to="n.src"
                            @click="dialog = false" />
                    </v-list>
                </v-card>
            </v-dialog>
        </v-col>
        <v-col v-else class="text-right">
            <v-sheet class="d-inline-flex hel-neue-light">
                <div v-for="(n, i) in nav_items" :key="i" class="d-flex align-center text-uppercase">
                    <v-btn variant="plain" :ripple="false" size="large" :to="n.src">
                        {{ n.title }}
                    </v-btn>
                </div>
            </v-sheet>
        </v-col>
    </v-row>
</template>

<script>
import { reactive, toRefs } from 'vue'
import { useDisplay } from 'vuetify'
import { useRouter } from 'vue-router'

export default {
    setup() {
        const { smAndDown } = useDisplay()
        const state = reactive({
            dialog: false,
            nav_items: [
                {
                    title: 'Resume',
                    src: '/resume'
                },
                {
                    title: 'Software',
                    src: '/software'
                },
                {
                    title: 'Architecture',
                    src: '/architecture'
                },
                {
                    title: 'Misc.',
                    src: '/misc'
                }
            ]
        })

        const router = useRouter()
        const toMain = () => router.push('/');

        return {
            ...toRefs(state),
            toMain,
            smAndDown
        }
    }
}
</script>

<style lang="scss" scoped>
.name-text {
    cursor: pointer;
}
</style>