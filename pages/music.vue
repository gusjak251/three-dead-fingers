<template>
    <div class="bg-gradient-to-b from-emerald-950 from-20%  to-black to-100% min-h-screen pb-12">
        <Navbar />
        <Header />
        <PageTitle>Music</PageTitle>
        <SectionTitle class="text-center">Upcoming releases</SectionTitle>
        <Songs />
        <SectionTitle class="text-center">Previous releases</SectionTitle>
    </div>
</template>
    
<script>
export default {
    name: 'MusicPage'
}
</script>

<style>
h1 {
    font-weight: 100;
}
</style>
    