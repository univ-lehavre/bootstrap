<script lang="ts">
	interface Props {
		label: string;
		variant: 'primary' | 'secondary' | 'success' | 'danger' | 'warning' | 'info' | 'light' | 'dark'| 'link';
		icon?: string;
		outline?: boolean;
		disabled?: boolean;
		size: "large"|"small"|"standard";
		onclick?: () => void;
	}

	const { label, onclick, variant, icon, outline, disabled, size }: Props = $props();
</script>

<button {onclick} type="button" class="btn btn{outline?"-outline":""}-{variant} {size === "large"? "btn-lg" : size === "small" ? "btn-sm" : ""}" {disabled}>
	{#if icon}
		<i class="bi bi-{icon} me-1"></i>
	{/if}
	{label}
</button>
