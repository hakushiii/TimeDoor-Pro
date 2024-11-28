<script setup>
    import RecipeForm from '../recipeForm/RecipeForm.vue';
    
    import { useStore } from 'vuex';
    import { useRoute, useRouter } from 'vue-router';
    import { onMounted, ref } from 'vue';

    const store = useStore()
    const router = useRouter()
    const route = useRoute()

    var detailData = ref()
    var isLoading = false

    onMounted(async () => {
        isLoading = true
        try{
            await store.dispatch("recipe/getRecipeDetail", route.params.id)
            detailData = store.state.recipe.recipeDetail
            isLoading = false
        }  catch (err) {
            console.log(err)
        }
    })
</script>

<template>
    <main>
        <div class="container-md my-5 py-5">
            <RecipeForm v-if="!isLoading" :isEdit="true" :data="{detailData}"/>
        </div>
    </main>
</template>