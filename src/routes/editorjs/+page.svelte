<script>
	import { createEditor } from 'svelte-editorjs'
	const { editor, data, isReady } = createEditor()
	
	$: {
		if (isReady) {
			console.log('Saved data:', $data)
		}
	}
</script>

<h1>EditorJS</h1>
<div class=editor use:editor />
<button on:click={() => $editor.clear()}>Clear contents</button>
<button on:click={() => $editor.save()}>Save contents</button>

<style>
	.editor {
		border: 2px solid #ccc;
	}
</style>