<script>
	import { onMount } from 'svelte';
	import Button from '../../components/Button.svelte';
	import { passive } from 'svelte/legacy';

	let points = $state(0);
	let clickingPower = $state(1);
	let passiveIncome = $state(0);

    let upgradeClickCost = 20;
    let upgradePassiveCost = 100;

	onMount(() => {
		//INTERVAL
		let passiveTimer = setInterval(() => {
			points += passiveIncome;
		}, 1000);

		return () => clearInterval(passiveTimer);
	});

	function increment() {
		//make a button that increases seconds by 1
		points += clickingPower;
	}

	function upgradeClickingPower(amount) {
		if (points - amount * upgradeClickCost >= 0) {
			points -= amount * upgradeClickCost;
			clickingPower += amount;
		}
	}

    function upgradePassiveIncome(amount) {
        if(points - amount * upgradePassiveCost >= 0) {
            points-= amount * upgradePassiveCost;
            passiveIncome += amount;
        }
    }
</script>

<!-- container for game -->
<div class="flex h-screen flex-col items-center justify-center bg-blue-300">
    <div class="text-5xl m-2">Clicker Game</div>
    <div class="flex w-full border justify-around">
        <div>Clicking Power: {clickingPower}</div>
        <div>Passive Income: {passiveIncome}</div>
    </div>
	<div>{points}</div>
	<button
		onclick={increment}
		class="m-3 h-48 w-48 border bg-black rounded-full bg-gradient-to-r from-red-800 via-red-500 to-red-800 transition-all duration-100 active:scale-110"
	></button>
	<div class="flex w-full border text-center">
		<div class="w-1/2 flex flex-col">
			<div>Click Upgrades</div>
			<Button class="text-black" text="+1 - {1 * upgradeClickCost}" fn={() => upgradeClickingPower(1)}></Button>
			<Button class="text-black" text="+5 - {5 * upgradeClickCost}" fn={() => upgradeClickingPower(5)}></Button>
			<Button class="text-black" text="+20 - {20 * upgradeClickCost}" fn={() => upgradeClickingPower(20)}></Button>
		</div>
		<div class="w-1/2 flex flex-col">
			<div>Passive Upgrades</div>
			<Button class="text-black" text='+1 - {1 * upgradePassiveCost}' fn={() => upgradePassiveIncome(1)}></Button>
			<Button class="text-black" text='+5 - {5 * upgradePassiveCost}' fn={() => upgradePassiveIncome(5)}></Button>
			<Button class="text-black" text='+20 - {20 * upgradePassiveCost}' fn={() => upgradePassiveIncome(20)}></Button>
		</div>
	</div>
</div>
