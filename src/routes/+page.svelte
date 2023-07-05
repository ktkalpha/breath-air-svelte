<script lang="ts">
	import { inhale, exhale } from '../stores';
</script>

<main class="flex flex-col items-center">
	<div class="card">
		<p class="label-counter">들이마시기</p>
		<div class="flex flex-row">
			<button class="button mr-3" on:click={() => $inhale++}>+</button>
			<p class="text-white text-[6rem]">{$inhale}</p>
			<button class="button ml-3" on:click={() => $inhale--}>-</button>
		</div>
	</div>
	<a class="link-button" href="/exercise">시작</a>
	<div class="card">
		<p class="label-counter">내쉬기</p>
		<div class="flex flex-row">
			<button class="button mr-3" on:click={() => $exhale++}>+</button>
			<p class="text-white text-[6rem]">{$exhale}</p>
			<button class="button ml-3" on:click={() => $exhale--}>-</button>
		</div>
	</div>
</main>
