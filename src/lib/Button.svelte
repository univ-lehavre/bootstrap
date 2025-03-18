<script lang="ts">
	interface Props {
		label: string;
		variant:
			| 'primary'
			| 'secondary'
			| 'success'
			| 'danger'
			| 'warning'
			| 'info'
			| 'light'
			| 'dark'
			| 'link';
		icon?: string;
		outline?: boolean;
		disabled?: boolean;
		size?: 'large' | 'small' | 'standard';
		onclick?: () => void;
	}

	const { label, onclick, variant, icon, outline, disabled, size }: Props = $props();

	const btnClass = $derived(`btn${outline ? '-outline' : ''}-${variant}`);
	const btnSize = $derived(size === 'large' ? 'btn-lg' : size === 'small' ? 'btn-sm' : '');
</script>

{#snippet content()}
	{#if icon}
		<i class="bi bi-{icon} me-1"></i>
	{/if}
	{label}
{/snippet}

<button {onclick} type="button" class="btn {btnClass} {btnSize}" {disabled}>
	{@render content()}
</button>
