<script>
    export let count = 0;
    export let average = 0;
</script>

<div class="feedback-stats">
    <h4 class="feedback-review">{count} Reviews</h4>
    <h4 class="feedback-average">Rating Average: {average}</h4>
</div>

<style>
    .feedback-stats{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>