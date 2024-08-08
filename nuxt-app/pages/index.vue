<template>
  <div>Welcome to the home page!</div>
</template>

<script setup>
useSeoMeta({
  title: "Gonzalo Encinar",
  description:
    "Gonzalo Encinar is a software expert with over 4 years of professional experience in the industry (Quality Asssurance, Release Management, NoCode solutions & AI Tools and Software Development)",
  ogTitle: "Gonzalo Encinar",
  ogDescription:
    "Gonzalo Encinar is a software expert with over 4 years of professional experience in the industry (Quality Asssurance, Release Management, NoCode solutions & AI Tools and Software Development)",
  ogImage: "[og:image]",
  ogUrl: "[og:url]",
  twitterTitle: "Gonzalo Encinar",
  twitterDescription:
    "Gonzalo Encinar is a software expert with over 4 years of professional experience in the industry (Quality Asssurance, Release Management, NoCode solutions & AI Tools and Software Development)",
  twitterImage: "[twitter:image]",
  twitterCard: "summary",
});

useHead({
  htmlAttrs: {
    lang: "en",
  },
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: "/favicon.png",
    },
  ],
});
</script>
