<script lang="ts">
	import CopyIcon from "@lucide/svelte/icons/copy";
	import { Button, buttonVariants } from "$lib/registry/ui/button/index.js";
	import { Input } from "$lib/registry/ui/input/index.js";
	import { Label } from "$lib/registry/ui/label/index.js";
	import * as Popover from "$lib/registry/ui/popover/index.js";
</script>

<Popover.Root>
	<Popover.Trigger class={buttonVariants({ variant: "secondary" })}>Share</Popover.Trigger>
	<Popover.Content class="w-[520px]" align="end">
		<div class="flex flex-col space-y-2 text-center sm:text-left">
			<h3 class="text-lg font-semibold">Share preset</h3>
			<p class="text-muted-foreground text-sm">
				Anyone who has this link and an OpenAI account will be able to view this.
			</p>
		</div>
		<div class="flex items-center space-x-2 pt-4">
			<div class="grid flex-1 gap-2">
				<Label for="link" class="sr-only">Link</Label>
				<Input
					id="link"
					value="https://platform.openai.com/playground/p/7bbKYQvsVkNmVb8NGcdUOLae?model=text-davinci-003"
					readonly
					class="h-9"
				/>
			</div>
			<Button type="submit" size="sm" class="px-3">
				<span class="sr-only"> Copy </span>
				<CopyIcon />
			</Button>
		</div>
	</Popover.Content>
</Popover.Root>
