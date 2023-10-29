<template>
    <div class="bg-gradient-to-b from-emerald-950 from-20%  to-black to-100% min-h-screen pb-12">
        <Navbar />
        <Header />
        <PageTitle>Contact information</PageTitle>
        <div class="flex flex-col md:flex-row gap-y-4 md:gap-y-0 justify-evenly w-3/4 mx-auto">
            <div class="flex flex-col w-full md:w-40 text-center md:text-left">
                <Title>Name</Title>
                <p v-for="member in members" :key="member.email" class="text-white">
                    {{ member.name }}
                </p>
            </div>
            <div class="flex flex-col w-full md:w-40 text-center md:text-left">
                <Title>Role</Title>
                <p v-for="member in members" :key="member.email" class="text-white">
                    {{ member.role }}
                </p>
            </div>
            <div class="flex flex-col w-full md:w-40 text-center md:text-left">
                <Title>Email</Title>
                <p v-for="member in members" :key="member.email" @click="copyEmail(member.email)"
                    class="text-white cursor-pointer hover:opacity-75">
                    {{ member.email }}
                </p>
            </div>
        </div>
        <Snack @hide="showSnack = false" :show="showSnack" :text="'Link copied to clipboard'"></Snack>
    </div>
</template>
  
<script>
export default {
    name: 'ContactPage',
    data() {
        return {
            members: [
                {
                    'name': 'Main Contact',
                    'email': 'info@threedeadfingers.com',
                    'role': 'Booking'
                },
                {
                    'name': 'Oliwer',
                    'email': 'oliwer.bergman@threedeadfingers.com',
                    'role': 'Singer/Guitarist/Songwriter'
                },
                {
                    'name': 'Fiskis',
                    'email': 'remy.fiskis3df@gmail.com',
                    'role': 'Guitarist/Songwriter'
                },
                {
                    'name': 'Gustav',
                    'email': 'gustavjakobsson3@gmail.com',
                    'role': 'Bass player'
                },
                {
                    'name': 'Henry',
                    'email': 'henrybp04@gmail.com',
                    'role': 'Drummer'
                }
            ],
            showSnack: false
        }
    },
    methods: {
        copyEmail(email) {
            navigator.clipboard.writeText(email);
            if (!this.showSnack) this.showSnack = true;
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
  