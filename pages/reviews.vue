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
        <PageTitle>Reviews</PageTitle>
        <Reviews />
    </div>
</template>
    
<script>
export default {
    name: 'ReviewsPage',
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
    