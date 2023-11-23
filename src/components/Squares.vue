<template>
    <div class=" flex items-center justify-center" ref="obj">
        <div class="w-[300px] h-[300px] rounded-2xl border border-white relative flex items-center justify-center">
            <div class="w-[80%] h-[80%] rounded-2xl border border-white flex items-center justify-center">
                <div class="w-[70%] h-[70%] rounded-2xl border border-white flex items-center justify-center">
                    <div class="w-[60%] h-[60%] rounded-2xl border border-white flex items-center justify-center">
                        <div class="w-[50%] h-[50%] rounded-2xl border border-white flex items-center justify-center">
                            <div class="w-[40%] h-[40%] rounded-2xl border border-white flex items-center justify-center">
                            </div>

                        </div>

                    </div>

                </div>

            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger'

const obj = ref(null)
onMounted(() => {
    const inView = ref(ScrollTrigger.isInViewport(obj.value, 1))

    if (inView) {

        ScrollTrigger.observe({
            target: window,
            type: "wheel,touch,pointer,scroll",
            onDown() {
                gsap.to(obj.value, {
                    scale: '3'
                })
            },
            onUp() {
                gsap.to(obj.value, {
                    scale: 0.5
                })
            }
        })
    }
})
</script>