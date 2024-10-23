<template>
  <div>
    <h1 class="title">
      <p class="p-4 bg-green-200">
        {{ $page.props.flash.greet }}
      </p>
      Welcome back {{ $page.props.auth.user.name }}
    </h1>
  </div>
</template>
