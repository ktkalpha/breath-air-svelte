<script lang="ts">
	import { inhale, exhale } from '../stores';
</script>

<main class="flex flex-col items-center">
	<div class="mt-5">
		<p class="label-counter">들이마시기</p>
		<div class="flex flex-row">
			<button class="button mr-3" on:click={() => $inhale++}>+</button>
			<p class="counter">{$inhale}</p>
			<button
				class="button ml-3"
				on:click={() => {
					if ($inhale > 0) {
						$inhale--;
					}
				}}>-</button
			>
		</div>
	</div>
	<div class="splitter" />
	<div>
		<p class="label-counter">내쉬기</p>
		<div class="flex flex-row">
			<button class="button mr-3" on:click={() => $exhale++}>+</button>
			<p class="counter">{$exhale}</p>
			<button
				class="button ml-3"
				on:click={() => {
					if ($exhale > 0) {
						$exhale--;
					}
				}}>-</button
			>
		</div>
	</div>
	<a class="link-button" href="/exercise">시작</a>
</main>
