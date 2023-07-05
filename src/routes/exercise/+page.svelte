<script lang="ts">
	import { TextToSpeech } from '@capacitor-community/text-to-speech';
	import { getStores } from '$app/stores';
	import { onMount } from 'svelte';
	import { inhale, exhale } from '../../stores';
	let time = 0;
	let step = 1;
	onMount(() => {
		say('들숨');
	});

	function say(text: string) {
		return TextToSpeech.speak({
			text: text,
			lang: 'ko-KR',
			rate: 1.0,
			pitch: 1.0,
			volume: 1.0,
			category: 'ambient'
		});
	}

	let timer = setInterval(() => {
		time++;
		if (step === 1 && time >= $inhale) {
			say('날숨');
			time = 0;
			step = 2;
		} else if (step === 2 && time >= $exhale) {
			say('들숨');
			time = 0;
			step = 1;
		}
	}, 1000);
</script>

<main class="flex flex-col">
	<!-- {$inhale} -->
	<!-- {$exhale} -->
	{#if step === 1}
		<p class="time-ind">{$inhale - time}</p>
		<p class="msg">들이마시기</p>
	{/if}
	{#if step === 2}
		<p class="time-ind">{$exhale - time}</p>
		<p class="msg">내쉬기</p>
	{/if}
	<a
		class="link-button"
		href="/"
		on:click={() => {
			clearInterval(timer);
		}}>멈추기</a
	>
</main>
