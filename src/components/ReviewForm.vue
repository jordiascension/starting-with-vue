<template>
  <form class="ReviewForm" @submit.prevent="onSubmit">
    <h3>Leave a review</h3>
    <div class="mb-3">
    <label for="name" class="form-label">Name:</label>
    <input id="name" class="form-control" v-model="name">
    </div>

    <div class="mb-3">
    <label for="review" class="form-label">Review:</label>      
    <textarea id="review" class="form-control" v-model="review"></textarea>
    </div>

    <div class="mb-3">
    <label for="rating" class="form-label">Rating:</label>
    <select id="rating" class="form-control" v-model.number="rating">
      <option>5</option>
      <option>4</option>
      <option>3</option>
      <option>2</option>
      <option>1</option>
    </select>
    </div>

    <input class="button" type="submit" value="Submit">
  </form>
</template>

<script>
export default {
    name: 'ReviewForm',
    data: () => ({
        name: '',
        review: '',
        rating: null
    }),
    methods: {
    onSubmit() {
        let productReview = {
        name: this.name,
        review: this.review,
        rating: this.rating,
        }
        this.$emit('review-submitted', productReview)    
        alert(JSON.stringify(productReview))
        this.name = ''
        this.review = ''
        this.rating = null
        }
    }
}
</script>

<style>

</style>