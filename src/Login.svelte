<script>
    import { useNavigate, useLocation } from "svelte-navigator";
    import { user } from "./stores"
  
    const navigate = useNavigate();
    const location = useLocation();
  
    let username;
    let password;
  
    function handleSubmit() {
      $user = { username, password };
      const from = ($location.state && $location.state.from) || "/";
      navigate(from, { replace: true });
    }
  </script>
  
  <form on:submit={handleSubmit} class="p-2">
    <h3>Login</h3>
    <input
        class="my-2 rounded-md p-1"
        bind:value={username}
        type="text"
        name="username"
        placeholder="Username"
    />
    <br />
    <input
        class="my-2 rounded-md p-1"
        bind:value={password}
        type="password"
        name="password"
        placeholder="Password"
    />
    <br />
    <button class="btn btn-sm btn-primary rounded-md my-2" type="submit">Login</button>
  </form>
  