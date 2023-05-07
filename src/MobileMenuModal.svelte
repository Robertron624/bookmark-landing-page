<script>
    export let showModal;

    let dialog;

    $: if(dialog && showModal) {
        dialog.showModal();
    }
</script>

<dialog
	bind:this={dialog}
	on:close={() => (showModal = false)}
	on:click|self={() => dialog.close()}
    on:keyup={() => dialog.close()}
>
	<div on:keyup={() => console.log()} on:click|stopPropagation>
		<slot name="header" />
		<slot name="menu-content"/>
		<!-- svelte-ignore a11y-autofocus -->
		<!-- <button autofocus on:click={() => dialog.close()}>close modal</button> -->
	</div>
</dialog>

<style lang="scss">

    @import './vars.scss';

	dialog {
		max-width: 32em;
		border-radius: 0.2em;
		border: none;
		padding: 0;
        width: 100vw;
        height: 100vh;
        background-color: $very-dark-blue;
        opacity: .7;
	}
	dialog::backdrop {
		background: rgba(0, 0, 0, 0.3);
	}
	dialog > div {
		padding: 1em;
	}
	dialog[open] {
		animation: zoom 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
	}
	@keyframes zoom {
		from {
			transform: scale(0.95);
		}
		to {
			transform: scale(1);
		}
	}
	dialog[open]::backdrop {
		animation: fade 0.2s ease-out;
	}
	@keyframes fade {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
</style>