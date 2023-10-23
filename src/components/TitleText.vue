<!--
    This component wants to reproduce a "markdown" title this is experimental, and might 
    be misimplemented, but we need this so if you want to upgrade this, you are welcome 
-->
<script setup lang="ts">
import { computed } from 'vue'
import { isString } from '@utils/typecheck'

export interface TitleTextProps {
    level?: number|string
    symbol?: string
}
const props = withDefaults(defineProps<TitleTextProps>(), {
    level: 1,
    symbol: '#'
})

const levelNumber = computed(() => {
    const num = isString(props.level) ?  Number.parseInt(props.level, 10) : props.level
    if (isNaN(num)) throw Error(`Unable to convert the value ${props.level} to a number`)
    if (num < 1 || num > 4) return 4
    return num
})

const parsedSymbol = computed(() => {
    const fixed = props.symbol.trim()
    return fixed.charAt(0) || '#'
})

const LevelTag = computed(() => `h${levelNumber.value}`)

const isLevel = (value: number) => levelNumber.value === value

const beforeTextSize = computed(() => ({
    'before:text-7xl': levelNumber.value === 1,
    'before:text-6xl': levelNumber.value === 2,
    'before:text-5xl': levelNumber.value === 3,
    'before:text-4xl': levelNumber.value === 4,
}))

const textSize = computed(() => ({
    'text-6xl': levelNumber.value === 1,
    'text-5xl': levelNumber.value === 2,
    'text-4xl': levelNumber.value === 3,
    'text-3xl': levelNumber.value === 4,
}))

const styleClasses = computed(() => [
    {
        'mb-1': isLevel(4),
        'mb-5': isLevel(1),
        'mb-3': isLevel(2),
        'mb-2': isLevel(3),
    },
    beforeTextSize.value,
    textSize.value,
])
</script>
<template>
    <div
        class="before:content-[attr(symbol)] before:hover:text-slate-900 before:text-slate-400 dark:before:text-gray-700 dark:hover:before:text-gray-300 before:font-bold before:mr-1 before:transition-colors flex flex-row align-middle justify-stretch"
        :symbol="parsedSymbol"
        :class="styleClasses">
        
        <component
            :is="LevelTag">
            <slot />
        </component>
    </div>
</template>