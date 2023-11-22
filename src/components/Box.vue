<template>
    <section class="box my-4 relative overflow-hidden">
        <slot />
    </section>
</template>

<script setup>
import gsap from 'gsap';
gsap.fromTo(".box", {
    x: 500,
    opacity: 0,
}, {
    x: 0,
    opacity: 1,
    duration: 2,
    stagger: 0.5
})
</script>