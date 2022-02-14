<script context="module">
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

<script>
    export let json;
</script>
<h1>Auth Me response</h1>
<pre>
    <code>
        {JSON.stringify(json, null, 2)}
    </code>
</pre>