<script>
import MyComponent from './MyComponent.vue'
import another from './another.vue'

export default {
    components: {
        MyComponent,
        another
    },
    data() {
        return {
            posts: [
                { id: 1, title: 'title1' },
                { id: 2, title: 'title2' },
                { id: 3, title: 'title3' }
            ],
            title: 'mycomponent',
            postFontSize: 1,
            current: 'another'
        }
    },
    methods: {
        enlargeText() {
            this.postFontSize += 0.1
        },
        switchComponent() {
            this.current === 'another' ? this.current = 'MyComponent' : this.current = 'another'
        }
    }
}
</script>

<template>
    <div :style="{ fontSize: postFontSize + 'em' }">
        <!-- test git push -->
        <!-- <MyComponent v-for='post in posts' :key='post.id' :title='post.title' @enlarge-text='enlargeText'>
            123
        </MyComponent> -->
        <component :is='current'/>
    </div>
    <button @click="switchComponent"></button>
</template>