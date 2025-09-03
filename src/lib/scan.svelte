<script>
    const shapes = ["s", "t", "x", "c", "h"];
    const colors = ["1", "2", "3", "4"];

    // 3x3 grid represented as 1D array
    let grid = Array(9).fill("00");

    let selectedShape = "s";
    let selectedColor = "1";

    function selectCell(index) {
        grid[index] = selectedShape + selectedColor;
    }

    function resetCell(index) {
        grid[index] = "00";
    }

    $: tagCode = grid.join("");

    function color(c) {
        return { "1": "black", "2": "cyan", "3": "magenta", "4": "yellow" }[c];
    }
</script>

<div class="fcy fse fdr sf-nav">
    <!-- Left box for upload/scanner (not implemented yet) -->
    <div class="bigboxb">Upload / Scanner (future)</div>

    <!-- Manual grid -->
    <div class="fsb fdc bigbox">
        <!-- Controls -->
        <div class="controls fsb fdc">
            <label>
                Shape:
                <select bind:value={selectedShape}>
                    {#each shapes as s}
                        <option value={s}>{s}</option>
                    {/each}
                </select>
            </label>

            <label>
                Color:
                <select bind:value={selectedColor}>
                    {#each colors as c}
                        <option value={c}>{c}</option>
                    {/each}
                </select>
            </label>
        </div>

        <!-- Grid -->
        <div class="grid-container">
            {#each grid as cell, index}
                <!-- svelte-ignore a11y_click_events_have_key_events -->
                <!-- svelte-ignore a11y_no_static_element_interactions -->
                <div
                    class="box"
                    on:click={() => selectCell(index)}
                    on:dblclick={() => resetCell(index)}
                >
                    {#if cell !== "00"}
                        <div
                            class="shape"
                            style="background-color: {color(cell[1])}"
                        >
                            {cell[0]}
                        </div>
                    {/if}
                </div>
            {/each}
        </div>

        <!-- Debug / output -->
        <p>Tag Code: {tagCode}</p>
    </div>
</div>

<style>
    .bigbox,
    .bigboxb {
        width: 330px;
        height: 330px;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        gap: 10px;
    }

    .bigboxb {
        border: 2px dashed black;
        align-items: center;
        justify-content: center;
        text-align: center;
    }

    .controls label {
        margin-bottom: 10px;
    }

    .grid-container {
        display: grid;
        grid-template-columns: repeat(3, 100px);
        gap: 5px;
    }

    .box {
        width: 100px;
        height: 100px;
        border: 2px dashed black;
        border-radius: 10px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .shape {
        width: 80%;
        height: 80%;
        display: flex;
        align-items: center;
        justify-content: center;
        font-weight: bold;
        border-radius: 5px;
    }
</style>
