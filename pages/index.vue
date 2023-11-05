<template>
  <div class="bg-gradient-to-b from-emerald-950 from-5%  to-black to-70% min-h-screen pb-12">
    <Transition>
      <div class="fixed flex justify-center items-center w-full h-full z-50 bg-black pointer-events-none" v-if="isLoading"
        v-cloak>
        <img class="h-1/2 animate-pulse" src="images/tdf-ape.png" />
      </div>
    </Transition>
    <Navbar />
    <Header />
    <Bio class="mb-4" />
    <SectionTitle class="text-center">Reviews</SectionTitle>
    <Reviews :light="true" class="mb-20" />
    <SectionTitle class="text-center mt-4 mb-2">Members</SectionTitle>
    <div class="flex flex-col mx-auto md:flex-row justify-center gap-12 mb-20">
      <MemberCard v-for="member in members" :key="member.name" :name="member.name" :role="member.role"
        :img="member.image" />
    </div>
    <SectionTitle class="text-center mt-4 mb-2">Photos</SectionTitle>
    <Press-Photos />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      members: [
        {
          'name': 'Oliwer',
          'role': 'Singer/Guitarist/Songwriter',
          'image': 'images/oliwer.jpg'
        },
        {
          'name': 'Fiskis',
          'role': 'Guitarist/Songwriter',
          'image': 'images/fiskis.jpg'
        },
        {
          'name': 'Gustav',
          'role': 'Bass player',
          'image': 'images/gustav-portrait.jpg'
        },
        {
          'name': 'Henry',
          'role': 'Drummer',
          'image': 'images/henry.jpg'
        }
      ],
      isLoading: true
    }
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false;
    }, 50);
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Gabarito&display=swap');

* {
  font-family: 'Gabarito', cursive;
}

.v-enter-active,
.v-leave-active {
  transition: opacity .5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
