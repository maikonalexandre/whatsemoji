<script>
  import "../app.css";
  import Navbar from "../components/Navbar.svelte";
  import Search from "../components/Search.svelte";
  import Transiction from "../components/Transiction.svelte";
  import { GithubLogo } from "phosphor-svelte";
  import { Toaster } from "svelte-sonner";
  import { page } from "$app/stores";
</script>

<svelte:head>
  <title>Whatsemogi</title>
  <meta
    name="Emogis from whatsapp"
    content="A library with open source emogis from whatsapp"
  />
  <!-- <meta
    name="google-site-verification"
    content="EOVyvjb1LaJ29mw3mxRQhL5wvI7HjeDxxB4-7vV6NvE"
  /> -->
</svelte:head>

<div class="w-screen h-screen flex justify-center py-10 bg-container">
  <div
    class="bg-background max-w-3xl rounded-t-2xl rounded-bl-2xl rounded-br-lg text-neutral-400 flex flex-col"
  >
    <Navbar />
    <Search />
    <div class="overflow-y-auto flex-1">
      <Transiction pathname={$page.url.pathname}>
        <div class="p-4">
          <slot />
        </div>
      </Transiction>
      <Toaster
        position="top-right"
        toastOptions={{
          style: `background-color: #38424A;
			 color: #fff; 
			 border-radius: 1rem; border: 1px solid #262626;`,
        }}
      />
    </div>
  </div>
  <div class="absolute right-8 bottom-8">
    <a
      class="text-lg flex items-center gap-2 text-neutral-600 hover:text-sky-600"
      href="https://github.com/maikonalexandre/whatsemogi"
    >
      View repo <GithubLogo />
    </a>
  </div>
</div>
