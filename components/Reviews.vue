<template>
    <div class="flex flex-col flex-wrap gap-4 md:gap-0 md:flex-row justify-evenly items-center w-3/4 mx-auto">
        <div v-for="review in showReviews" :key="review.url">
            <Review :author="review.author" :record="review.record" :rating="review.rating" :quote="review.quote"
                :url="review.url" />
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
                    author: 'Metal Centre',
                    record: 'All Worlds Apart',
                    rating: '8.5/10',
                    quote: '"THREE DEAD FINGERS has great potential."',
                    url: 'https://www.metalcentre.com/2022/01/three-dead-fingers-all-worlds-apart/'
                },
                {
                    author: 'Dead rhetoric',
                    record: 'All Worlds Apart',
                    rating: '7.5/10',
                    quote: '"the future could look quite bright for them going into their third full-length"',
                    url: 'https://deadrhetoric.com/reviews/three-dead-fingers-all-worlds-apart-art-gates-records/'
                },
                {
                    author: 'Eternal terror',
                    record: 'All Worlds Apart',
                    rating: '4/6',
                    quote: '"this is a good release that shows great promise"',
                    url: 'https://eternal-terror.com/2022/01/13/three-dead-fingers-all-worlds-apart/'
                },
            ]
        }
    },
    computed: {
        showReviews() {
            if (this.light) {
                return this.reviews.splice(0, 3);
            }
            return this.reviews;
        }
    }
}
</script>
  