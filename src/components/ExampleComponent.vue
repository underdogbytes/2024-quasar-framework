<template>
	<div>
		<q-item-section>
			<q-item-label>
				{{ title }}
			</q-item-label>
			<q-item-label caption>
				<q-badge
					color="blue-4"
					text-color="white"
				>
					nao sei o que to fazendo /ᐠ - ˕ -マ
					<q-icon
						name="thumb_up"
						size="14px"
						class="q-ml-xs"
					/>
				</q-badge>
			</q-item-label>
		</q-item-section>

		<ul>
			<li
				v-for="todo in todos"
				:key="todo.id"
			>
				<input
					type="checkbox"
					name="todo"
				/>
				{{ todo.content }}
			</li>
		</ul>
	</div>
</template>

<script setup lang="ts">
import { computed } from 'vue';
import { Todo } from './models';

interface Props {
	title: string;
	todos?: Todo[];
}
const props = withDefaults(defineProps<Props>(), {
	todos: () => [],
});

const todoCount = computed(() => props.todos.length);
</script>

<style scoped>
ul > li {
	list-style-type: none;
}
</style>
