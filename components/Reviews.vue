<template>
    <div class="flex flex-row justify-evenly w-3/4 mx-auto">
        <div v-for="review in reviews" :key="review.url">
            <Review :author="review.author" :rating="review.rating" :quote="review.quote" :url="review.url" />
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Reviews',
    props: {
        light: {
            type: Boolean,
            default: false
        },
    },
    data() {
        return {
            reviews: [
                {
                    author: 'Sweden rock mag',
                    rating: '7.5/10',
                    quote: 'Micke bra!',
                    url: 'https://www.youtube.com'
                },
                {
                    author: 'Deutsche metal',
                    rating: '9/10',
                    quote: '"Its the fookin best!"',
                    url: 'https://www.google.com'
                }
            ]
        }
    }
}
</script>
  