<template>
    <div class="bg-gradient-to-b from-emerald-950 from-5%  to-black to-90% min-h-screen pb-12">
        <Transition>
            <div class="fixed flex justify-center items-center w-full h-full z-50 bg-black pointer-events-none"
                v-if="isLoading" v-cloak>
                <img class="h-1/2 animate-pulse" src="images/tdf-ape.png" />
            </div>
        </Transition>
        <Navbar />
        <Header />
        <PageTitle>Contact information</PageTitle>
        <div class="gap-4 flex flex-col justify-evenly mx-auto px-10 max-w-xl">
            <ContactCard 
                v-for="member in members" 
                :key="member.name" 
                :name="member.name" 
                :role="member.role" 
                :email="member.email"
                @copy="showSnack = true"
            />
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
            showSnack: false,
            isLoading: true
        }
    },
    methods: {
        copyEmail(email) {
            navigator.clipboard.writeText(email);
            if (!this.showSnack) this.showSnack = true;
        }
    },
    mounted() {
        this.isLoading = false;
    }
}
</script>
  
<style>
@import url('https://fonts.googleapis.com/css2?family=Gabarito&display=swap');

* {
    font-family: 'Gabarito', cursive;
}
</style>
  