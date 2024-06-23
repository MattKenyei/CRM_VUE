<script setup lang="ts">
import { cn } from '@/utils'
import { buttonVariants } from './index'

interface Props {
	variant?: NonNullable<Parameters<typeof buttonVariants>[0]>['variant']
	size?: NonNullable<Parameters<typeof buttonVariants>[0]>['size']
	as?: string
}

const props = withDefaults(defineProps<Props>(), {
  as: 'button',
})
</script>

<template>
  <Primitive
    :as="as"
    :as-child="asChild"
    :class="cn(buttonVariants({ variant, size }), props.class)"
  >
    <slot />
  </Primitive>
</template>
