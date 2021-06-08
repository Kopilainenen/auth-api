<script>
    import {goto} from "@sapper/app.mjs";
    password = ''
    const submit = async () => {
        await fetch('http://localhost:8000/api/restore_password', {
            method: 'POST',
            headers: {'Content-Type': 'application/json'},
            credentials: 'include',
            body: JSON.stringify({
               password
                
            })
        });
        await goto('/');
    }
</script>

<form on:submit|preventDefault={submit}>
    <h1 class="h3 mb-3 fw-normal">Change password</h1>
    <h1 class="h3 mb-3 fw-normal">Restore password</h1>

   
<input bind:value={password} type="password" class="form-control" placeholder="Password" required>


    <button class="w-100 btn btn-lg btn-primary" type="submit">Submit</button>
</form>