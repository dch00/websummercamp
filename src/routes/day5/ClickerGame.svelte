<script>

	import { onMount } from "svelte";
	import Button from "../../components/Button.svelte";

    let points = $state(1000000);
    let clickingPower = $state(1);
    let passiveIncome = $state(1);

    let upgradeClickCost = 100;
    let upgradePassiveCost = 500;

    onMount(() => {
        // INTERVAL
        let passiveTimer = setInterval(() => {
            points += passiveIncome;
        }, 1000);

        return () => clearInterval(passiveTimer);
    });

    function increment() {
        // make a button that increases seconds by 1
        points += clickingPower;
    }

    function upgradeClickingPower(amount) {
        if(points - amount * upgradeClickCost >= 0) {
            points -= amount * upgradeClickCost;
            clickingPower += amount;
        }
    }

    function upgradePassiveIncome(amount) {
        if(points - amount * upgradePassiveCost >= 0) {
            points -= amount * upgradePassiveCost;
            passiveIncome += amount;
        }
    }

</script>

<!-- container for game -->
<div class="h-screen bg-blue-200 flex flex-col justify-center items-center">
    <div>{points}</div>
    <button onclick={increment} class="active:scale-110 transition-all duration-250 rounded-full h-48 w-48 bg-blue-900"></button>
    <div class="border w-full flex text-center">
        <div class="w-1/2 flex flex-col">
            <div>Click Upgrades</div>
            <Button text="+1 - {1 * upgradeClickCost}" fn={() => upgradeClickingPower(1)}/>
            <Button text="+5 - {5 * upgradeClickCost}" fn={() => upgradeClickingPower(5)}/>
        </div>
        <div class="w-1/2 flex flex-col">
            <div>Passive Upgrades</div>
            <Button text="+1 - {1 * upgradePassiveCost}" fn={() => upgradePassiveIncome(1)}/>
        </div>
    </div>


</div>
