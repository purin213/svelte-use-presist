<script>
	import { persist } from '$lib';

	const input_styles = 'border-2 border-black';
	const label_styles = 'font-black';
</script>

<main class="prose lg:prose-xl mb-4">
	<h1>svelte-use-persist demo</h1>

	<p>
		<a href="https://github.com/fawaz-alesayi/svelte-use-presist">svelte-use-persist</a> is a Svelte
		action that persists form values or individual inputs' values to localStorage and loads them back
		when the form or input is loaded again.
	</p>

	<p>Fill out any of the fields below and refresh the page. Their values will be restored!</p>
</main>

<form
	class="flex flex-col items-start max-w-4xl border-4 border-black p-4 gap-4 mb-8"
	id="my-form"
	data-testid="my-form"
	use:persist={{
		key: 'form-test'
	}}
>
	<label for="title" class={label_styles}>Title</label>
	<input type="text" name="title" data-testid="title" class={input_styles} />

	<label for="content" class={label_styles}>Content</label>
	<textarea name="content" data-testid="content" class={input_styles} />

	<label for="date" class={label_styles}>Date</label>
	<input type="date" name="date" data-testid="date" class={input_styles} />

	<label for="phone" class={label_styles}>Phone</label>
	<input type="tel" name="phone" data-testid="phone" class={input_styles} />

	<label for="email" class={label_styles}>Email</label>
	<input type="email" name="email" data-testid="email" class={input_styles} />

	<label for="url" class={label_styles}>URL</label>
	<input type="url" name="url" data-testid="url" class={input_styles} />

	<label for="number" class={label_styles}>Number</label>
	<input type="number" name="number" data-testid="number" class={input_styles} />

	<label for="range" class={label_styles}>Range</label>
	<input type="range" name="range" data-testid="range" class={input_styles} />

	<label for="color" class={label_styles}>Color</label>
	<input type="color" name="color" data-testid="color" class={input_styles} />

	<label for="checkbox" class={label_styles}>Checkbox</label>
	<input type="checkbox" name="checkbox" data-testid="checkbox" value="on" class={input_styles} />

	<label for="radio" class={label_styles}>Radio</label>
	<input type="radio" name="radio" data-testid="radio" value="on" class={input_styles} />

	<label for="select" class={label_styles}>Select</label>
	<select name="select" data-testid="select" class={input_styles}>
		<option value="1">One</option>
		<option value="2">Two</option>
		<option value="3">Three</option>
	</select>

	<label for="password" class={label_styles}>Password</label>
	<small>Passwords are not persisted by default</small>
	<input type="password" name="password" data-testid="password" />

	<!-- <label for="select-multiple">Select multiple</label>
	<select name="select-multiple" data-testid="select-multiple" multiple>
		<option value="1">One</option>
		<option value="2">Two</option>
		<option value="3">Three</option>
	</select> -->

	<!-- <button type="reset" data-testid="reset"> Reset </button> -->

	<button
		type="button"
		data-testid="clear"
		class="btn variant-filled-primary font-black border-black border-2"
		on:click={() => window.location.reload()}
	>
		Refresh Page
	</button>

	<button
		type="submit"
		data-testid="submit"
		class="btn variant-filled-primary font-black border-black border-2"
	>
		Submit
	</button>

	<button
		type="reset"
		data-testid="reset"
		class="btn variant-filled-primary font-black border-black border-2"
	>
		Reset Form
	</button>
</form>

<section id="discrete">
	<label for="discrete" class={label_styles}>Discrete input (outside form)</label>
	<input
		use:persist={{
			key: 'discrete'
		}}
		type="text"
		name="discrete"
		data-testid="discrete"
		class={input_styles}
	/>
</section>
