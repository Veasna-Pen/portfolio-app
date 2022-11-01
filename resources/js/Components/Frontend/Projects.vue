<template>
    <div class="container mx-auto">
        <nav
            class="mb-12 border-b-2 border-light-tail-100 dark:text-dark-navy-100"
        >
            <ul class="flex flex-col lg:flex-row justify-evenly items-center">
                <li class="cursor-pointer capitalize m-4">
                    <button
                        class="inline-block py-3 px-4 rounded-lg hover:text-gray-900 hover:bg-gray-100 dark:hover:bg-gray-800 dark:hover:text-white"
                    >
                        All
                    </button>
                </li>
                <li
                    class="cursor-pointer capitalize m-4"
                    v-for="projectSkill in skills.data"
                    :key="projectSkill.id"
                >
                    <button
                        class="inline-block py-3 px-4 rounded-lg hover:text-gray-900 hover:bg-gray-100 dark:hover:bg-gray-800 dark:hover:text-white"
                    >
                        {{ projectSkill.name }}
                    </button>
                </li>
            </ul>
        </nav>
        <section class="grid gap-y-12 lg:grid-cols-3 lg:gap-8">
            <Project v-for="project in projects.data" :key="project.id" :project="project" />
        </section>
    </div>
</template>

<script setup>

import Project from "./Project.vue";
defineProps({
    skills: Object,
    projects: Object,
});
</script>
