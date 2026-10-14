<script lang="ts" setup>
import { PropType } from 'vue';
import { ToastType } from '../../types';

defineProps({
	id: {
		type: Number,
		required: true,
	},
	type: {
		type: String as PropType<ToastType>,
		default: ToastType.Success,
	},
	message: {
		type: String,
		required: true,
	},
});
</script>

<template>
	<div
		class="w-full p-4 rounded-xl shadow-md border"
		:class="{'bg-red-500/15 border-red-500/30': type === ToastType.Error, 'bg-emerald-500/15 border-emerald-500/30': type === ToastType.Success, 'bg-sky-500/15 border-sky-500/30': type === ToastType.Info}">
		<span class="text-sm" :class="{'text-red-300': type === ToastType.Error, 'text-emerald-300': type === ToastType.Success, 'text-sky-300': type === ToastType.Info}">
			{{ message }}
		</span>
	</div>
</template>