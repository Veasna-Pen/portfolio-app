<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';
import FrontendLayout from '@/Layouts/Frontend.vue';
import Hero from '@/Components/Frontend/Hero.vue';
import Promote from '@/Components/Frontend/Promote.vue';
import About from '@/Components/Frontend/About.vue';

</script>

<template>
    <Head title="Welcome" />
    <FrontendLayout>
    <!--Hero Section-->
    <Hero />
    <!--Promote Section-->
    <Promote />
    <!--About Section-->
    <About />
    <!--Skill Section-->
    <!--Portfolio-->
    <!--Service Section-->
    </FrontendLayout>
</template>
