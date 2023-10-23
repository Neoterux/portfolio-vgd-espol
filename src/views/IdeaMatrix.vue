<template>
    <main class="flex min-w-full">
        <h1 class="text-4xl text-center">Idea Matrix for Videogames</h1>
        <table>

        </table>
        <MatrixComponent :columns="columns" :data="data"/>
    </main>
</template>

<script setup lang="ts">
import MatrixComponent from '@/components/MatrixComponent.vue'
import { ref } from 'vue'

const columns = ref([
    'Idea 1',
    'Idea 2',
    'Idea 3',
    'Idea 4',
    'Idea 5',
    'Idea 6',
    'Idea 7',
    'Idea 8',
    'Idea 9',
    'Idea 10',
])

const data = ref([
    ['i1v1', 'i2v1', 'i3v1','i4v1','i5v1','i6v1','i7v1','i8v1','i9v1','i10v1',],
])
</script>