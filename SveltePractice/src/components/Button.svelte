<script>
    export let style = 'primary';
    export let type = 'button';
    export let disabled = false;
</script>

<button {type} {disabled} class={style}>
    <slot></slot>
</button>

<style>
    button{
        color:#fff;
        border: 0;
        border-radius: 8px;
        width: 100px;
        height: 40px;
        cursor: pointer;
        position: absolute;
        margin-top: 4px;
        right: 125px;
    }

    .primary{
        background-color: #202142;
    }

    button:hover{
        transform: scale(0.98);
        opacity: 0.9;
    }


    button:disabled{
        background-color: #CCCCCC;
        color:#333;
        cursor: auto;
    }

</style>