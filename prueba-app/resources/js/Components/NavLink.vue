<script setup>
import { computed } from "vue";
import { Link } from "@inertiajs/vue3";

const props = defineProps({
    href: {
        type: String,
        required: true,
    },
    active: {
        type: Boolean,
    },
});

const classes = computed(() =>
    props.active
        ? "inline-flex items-center px-1 pt-1 "
        : "inline-flex items-center px-1 pt-1 focus:outline-none  "
);
</script>

<template>
    <Link :href="href" :class="classes">
        <slot />
    </Link>
</template>

<style>
a {
    text-decoration: none;
    color: black;
}
a:hover {
    text-decoration: none;
    color: black;
}
</style>
