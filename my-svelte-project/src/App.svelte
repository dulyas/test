<script>
import Block from "./Block.svelte";
const blocks = [
	{
		color: 'red',
		opacity: 1,
	},
	{
		color: 'blue',
		opacity: 1,
	},
	{
		color: 'green',
		opacity: 1,
	},
];

function handleClick(i) {
	if (blocks[i].opacity === 1) {
		blocks.forEach((block) => block.opacity = 1);
		blocks[i].opacity = 0;
	} else if (blocks[i].opacity === 0) {
		blocks[i].opacity = 1;
	}
}

</script>

<main>

	{#each blocks as block, i}
	<div on:click={() => handleClick(i)}>
		<Block bgColor={block.color} opacity={block.opacity} />
	</div>
	{/each}

</main>

<style lang="scss">
	main {
		display: flex;
		justify-content: space-around;
		margin: 0 auto;
		width: 1020px;
	}
</style>