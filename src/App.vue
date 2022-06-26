<template>
    <div class="app">
        <header>
            <div class="order">
                <button @click="handleClick('title')">Order by title</button>
                <button @click="handleClick('salary')">Order by salary</button>
                <button @click="handleClick('location')"
                    >Order by location</button
                >
            </div>
        </header>
        <JobList :jobs="jobs" :order="order" />
    </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobList.vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
    name: "App",
    components: { JobList },
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
        const order = ref<OrderTerm>("title");

        const handleClick = (term: OrderTerm) => {
            order.value = term;
        };

        return { jobs, handleClick, order };
    },
});
</script>

<style>
body {
    background-color: rgb(215, 215, 250);
}
header {
    text-align: center;
}
header .order {
    margin-top: 20px;
}
button {
    margin: 0 10px;
    color: #11c96a;
    border: 3px solid #11c96a;
    background: #f8f9f9;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
}
</style>
