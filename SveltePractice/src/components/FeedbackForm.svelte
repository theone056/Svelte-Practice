<script>
    import Button from "./Button.svelte";
    import Card from "./Card.svelte";
    import RatingSelect from './RatingSelect.svelte';
    let text = '';
    let disabledButton = true;
    let min = 10;
    let message = '';
    const InputHandler = () =>{
        if(text.trim().length <=min)
        {
            message = `Text must be at least ${min} characters`
            disabledButton = true;
        }
        else{
            message = null;
            disabledButton = false;
        }
    }

</script>

<Card>
    <header>
        <h3>How would you rate your service ?</h3>
    </header>
    <form action="">
        <div class="input-group">
            <RatingSelect/>
            <input type="text" on:input={InputHandler} bind:value={text} placeholder="Tell us something that keeps you coming back">
            <Button disabled={disabledButton} type='submit'>Send</Button>
        </div>
        {#if message}
            <div class="class">
                {message}
            </div>
        {/if}
    </form>
</Card>

<style>
    header{
        text-align: center;
    }
    form{
        text-align: center;
    }
    .input-group{
        text-align: center;
        margin: 0 70px;
    }

    input{
        width: 100%;
        max-width: 600px;
        border: 1px solid #C3C3E4;
        border-radius: 10px;
        padding: 15px;
    }
</style>