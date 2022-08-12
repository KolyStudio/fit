<script>
	let age = '';
	let poids = '';
    let taille = '';
    let genre = 'homme';

    function setHomme(){
        genre = 'homme';
        console.log(genre);
    }

    function setFemme(){
        genre = 'femme';
        console.log(genre);
    }
    

    
</script>
<svelte:head>
    <title>Mon Alimentation</title>
</svelte:head>
<div class="flex flex-col items-center py-2"><img src="icon.png" alt="avocat" class="w-[70px]"/>
<h1 class="font-semibold text-lg">Mon Alimentation</h1></div>
<section class="bg-white m-auto w-[95%] rounded-3xl my-4">
    <h1 class="font-medium text-center text-lg py-2">Informations</h1>
    <div class="flex justify-evenly">
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-grey-400 text-center"><input class="w-[100px] text-center" type=number placeholder="22" bind:value={age}></div>
            <div class="font-medium">Age</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-grey-400 text-center"><input class="w-[100px] text-center" type=number placeholder="170" bind:value={taille}></div>
            <div class="font-medium">Taille</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-grey-400 text-center"><input class="w-[100px] text-center" type=number placeholder="65" bind:value={poids}></div>
            <div class="font-medium">Poids</div>
        </div>

       
    </div>

    {#if genre == 'homme'} 
    <div class="flex justify-evenly space-x-4 py-4">
        <div class="bg-blue-300 px-3 rounded-lg font-medium py-1" on:click={setHomme}>HOMME</div>
        <div class="bg-gray-200 px-3 rounded-lg font-medium py-1" on:click={setFemme}>FEMME</div>
    </div>
    {:else}
    <div class="flex justify-evenly space-x-4 py-4">
        <div class="bg-gray-200 px-3 rounded-lg font-medium py-1" on:click={setHomme}>HOMME</div>
        <div class="bg-purple-300 px-3 rounded-lg font-medium py-1" on:click={setFemme}>FEMME</div>
    </div>
    {/if}
</section>

{#if genre == 'femme'}
<section class="bg-white m-auto w-[95%] rounded-3xl my-4">
    <h1 class="font-medium text-center text-lg py-2">Métabolisme</h1>
    <div class="flex justify-evenly">
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-red-400">{((((9.740 * poids) + (172.9 * (taille/100)) - (4.737 * age) + 667.051)* 1.55)*0.75).toFixed(0)} kcal</div>
            <div class="font-medium">Perte</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-yellow-400">{(((9.740 * poids) + (172.9 * (taille/100)) - (4.737 * age) + 667.051)* 1.55).toFixed(0)} kcal</div>
            <div class="font-medium">Maintien</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-green-400">{((((9.740 * poids) + (172.9 * (taille/100)) - (4.737 * age) + 667.051)* 1.55)*1.25).toFixed(0)} kcal</div>
            <div class="font-medium">Prise</div>
        </div>
    </div>
</section>

<section class="bg-white m-auto w-[95%] rounded-3xl my-4">
    <h1 class="font-medium text-center text-lg py-2">Macronutriments </h1>
    <div class="flex justify-evenly">
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-red-400">{(poids * 1.7).toFixed(0)}g</div>
            <div class="font-medium">Protéines</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-yellow-400">{((0.35 *((((9.740 * poids) + (172.9 * (taille/100)) - (4.737 * age) + 667.051)* 1.55)*0.75))/9).toFixed(0)}g</div>
            <div class="font-medium">Lipides</div>
        </div>
    </div>
</section>
{:else}
<section class="bg-white m-auto w-[95%] rounded-3xl my-4">
    <h1 class="font-medium text-center text-lg py-2">Métabolisme</h1>
    <div class="flex justify-evenly">
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-red-400">{((((13.707 * poids) + (492.3 * (taille/100)) - (6.673 * age) + 77.607)* 1.55)*0.75).toFixed(0)} kcal</div>
            <div class="font-medium">Perte</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-yellow-400">{(((13.707 * poids) + (492.3 * (taille/100)) - (6.673 * age) + 77.607)* 1.55).toFixed(0)} kcal</div>
            <div class="font-medium">Maintien</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-green-400">{((((13.707 * poids) + (492.3 * (taille/100)) - (6.673 * age) + 77.607)* 1.55)*1.25).toFixed(0)} kcal</div>
            <div class="font-medium">Prise</div>
        </div>
    </div>
</section>

<section class="bg-white m-auto w-[95%] rounded-3xl my-4">
    <h1 class="font-medium text-center text-lg py-2">Macronutriments </h1>
    <div class="flex justify-evenly">
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-red-400">{(poids * 1.7).toFixed(0)}g</div>
            <div class="font-medium">Protéines</div>
        </div>
        <div class="flex flex-col items-center">
            <div class="font-medium text-2xl text-yellow-400">{((0.35 *((((13.707 * poids) + (492.3 * (taille/100)) - (6.673 * age) + 77.607)* 1.55)*0.75))/9).toFixed(0)}g</div>
            <div class="font-medium">Lipides</div>
        </div>
    </div>
</section>
{/if}
