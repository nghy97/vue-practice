<template>
	<ul class="list">
		<li
			:class="{ 'line-through': toDo.completed }"
			v-for="toDo in toDos"
			:key="toDo.key"
		>
			<input style="" type="checkbox" @change="completeToDo(toDo.key)" />
			{{ toDo.toDo }}
			<button @click="removeToDo(toDo.key)">
				삭제
			</button>
		</li>
	</ul>
</template>

<script>
export default {
	props: {
		toDos: {
			type: Array,
			default: () => [],
		},
		removeToDo: {
			type: Function,
			default: () => false,
		},
		completeToDo: {
			type: Function,
			default: () => false,
		},
	},
};
</script>

<style scoped>
ul {
	padding: 0;
}

li {
	list-style: none;
}

.line-through {
	text-decoration: line-through;
}
</style>
