<script>
    import { user } from "../../stores";
    import { useFocus } from "svelte-navigator";
    
	const registerFocus = useFocus();
    function handleLogout() {
        $user = null;
    }
</script>

<h3 use:registerFocus>Welcome {$user.username}</h3>
<button on:click={handleLogout}>Logout</button>