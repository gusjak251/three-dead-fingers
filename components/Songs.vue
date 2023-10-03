<template>
    <div class="flex flex-column justify-around gap-y-2 w-full">
        <div v-for="song in songs" :key="song.title" class="text-white text-center">
            <Title>{{ song.title }}</Title>
            <p>{{ song.description }}</p>
            <audio></audio>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Songs',
    data() {
        return {
            songs: [
                {
                    'link': 'images/fiskis.jpg',
                    'title': 'Coward in blue',
                    'description': 'Lallish song',
                },
                {
                    'link': 'images/fiskis.jpg',
                    'title': 'Five O Zero',
                    'description': 'Create a gap in time!'
                },
            ]
        }
    }
}
</script>
  