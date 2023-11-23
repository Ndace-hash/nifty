<template>
    <div id="shape-container">
        <div class="border-b border-white  flex justify-between">
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
        </div>
        <div class="flex h-full flex-col md:flex-row">
            <div class="flex-grow flex flex-col">
                <div class="overflow-hidden">

                    <Circles class="py-12" />
                </div>
                <div class="py-4 px-6 border-t border-white">
                    <h3>Lorem, ipsum dolor.</h3>
                    <p>Lorem ipsum dolor sit amet.<br />Lorem ipsum dolor sit.</p>
                </div>
            </div>
            <div class="border-l border-white flex-grow flex flex-col">
                <div class="border-b border-white uppercase py-4 px-6">
                    <h3>Lorem, ipsum.</h3>
                    <p>Lorem ipsum dolor sit amet consectetur.</p>
                </div>
                <div class="overflow-hidden">

                    <Squares class="h-full py-12" />
                </div>
            </div>
        </div>
        <div class="border-t border-white flex justify-between">
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
            <div class="border-r border-white py-2 px-4 flex items-center justify-center flex-grow"><span>Lorem,
                    ipsum.</span>
            </div>
        </div>

    </div>
</template>

<script setup>
import Circles from './Circles.vue';
import Squares from './Squares.vue'
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
onMounted(() => {
    // gsap.fromTo(obj.value, { scale: 0, duration: 3 }, { scale: 2, stagger: 2 })
    ScrollTrigger.create({
        trigger: "#obj",

        onEnter(self) {
            gsap.fromTo(self, { scale: 0, duration: 2, }, { scale: 1.5, scrollTrigger: { trigger: obj.value, } })
        }
    })
})

</script>

