<script>
    let temperature = '';
    let timer = '';
    let message = '';

    function start() {
        if (temperature && timer) {
            message = `Oven started at ${temperature} degrees for ${timer} minutes.`;
        } else {
            message = "Please set the temperature and timer before starting the oven.";
        }
    }
</script>

<div id="oven">
    <input type="number" bind:value={temperature} min="0" max="550" step="10" placeholder="Temperature">
    <input type="number" bind:value={timer} min="0" max="120" step="1" placeholder="Timer">
    <button class="top" on:click={start}>Start</button>
    <button on:click={() => { temperature = ''; timer = ''; message = ''; }}>Reset</button>
    <p>{message}</p>
</div>

<style>
    #oven {
        width: 500px;
        padding: 20px;
        border: 1px solid #000;
        background-color: #240707;
        border-radius: 10px;
        margin-left: auto;
        margin-right: auto;
    }

    #oven input {
        width: 100%;
        margin-bottom: 10px;
        color: #ffffff;
        background: #000000;
    }

    #oven button {
        width: 50%;
        margin-left: 125px;
        background: #000000;
        color: #ff0000;
        border-radius: 10px;
    }

    .top {
        margin-bottom: 10px;

    }
</style>