<template>
	<q-page class="row items-center justify-evenly">
		<carousel-index />
		<example-component
			title="🥐 TODO"
			:todos="todos"
			:meta="meta"
		/>
	</q-page>
</template>

<script setup lang="ts">
import { Todo, Meta } from 'components/models';
import ExampleComponent from 'components/ExampleComponent.vue';
import CarouselIndex from 'src/components/CarouselIndex.vue';
import { ref } from 'vue';

const todos = ref<Todo[]>([
	{
		id: 1,
		content: 'Ir comprar pão',
	},
	{
		id: 2,
		content: 'Lavar roupa',
	},
	{
		id: 3,
		content: 'Dormir',
	},
	{
		id: 4,
		content: 'Assistir HunterXHunter',
	},
	{
		id: 5,
		content: 'Procurar trabaio',
	},
]);
const meta = ref<Meta>({
	totalCount: 1200,
});
</script>
