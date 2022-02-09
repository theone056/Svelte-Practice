<script>
    import Button from "./Button.svelte";
    import Card from "./Card.svelte";
</script>

<Card>
    <header>
        <h3>How would you rate our service ?</h3>
    </header>
    <form action="">
        <div class="input-group">
            <input type="text" placeholder="Tell us something that keeps you coming back">
            <Button>Send</Button>
        </div>
    </form>
</Card>

<style>
</style>