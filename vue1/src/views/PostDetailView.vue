<template>
   <div>
    <h2>This is a post page</h2>
    <p>Display the content of post with ID of {{ $route.params.id }} here</p>
    <div>
        <button @click="showPostId">Show post id</button>
    </div>
    <div>
        <button @click="goHomeIn3Seconds">Go Home in 3 seconds</button>
    </div>
    <div>
        <button @click="goToFirstPost">Go to first post</button>
    </div>
    <p><RouterLink to="/post">&lt; Back</RouterLink></p>
   </div>
</template>

<script setup>
    import { useRoute, useRouter } from 'vue-router'
    const route = useRoute()
    const router = useRouter()

    const showPostId = () => {
        alert(`The id of this post is ${ route.params.id }`)
    }

    const goHomeIn3Seconds= () => {
        setTimeout(() => {
            router.push({ name: 'home'})
        }, 3000);
    }
    const goToFirstPost= () => {
            router.push({ 
                name: 'postDetail', 
                params: {
                id: 'id1'
                }
            })
    }
</script>