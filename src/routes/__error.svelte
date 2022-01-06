<script context="module">
   export function load({ error }) {
      return {
         props: { message: error.message }
      };
   }
</script>

<script>
   export let message
</script>

<div class="error">
   <h2>Ups!</h2>
   <p>{message}</p>
   <a href="/">Redirect to home page</a>
</div>

<style>
   .error {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
   }
</style>