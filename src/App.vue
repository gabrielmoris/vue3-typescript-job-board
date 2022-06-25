<template>
    <div class="app"> Hello world </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "./types/Job";

export default defineComponent({
    name: "App",
    components: {},
    setup() {
        const jobs = ref<Job[]>([
            {
                title: "Farm worker",
                location: "Cecebre",
                salary: 30000,
                id: "1",
            },
            {
                title: "Musician",
                location: "Culleredo",
                salary: 50000,
                id: "2",
            },
            {
                title: "Web Developer",
                location: "Berlin",
                salary: 80000,
                id: "3",
            },
            {
                title: "Busines developement",
                location: "Switzerland",
                salary: 100000,
                id: "4",
            },
            {
                title: "Waiter",
                location: "Coruña",
                salary: 20000,
                id: "5",
            },
        ]);

        return { jobs };
    },
});
</script>

<style></style>
