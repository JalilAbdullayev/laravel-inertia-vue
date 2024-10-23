<template>
    <Head :title="` | ${$page.component}`">
        <meta head-key="description" name="description" content="This is homepage."/>
    </Head>
    <h1>
        {{ $page.props.user }}
    </h1>
</template>
