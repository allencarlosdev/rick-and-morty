<template>
    <div class="search">
        <input class="search__input"
        type="text"
        placeholder="Search by name"
        v-model="name"
        @keyup="filter()"
        >
    </div>
</template>
<script>
import { ref } from 'vue'
import { useStore } from 'vuex'
export default {
    setup(){
        const store = useStore()
        const name = ref('')

        const filter = () => {
            store.dispatch('filterByName', name.value)
        }

        return {
            name,
            filter,
        }
    }
}
</script>
<style>
    .search{
        width: 25rem;
        margin: 3rem auto 0;
    }
    .search__input{
        height: 3.313rem;
        width: 25rem;
        border:none;
        border-radius: 0.625rem;
        padding: 0 0.5rem;
    }
</style>