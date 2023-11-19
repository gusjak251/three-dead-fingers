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
        <PageTitle>Music</PageTitle>
        <SectionTitle class="text-center">Upcoming releases</SectionTitle>
        <div class="album-card px-2.5 py-1.5 w-72 rounded-md mx-auto flex flex-col">
            <p class="text-white text-center">For the Next Species</p>
            <span class="divider my-1 mx-auto"></span>
            <p class="text-gray-500 text-center">Release date: unknown</p>
        </div>
        <SectionTitle class="text-center">Previous releases</SectionTitle>
        <div class="space-y-5">
            <iframe style="border-radius:12px" class="mx-auto w-3/4 md:w-1/2"
                src="https://open.spotify.com/embed/album/2VNrduNdOJKoELeQF3LHgX?utm_source=generator&theme=0" height="352"
                frameBorder="0" allowfullscreen=""
                allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy">
            </iframe>
            <iframe style="border-radius:12px" class="mx-auto w-3/4 md:w-1/2"
                src="https://open.spotify.com/embed/album/3RYm1taDUhk9eNtYCczGEX?utm_source=generator&theme=0" height="352"
                frameBorder="0" allowfullscreen=""
                allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy">
            </iframe>
        </div>
    </div>
</template>
    
<script>
export default {
    name: 'MusicPage',
    data() {
        return {
            isLoading: true
        }
    },
    mounted() {
        this.isLoading = false;
    }
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
    