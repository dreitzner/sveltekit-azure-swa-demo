<script context="module" lang="ts">
    export async function load({fetch}) {
        const response = await fetch('/.auth/me');

		return {
			status: response.status,
			props: {
				json: response.ok && (await response.json())
			}
		};
    }
</script>

<script lang="ts">
    export let json: any;
</script>
<h1>Auth Me response</h1>
<pre>
    <code>
        {JSON.stringify(json, null, 2)}
    </code>
</pre>