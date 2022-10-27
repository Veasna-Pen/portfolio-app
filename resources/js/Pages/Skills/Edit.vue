<template>
    <Head title="Update Skill" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
               Update Skills
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-md mx-auto sm:px-6 lg:px-8 bg-white">
                <form @submit.prevent="submit" class="p-4">
            <div>
                <InputLabel for="name" value="Name" />
                <TextInput id="name" type="text" class="mt-1 block w-full" v-model="form.name" autofocus autocomplete="Name" />
                <InputError class="mt-2" :message="$page.props.errors.name" />
            </div>

            <div class="mt-2">
                <InputLabel for="image" value="Image" />
                <TextInput id="image" type="file" class="mt-1 block w-full" @input="form.image = $event.target.files[0]"/>
                <InputError class="mt-2" :message="$page.props.errors.image" />
            </div>

            <div class="flex items-center justify-end mt-4">
                <PrimaryButton class="ml-4" :class="{ 'opacity-25': form.processing }" :disabled="form.processing">
                    Update
                </PrimaryButton>
            </div>
        </form>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<script setup>
import { Head, useForm } from '@inertiajs/inertia-vue3';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Inertia } from "@inertiajs/inertia";

const props = defineProps({
    skill: Object,
});

const form = useForm({
    name: props.skill?.name,
    image: null,
});

const submit = () => {
    Inertia.post(`/skills/${props.skill.id}`,{
        _method: "put",
        name: form.name,
        image: form.image,
    });
};
</script>
