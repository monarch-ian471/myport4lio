<template>
  <section id="home">
    <div class="bg-gradient-to-r from-cyan-50/40 to-cyan-100/40 pt-20">
      <div class="grid grid-cols-1 laptop:grid-cols-2 items-end gap-8 laptop:gap-20">
        <!-- left side -->
        <div
          class="col-span-1 order-2 laptop:order-1 px-4 laptop:px-10 py-10 flex items-center gap-8 desktop:gap-14"
          >
          <div
            className="flex items-center gap-10 text-white"
            :style="{ writingMode: 'vertical-rl' }"
          >
            <ArrowLongDownIcon class="w-10 laptop:w-24 h-14 text-primary" />
            </div>

          <div class="space-y-3 laptop:space-y-6">
            <h1 class="text-white-soft text-3xl laptop:text-5xl font-medium">Ian Katengeza</h1>
            <div class="space-y-3">
              <p class="text-xl font-normal text-primary">Developer</p>
              <p class="text-base font-normal text-dark-1">
                I am a programmer, tech enthusiast, and passionate learner. My passion for Computer Science is driven by technology's seamless integration into everyday life, and its ability to make people's lives easier, it's not just ones and zeros, but a sense of purpose. I have gained experience through IT internships, progressing from IT Assistant to Junior Software Developer. Additionally, I have worked in administration and operations roles to develop strong interpersonal skills and enhance my career growth.
              </p>
            </div>
            <div class="flex gap-2">
              <PrimaryLink text="Contact me" link="#contact" />
              <SecondaryLink
                text="Download CV"
                link="/files/Ian-Katengeza-Resume.pdf"
                :icon="ArrowDownTrayIcon"
                download="/files/Ian-Katengeza-Resume.pdf"
              />
            </div>

            <ul class="flex items-center gap-2">
              <li v-for="social in socials" :key="social.id">
                <a
                  :href="social.link"
                  target="_blank"
                  class="h-10 w-10 rounded-full bg-white shadow-sm flex items-center justify-center text-black-mute hover:bg-primary hover:text-white-soft transition-all duration-300"
                >
                  <component :is="social.icon" class="h-5 w-5" />
                </a>
              </li>
            </ul>
          </div>
        </div>

        <!-- right side -->
         <div class="col-span-1 order-1 laptop:order-2 relative">
            <div class="relative h-[300px] w-[300px] laptop:h-[400px] laptop:w-[400px] mx-auto flex items-center justify-center">
              
              <!-- Rectangle -->
              <div class="absolute bottom-1/2 right-0 w-[150px] h-[100px] laptop:w-[250px] laptop:h-[125px] bg-black-soft animate-pulse"></div>

              <!-- Circle -->
              <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[100px] h-[100px] laptop:w-[150px] laptop:h-[150px] bg-primary rounded-full animate-pulse-slow"></div>

              <!-- Triangle -->
              <div class="absolute top-0 right-0 w-0 h-0 border-l-[50px] border-l-transparent border-r-[50px] border-r-transparent border-b-[100px] border-secondary laptop:border-l-[75px] laptop:border-r-[75px] laptop:border-b-[150px] animate-bounce"></div>

            </div>
          </div>
        </div>

         <!-- animation style -->
         <div class="col-span-1 order-1 laptop:order-2 relative">
        </div>
      </div>
  </section>
</template>

<script setup>
import { ArrowLongDownIcon, ArrowDownTrayIcon } from '@heroicons/vue/24/solid'
import PrimaryLink from '@/components/buttons/PrimaryLink.vue'
import SecondaryLink from '@/components/buttons/SecondaryLink.vue'
import LinkedInIcon from '../icons/LinkedInIcon.vue'
import FacebookIcon from '../icons/FacebookIcon.vue'

const socials = [
  {
    id: 1,
    name: 'LinkedIn',
    icon: LinkedInIcon,
    link: 'https://www.linkedin.com/in/ian-katengeza-2529a0206'
  },
  {
    id: 2,
    name: 'Facebook',
    icon: FacebookIcon,
    link: 'https://www.facebook.com/Iang0407/'
  }
]
</script>
