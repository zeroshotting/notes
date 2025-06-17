---
created: 2025-06-17
confidence level: low
review count: 0
---
# Vanilla
---
Simple request implementation:

```javascript
async function getPost() {
	try {
		const res = await fetch("https://someurl.com/api");
		const data = await res.json();
		console.logo(data);
	} catch (error) {
		console.error("Error: ", error);
	}
} 

getPost();
```

OR

```javascript
fetch("https://someurl.com/api")
	.then(res => res.json())
	.then(data => console.log(data))
	.catch(error => console.error("Error: ", error));
```

# Vue
---
Started learning vue. Basically it's a JS framework that has a more similar syntax to plain html as opposed to React's JSX (by default at least. there's still a lot I don't know about Vue). To start a simple Vue application you can run:

```bash
bun create vue@latest
```

It gives some prompts about whether to use JS or TS or whether to use Prettier or ESLint, etc bootstrap stuff. After that you can `cd` into the project folder and run `bun install` to install the required packages and `bun run dev` to start the server. You're met with the default structure and some placeholder code in the `src/components` directory which you can delete. `main.js` is the entry point of the application and it's included in an `index.html` file as a module. Vue is very component based. A vue component typically has three parts: `<script>`, `<template>`, and `style` for the logic, structure and appearance respectively.

Writing components in Vue can be done in two ways:

- Optional
- Composition

Vue also has some stuff called directives that allow you to attach conditions to the elements in `<template>`.
Best way to explain this is using code, so here are three code snippets:

```vue
<!-- optional method -->
<script>
export default {
	data() {
		return {
			name: 'John Doe',
			status: true,
			tasks: ['task one', 'task two', 'task three'],
			link: "https://google.com"
		}
	},
	methods: {
		toggleStatus() {
			if (this.status === true) this.status = false;
			else this.status = true;
		}
	}
}
</script>

<template>
	<h1>{{ name }}</h1>
	<p v-if="status === true">Status is true</p> <!-- directive in action -->
	<p v-else>Status is false</p>

	<ul>
		<li v-for="task in tasks" :key="task">{{ task }}</li>
	</ul>
	<a :href="link">click for google</a>

	<button @click="toggleStatus"></button>
</template>
```

```vue
<!-- composition method 1 -->
<script>
import { ref } from 'vue';

export default {
	setup() {
		const name = ref('John Doe');
		const status = ref(true);
		const tasks = ref(['task one', 'task two', 'task three']);

		const toggleStatus = () => {
			if (status.value == true) status.value = false; 
			else status.value = true;
		};

		return {
			name,
			status,
			tasks,
			toggleStatus
		};
	};
}
</script>

<template>
	<h1>{{ name }}</h1>
	<p v-if="status === true">Status is true</p> <!-- directive in action -->
	<p v-else>Status is false</p>

	<ul>
		<li v-for="task in tasks" :key="task">{{ task }}</li>
	</ul>

	<button @click="toggleStatus"></button>
</template>
```

```vue
<!-- composition method 2: the best imo -->
<script>
import { ref } from 'vue';

const name = ref('John Doe');
const status = ref(true);
const tasks = ref(['task one', 'task two', 'task three']);

const toggleStatus = () => {
	if (status.value == true) status.value = false; 
	else status.value = true;
};
</script>

<template>
	<h1>{{ name }}</h1>
	<p v-if="status === true">Status is true</p> <!-- directive in action -->
	<p v-else>Status is false</p>

	<ul>
		<li v-for="task in tasks" :key="task">{{ task }}</li>
	</ul>

	<button @click="toggleStatus"></button>
</template>
```

> ⚠ The 2nd composition method creates _shared state_ between component instances. Use with care in dynamic UIs.