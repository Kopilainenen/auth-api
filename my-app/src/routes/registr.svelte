<script>
    import {goto} from "@sapper/app.mjs";
    let name = '', surname = '', email = '', password = ''
    const submit = async () => {
        await fetch('http://localhost:8000/api/registr', {
            method: 'POST',
            headers: {'Content-Type': 'application/json'},
            body: JSON.stringify({
                name,
                surname,
                email,
                password
            })
        });
        await goto('/login');
    }
</script>

<form class="form-registr" on:submit|preventDefault={submit}>
    <h1 class="h3 mb-3 fw-normal">Please register</h1>
    <h1 class="h3 mb-3 fw-normal"> Registration</h1>


    <input bind:value={name} class="form-control" placeholder="Name" required>
    <input bind:value={surname} class="form-control" placeholder="Surname" required>

    <input bind:value={email} type="email" class="form-control" placeholder="Email" required>

    <input bind:value={password} type="password" class="form-control" placeholder="Password" required>

    <button class="w-100 btn btn-lg btn-primary" type="submit">Submit</button>
</form>

