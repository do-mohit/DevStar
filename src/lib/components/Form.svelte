<script>
	import { userCode, userLang, userTheme } from '../util/stores';
	import { get } from 'svelte/store';

	var code;
	const handleSubmit = () => {
		if (code) {
			userCode.update(() => code);
		}
	};
</script>

<div class="flex h-auto w-full">
	<form
		on:submit|preventDefault={handleSubmit}
		class="flex w-full flex-col bg-slate-800 px-4 pb-4 md:items-center"
	>
		<textarea
			class="
        m-0
        mb-5
        block
        w-full
        rounded
        border
        border-solid
        border-gray-300 bg-white
        bg-clip-padding px-3 py-1.5
        text-base
        font-normal
        text-gray-700
        transition
		ease-in-out
        focus:border-blue-600 focus:bg-white focus:text-gray-700 focus:outline-none
      "
			rows="12"
			placeholder="Your code"
			name="code"
			spellcheck={false}
			bind:value={code}
			on:change={({ target }) => {
				code = target.value;
			}}
		/>
		<button
			class="inline-block rounded bg-blue-600 px-6 py-2.5 text-xs font-medium uppercase leading-tight text-white shadow-md transition duration-150 ease-in-out hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg md:w-40"
			>Submit Code</button
		>
	</form>
</div>
