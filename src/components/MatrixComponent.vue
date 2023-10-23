<template>
    <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
        <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
            <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                <tr>
                    <th  scope="col"></th>
                    <th v-for="(headContent, index) in columns" :key="index" class="px-6 py-3">
                        <slot  name="cell-head">
                            {{ headContent }}
                        </slot>

                    </th>
                </tr>
            </thead>

            <tbody>
                <tr v-for="(row, index) in data" :key="index" class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
                    <td scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                        Variante {{ index + 1 }}
                    </td>
                    <td v-for="(data, colIndex) in row" :key="`cell-r${colIndex}-c${index}`" class="px-6 py-4">
                        {{ data }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup lang="ts">

import { emptyArray } from '../utils/common'

export interface IdeaProps {
    columns?: string[]
    data?: string[][]
}

withDefaults(defineProps<IdeaProps>(), {
    columns: () => emptyArray<string>(),
    data: () => emptyArray<string[]>()
})
</script>