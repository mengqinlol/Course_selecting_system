<script setup>
import { defineEmits } from 'vue';
const emits = defineEmits(['selectPages'])
const selectPages = (pageidx) => {
    emits("selectPages", pageidx)
}
const username = 'testuser'
const choose = () => {
    selectPages(0)
}
const del = () => {
    selectPages(1)
}
const query = () => {
    selectPages(2)
}
</script>

<script>

export default {
    data() {
        return {
            username: 'testuser'
        };
    },
    methods: {
        choose() {
            selectPages(0)
        },
        del() {
            selectPages(1)
        },
        query() {
            selectPages(2)
        }
    }
};
</script>

<template>
    <v-navigation-drawer expand-on-hover rail>
        <v-list>
            <v-list-item prepend-icon="mdi-account">
                <v-list-item-content>
                    <v-list-item-title>{{ username }}</v-list-item-title>
                    <v-list-item-subtitle>teacher or student</v-list-item-subtitle>
                </v-list-item-content>
            </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
            <v-list-item @click="choose" prepend-icon="mdi-folder" title="选择课程" value="myfiles"></v-list-item>
            <v-list-item @click="del" prepend-icon="mdi-account-multiple" title="删除课程" value="shared"></v-list-item>
            <v-list-item @click="query" prepend-icon="mdi-star" title="查询已选课程" value="starred"></v-list-item>
        </v-list>
    </v-navigation-drawer>

    <v-main style="height: 250px"></v-main>
</template>