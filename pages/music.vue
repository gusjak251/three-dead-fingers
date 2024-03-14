<template>
    <div class="bg-gradient-to-b from-emerald-950 from-5%  to-black to-90% min-h-screen pb-12">
        <Transition>
            <div class="fixed flex justify-center items-center w-full h-full z-50 bg-black pointer-events-none" v-if="isLoading">
                <img class="h-1/2 animate-pulse" src="images/tdf-ape.png" />
            </div>
        </Transition>
        <Navbar />
        <Header />
        <PageTitle>Music</PageTitle>
        <SectionTitle class="text-center">Upcoming releases</SectionTitle>
        <div class="album-card w-3/4 md:w-1/2 p-4 rounded-lg mx-auto flex flex-col" v-for="release in upcomingReleases" :key="release.name">
            <div class="flex flex-row mb-3 gap-4">
                <img :src="release.imageUrl" class="h-24 rounded-lg"/>
                <div class="flex-col mt-3">
                    <p class="text-white text-md text-left font-bold">{{ release.name }}</p>
                    <span class="divider my-1 mx-auto"></span>
                    <p class="text-gray-300 text-left">Release date: {{ release.releaseDate || "unknown"}}</p>
                </div>
            </div>
            <div>
                <p class="text-white pr-4">
                    {{ release.description }}
                </p>
            </div>
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
            isLoading: true,
            upcomingReleases: [
                {
                    name: "For the Next Species",
                    releaseDate: "2024-03-16",
                    description: "This unreleased album, blooming out in a mix of Psychedelia, Death Metal, unexpected rhythms & vivid melodies, marks the beginning of a new era for Three Dead Fingers.",
                    imageUrl: "images/for-the-next-species-cover.png",
                }
            ]
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
    