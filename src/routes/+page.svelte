<script>
    import { base } from '$app/paths'
</script>

<div class="app">
    <main>
        <section>
            <h1>preload triggered on hover</h1>
            <div data-sveltekit-preload-data="hover">
                <a href="{base}/1">1. PARENT: preload-data, SELF: none</a>
            </div>
            <div data-sveltekit-preload-data="hover">
                <a href="{base}/2" data-sveltekit-preload-code="hover">2. PARENT: preload-data, SELF: preload-code</a>
            </div>
            <div data-sveltekit-preload-code="hover">
                <a href="{base}/3">3. PARENT: preload-code, SELF: none</a>
            </div>
            <div data-sveltekit-preload-code="hover">
                <a href="{base}/4" data-sveltekit-preload-data="hover">4. PARENT: preload-code, SELF: preload-data</a>
            </div>
            <div>
                <a href="{base}/5" data-sveltekit-preload-data="hover">5. PARENT: none, SELF: preload-data</a>
            </div>
            <div>
                <a href="{base}/6" data-sveltekit-preload-code="hover">6. PARENT: none, SELF: preload-code</a>
            </div>
        </section>
    </main>
</div>

<style>
    section {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        font-family: monospace;
    }

    section div {
        margin: 1rem 0;
    }

    a {
        display: block;
        text-decoration: none;
        font-size: 16px;
        border: 1px solid #ddd;
        padding: 1rem;
    }
</style>
