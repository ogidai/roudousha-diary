<template>
  <div>
    <b-card-group>
        <b-card>
            <router-link to="/">
            <h2>{{ postDate }}</h2>
            <p>{{ postContent }}</p>
            </router-link>
        </b-card>
    </b-card-group>
    <NewPostButton />
  </div>
</template>

<script>
import NewPostButton from '@/components/NewPostButton'

export default {
  name: 'Home',
  components: {
    NewPostButton
  },
  data() {
        return {
            postId: 1,
            postDate: '2020/02/00',
            postContent: 'samplesamplesamplesamplesamplesamplesamplesamplesamplesamplesamplesamplesample'
        }
    }
}
</script>

<style>

</style>

