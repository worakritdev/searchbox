<script context="module">
  /**
   * @type {import('@sveltejs/kit').Load}
   */
  export async function load({ page, fetch, session, context }) {
    const url = `http://localhost:1337/blogs/${page.params.slug}`;
    const res = await fetch(url);

    if (res.ok) {
      return {
        props: {
          article: await res.json(),
        },
      };
    }

    return {
      status: res.status,
      error: new Error(`Could not load ${url}`),
    };
  }
</script>

<script>
  export let article;
</script>

{JSON.stringify(article)}

<style>
</style>
