<template>
  <div class="bg-gradient-to-b from-emerald-950 from-20%  to-black to-100% min-h-screen pb-12">
    <Navbar />
    <Header />
    <Bio />
    <Press-Photos />
    <Title class="text-center mt-4 mb-2">Members</Title>
    <div class="flex flex-row justify-center gap-2">
      <MemberCard v-for="member in members" :key="member.name" :name="member.name" :role="member.role"
        :img="member.image" />
    </div>
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
          'image': 'images/band-photo.jpg'
        },
        {
          'name': 'Henry',
          'role': 'Drummer',
          'image': 'images/henry.jpg'
        }
      ],
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Gabarito&display=swap');

* {
  font-family: 'Gabarito', cursive;
}
</style>
