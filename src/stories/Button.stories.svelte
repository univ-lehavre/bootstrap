<script module>
	import { defineMeta } from '@storybook/addon-svelte-csf';
	import Button from '$lib/Button.svelte';
	import { fn } from '@storybook/test';

	// More on how to set up stories at: https://storybook.js.org/docs/writing-stories
	const { Story } = defineMeta({
		title: 'Example/Button',
		component: Button,
		tags: ['autodocs'],
		argTypes: {
			label: { control: 'text' },
			variant: {
				control: { type: 'select' },
				options: [
					'primary',
					'secondary',
					'success',
					'danger',
					'warning',
					'info',
					'light',
					'dark',
					'link'
				]
			},
			icon: { control: 'text' },
			outline: { control: 'boolean' },
			disabled: { control: 'boolean' },
			size: {
				control: { type: 'radio' },
				options: ['large', 'standard', 'small']
			}
		},
		args: {
			label: 'Button',
			variant: 'primary',
			icon: 'arrow-up-circle-fill',
			outline: false,
			disabled: false,
			size: 'standard',
			onclick: fn()
		}
	});
</script>

<!-- More on writing stories with args: https://storybook.js.org/docs/writing-stories/args -->
<Story name="Success" args={{ variant: 'success', label: 'Success' }} />

<Story name="Large" args={{ size: 'large' }} />

<Story name="Small" args={{ size: 'small' }} />
