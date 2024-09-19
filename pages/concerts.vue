<template>
    <div class="bg-gradient-to-b from-emerald-950 from-5%  to-black to-90% min-h-screen pb-12">
        <Transition>
            <div class="fixed flex justify-center items-center w-full h-full z-50 bg-black pointer-events-none" v-if="isLoading">
                <img class="h-1/2 animate-pulse" src="images/tdf-ape.png" />
            </div>
        </Transition>
        <Navbar />
        <Header />
        <PageTitle>Upcoming concerts</PageTitle>
        <section class="flex flex-col gap-4 max-w-xl px-10 mx-auto">
            <ConcertCard 
                v-for="concert in visibleConcertCards"
                :key="concert.link"
                :name="concert.name"
                :location="concert.location"
                :date="concert.date"
                :description="concert.description"
                :link="concert.link"
            />
            <button 
                v-if="concerts.length > initialNumberOfCards" 
                @click="showAllCards = !showAllCards"
                class="text-white mx-auto flex flex-row items-center gap-1"
            >
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4" :class="showAllCards ? 'rotate-180' : ''">
                    <path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
                </svg>
                <span>{{ showAllCards ? "Show less" : "Show more" }}</span>
            </button>
        </section>
    </div>
</template>
    
<script>
export default {
    name: 'MusicPage',
    data() {
        return {
            isLoading: true,
            initialNumberOfCards: 3,
            showAllCards: false,
            concerts: [
                {
                    name: "Motor Rock Pub",
                    location: "Slupsk (PL)",
                    date: "2024-09-27",
                    description: "First show of 2024 tour",
                    link: "https://www.facebook.com/events/992584325850500"
                },
                {
                    name: "Centrala Klub Muzyczny",
                    location: "Kolobzreg (PL)",
                    date: "2024-09-28",
                    description: "Second show of 2024 tour",
                    link: "https://www.facebook.com/events/997678318700799"
                },
                {
                    name: "Krzywy Gryf",
                    location: "Szczecin (PL)",
                    date: "2024-09-29",
                    description: "Third show of 2024 tour",
                    link: "https://www.facebook.com/events/994364535299934"
                },
                {
                    name: "Otu Pub",
                    location: "Bydgoszcz (PL)",
                    date: "2024-10-01",
                    description: "Fourth show of 2024 tour",
                    link: "https://www.facebook.com/events/958888519320967"
                },
                {
                    name: "Voodoo Club",
                    location: "Warsaw (PL)",
                    date: "2024-10-02",
                    description: "Fifth show of 2024 tour",
                    link: "https://www.facebook.com/events/305457582660545"
                },
                {
                    name: "6scian Rock & Roll Pub",
                    location: "Bialystok (PL)",
                    date: "2024-10-03",
                    description: "Sixth show of 2024 tour",
                    link: "https://www.facebook.com/events/7911769108880258"
                },
                {
                    name: "Lemmy Music Club",
                    location: "Kaunas (LT)",
                    date: "2024-10-04",
                    description: "Seventh show of 2024 tour",
                    link: "https://www.facebook.com/events/389115547021713"
                },
                {
                    name: "Depo - Alternative Music Venue & Bar",
                    location: "Riga (LV)",
                    date: "2024-10-05",
                    description: "Eight show of 2024 tour",
                    link: "https://www.facebook.com/events/496547326160852"
                },
                {
                    name: "Tapper Rock Club",
                    location: "Tallinn (EE)",
                    date: "2024-10-06",
                    description: "Last show of 2024 tour",
                    link: "https://www.facebook.com/events/1489219678400338"
                },
            ]
        }
    },
    computed: {
        visibleConcertCards() {
            if(this.showAllCards) {
                return this.concerts;
            }
            return this.concerts.slice(0, this.initialNumberOfCards);
        }
    },
    mounted() {
        this.isLoading = false;
    },
}
</script>

<style>
h1 {
    font-weight: 100;
}

.album-card {
    background-color: #2a2a2a;
}

.divider {
    width: 80%;
    height: 1px;
    background-color: rgb(78, 78, 78);
}
</style>
    