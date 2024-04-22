<script setup>

</script>


<script>
async function login(login, password)
{
    var loggedin = false;
    if(login.contains('"'))
    {

    }

    fetch().then(response => response.json()).then(data = data.json)

    if(loggedin == false)
    {

    }
    else
    {
        //send request to node to log user in, incase of success, saves username in the local storage and redirects to user overview page

    }
}
</script>
<template>
    <div>
        <div>
            <a>Login</a>
            <input type="text">
        </div>

        <div>
            <a>Password</a>
            <input type="text">
        </div>

        <button></button>
    </div>
</template>