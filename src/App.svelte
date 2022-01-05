<script>
  
  import { Router, Route, Link } from "svelte-navigator";
  import PrivateRoute from "./PrivateRoute.svelte";
  import { user } from "./stores";
  import Login from "./Login.svelte";
  import Home from "./components/pages/Home.svelte"
  import About from "./components/pages/About.svelte"
  import Profile from "./components/pages/Profile.svelte";

  function handleLogout() {
    $user = null;
  }

</script>
<Router>
  <header class="p-2">
    <h1>Menu</h1>
    <nav>
      <Link to="/">Home</Link>
      <Link to="about">About</Link>
      <Link to="profile">Profile</Link>
    </nav>
  </header>

  <main>
    <Route path="login" component="{Login}" />
    <Route path="/" component="{Home}" />
    <Route path="about" component="{About}" />
    <PrivateRoute path="profile" let:location let:registerFocus>
      <Profile />
    </PrivateRoute>
  </main>
</Router>