<script>
    import GithubBar from '$lib/components/GithubBar.svelte';
    import Copy from '$lib/components/icons/Copy.svelte';
    import Box from '$lib/components/Box.svelte';
    import Coffee from '$lib/components/icons/Coffee.svelte';
    import Code from '$lib/components/icons/Code.svelte';
    import Alert from '$lib/components/icons/Alert.svelte';
    export let data;

    function copy(id) {
        let text = document.getElementById(id);
        navigator.clipboard.writeText(text.value);
    }
</script>

<div class="flex flex-col w-full items-center">
    <div class="relative py-36 w-full flex justify-center">
        <img
            src="/banner.png"
            class="opacity-5 absolute w-full align-top h-full top-0 bottom-0 object-cover"
            alt="Viking city"
            style="pointer-events: none"
        />
        <div class="fade-out" style="pointer-events: none"></div>
        <div class="container px-4">
            <h1 class="header text-8xl mb-4">Njord</h1>
            <h2 class="text-2xl">
                Lightweight, Extensible ORM and Query Builder for Rust
            </h2>
            <GithubBar repo={data.repo}></GithubBar>
            <div class="flex md:flex-row md:gap-x-6 gap-5 items-center flex-wrap">
                <img class="md:h-10 md:w-24 h-10 w-18" src="/sqlite.png" alt="SQLite logo" />
                <img class="md:h-10 md:w-24 h-10 w-18" src="/mysql.png" alt="MySQL logo" />
                <img class="md:h-10 md:w-44 h-10 w-36" src="/psql.png" alt="PostgreSQL logo" />
                <img class="md:h-10 md:w-32 h-10 w-18" src="/maria.png" alt="MariaDb logo" />
                <img class="md:h-4 md:w-32 h-2 w-18" src="/oracle.png" alt="Oracle logo" />
                <img class="md:h-10 md:w-10 h-10 w-18" src="/mssql.png" alt="MSSQL logo" />
            </div>
        </div>
    </div>
    <div class="container px-4 pb-16">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:grid-cols-3 mb-16">
            <Box
                text="Join our community on Discord! Connect with our developers, seek help on usage, share your ideas, and stay updated on the latest developments on the project. Your input fuels Njord's growth."
            >
                <Coffee></Coffee>
            </Box>
            <Box
                text="Njord is a FOSS project, and we welcome your contributions. Whether it's bug fixes, new features, documentation, or other improvements, your help is valuable. Check out our GitHub repository for more information."
            >
                <Code></Code>
            </Box>
            <Box
                text="Njord is currently in alpha. While it's shaping up to be a powerful ORM and Query Builder, exercise caution in production environments. Your feedback is invaluable as we work towards stability. Stay tuned for updates and improvements!"
            >
                <Alert></Alert>
            </Box>
        </div>
    </div>
</div>

<style>
    .fade-out {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100px; /* Adjust the height of the fade-out effect as needed */
        background: linear-gradient(to bottom, rgba(255, 255, 255, 0), #18181b);
    }
</style>
