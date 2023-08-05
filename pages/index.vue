<script setup lang="ts">
const { signIn, signOut, session, status, cookies } = useAuth()

const res = ref() 

async function signInWithoutRedirect() {
  res.value = await signIn('credentials', { redirect: false })
  // signIn always void instead of returning a Promise<{
  //     error: string | undefined
  //     status: number
  //     ok: boolean
  //     url: string | null
  // }> 
  // when redirect is false

}
</script>

<template>
  <div>
    <div>
      <button @click="signIn(`credentials`)">
        Sign In
      </button>
      <button @click="signInWithoutRedirect">
        Sign In Without Redirect
      </button>
      <button @click="signOut()">
        Sign Out
      </button>
    </div>
    <div>
      <pre>{{ status }}</pre>
      <pre>{{ session?.user }}</pre>
      <pre>{{ cookies }}</pre>
      <pre>{{ typeof res }}</pre>
    </div>
  </div>
</template>