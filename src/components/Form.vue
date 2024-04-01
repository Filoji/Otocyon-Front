<script setup lang="ts">
</script>

<template>
  <h1>Form basis</h1>
  <form action="http://localhost:3000/user" method="POST">
    <div>
      <label>Username</label><br />
      <input type="text" name="Username" />
    </div>
    <div>
      <label>Mail</label><br />
      <input type="text" name="Mail" />
    </div>
    <div>
      <label>Password</label><br />
      <input type="password" name="Password" />
    </div>
    <button type="submit">Envoyer</button>
  </form>
</template>