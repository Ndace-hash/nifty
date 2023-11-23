<script setup>
import Box from './components/Box.vue'
import ShapeContainer from './components/ShapeContainer.vue'
import { ref, onMounted } from 'vue'

import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
onMounted(() => {
  ScrollTrigger.batch(".box", {
    onEnter(batch) {
      gsap.fromTo(batch,
        {
          opacity: 0,
          duration: 15
        },
        {
          opacity: 1,
          stagger: 0.5,
          scrollTrigger: {
            trigger: batch,
            start: "20% bottom",
            end: "80% bottom",
            scrub: true
          }
        }
      )
    },
    onLeave(batch) {
      gsap.to(batch, { opacity: 0 })
    },
    onEnterBack(batch) {
      gsap.to(batch, { opacity: 1 })
    }
  })
})


const obj = ref(null)
onMounted(() => {
  const inView = ref(ScrollTrigger.isInViewport(obj.value, 1))


  ScrollTrigger.observe({
    target: window,
    type: "wheel,touch,pointer,scroll",
    onDown() {
      gsap.to(obj.value, {
        scale: 4
      })
    },
    onUp() {
      gsap.to(obj.value, {
        scale: 0.5
      })
    }
  })
})


</script>

<template>
  <Box class="py-4 h-[100px]">
    <div class="flex text-white justify-between px-8 items-center h-full">
      <p>Lorem ipsum dolor </p>
      <p>Lorem ipsum dolor </p>
      <p>Lorem ipsum dolor </p>
    </div>
  </Box>
  <Box class="h-[250px] flex items-center justify-center">
    <h1 class="font-bold text-[40px] md:text-[80px]">Lorem. Lorem</h1>
  </Box>
  <Box class="py-4 h-[100px]">
    <div class="flex text-white justify-between px-8 items-center h-full">
      <p>Lorem ipsum dolor </p>
      <p>Lorem ipsum dolor </p>
      <p>Lorem ipsum dolor </p>
    </div>
  </Box>
  <Box class=" h-[700px]">
    <img src="./assets/images/sky-city.jpg" alt="sky-city" class="w-full h-full object-cover">
    <div class="border border-white absolute right-0 top-0 rounded-lg rounded-tl-none rounded-br-none bg-[#434343]">
      <div class="flex">
        <div class="border border-x-white px-3 py-2 md:px-8 md:py-3">hello</div>
        <div class="border border-x-white px-3 py-2 md:px-8 md:py-3">hello</div>
        <div class="border border-x-white px-3 py-2 md:px-8 md:py-3">hello</div>
        <div class="border border-x-white px-3 py-2 md:px-8 md:py-3">hello</div>
      </div>
      <div class="flex justify-between">
        <div class="border-x-white border px-8">hello</div>
        <div class="flex flex-col justify-between gap-y-12 flex-grow-0 ">
          <h2 class="uppercase">Initiate sequence</h2>
          <h2 class="capitalize text-sm text-right">do something <br />to get this</h2>
        </div>
      </div>
    </div>
    <button
      class="absolute bottom-0 left-0 bg-white rounded-lg px-6 py-1 uppercase rounded-br-none rounded-tl-none text-black">Lorem,
      ipsum.</button>
  </Box>
  <Box class="py-4">
    <div class="flex text-white">
      <p>Edit sequence initiated</p>
      <p>Edit sequence initiated</p>
      <p>Edit sequence initiated</p>
    </div>
  </Box>
  <Box class="flex min-h-[300px]">
    <div class="flex flex-col justify-between">
      <div class="uppercase about  text-sm md:text-lg leading-loose">
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing. <span>Lorem, ipsum.</span> Lorem, ipsum dolor.
          <span>gramatis</span>
          and
          <span>Lorem.
          </span>.
        </p>
        <p>Lorem ipsum dolor sit amet consectetur. <span>Lorem ipsum dolor sit.</span>, Lorem ipsum dolor sit amet
          consectetur adipisicing elit.</p>
      </div>
      <div class="border-t border-white flex w-full justify-between">
        <div class="border-r border-white flex-grow flex items-center justify-center py-3 uppercase"> hello</div>
        <div class="border-r border-white flex-grow flex items-center justify-center py-3 uppercase"> hello</div>
        <div class="border-r border-white flex-grow flex items-center justify-center py-3 uppercase"> hello</div>
        <div class="border-r border-white flex-grow flex items-center justify-center py-3 uppercase"> hello</div>
      </div>
    </div>
    <div class="border-x px-4 w-max">
      <h1 class=" text-[15px] md:text-[40px] leading-none font-bold uppercase my-2">Breaking <br /> <span
          class="text-[24px] md:text-[70px]">News</span>
      </h1>
      <h1 class=" text-[15px] md:text-[40px] leading-none font-bold uppercase my-2">Breaking <br /> <span
          class="text-[24px] md:text-[70px]">News</span>
      </h1>
      <h1 class=" text-[15px] md:text-[40px] leading-none font-bold uppercase my-2">Breaking <br /> <span
          class="text-[24px] md:text-[70px]">News</span>
      </h1>
      <h1 class=" text-[15px] md:text-[40px] leading-none font-bold uppercase my-2">Breaking <br /> <span
          class="text-[24px] md:text-[70px]">News</span>
      </h1>
      <h1 class=" text-[15px] md:text-[40px] leading-none font-bold uppercase my-2">Breaking <br /> <span
          class="text-[24px] md:text-[70px]">News</span>
      </h1>
      <h1 class=" text-[15px] md:text-[40px] leading-none font-bold uppercase my-2">Breaking <br /> <span
          class="text-[24px] md:text-[70px]">News</span>
      </h1>
    </div>
    <div class="hidden md:flex md:w-1/4 ">
      <div class="border-b border-white flex items-center justify-center py-8">
        <div class="border-2 border-white rounded-full w-[150px] h-[150px]">
        </div>
      </div>
    </div>
  </Box>
  <Box class=" flex h-[400px] md:h-screen overflow-hidden">
    <iFrame src="/pacman.live/play.html" width="100%" height="100%" class="w-full h-full"></iFrame>
  </Box>
  <Box class="min-h-[400px]">
    <ShapeContainer />
  </Box>
  <Box class=" h-[600px] flex items-center justify-center">
    <img src="./assets/images/sky-city.jpg" alt="" class="object-cover w-full h-full">
    <div class="flex items-center justify-center absolute" ref="obj">
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
  </Box>
  <Box class="py-4 h-[100px]">
    <div class="flex text-white justify-between px-8 items-center h-full">
      <p>Lorem ipsum dolor </p>
      <p>Lorem ipsum dolor </p>
      <p>Lorem ipsum dolor </p>
    </div>
  </Box>
</template>


<style scoped>
.about p span {
  background-color: white;
  color: black;
}
</style>