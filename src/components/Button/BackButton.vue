<template>
    <a href="/" class="back-button">
      <span class="icon">&larr;</span>
      <span class="text">Back</span>
    </a>
</template>

<style scoped>
.back-button {
    display: inline-block;
    background-color: white; /* White background */
    border-radius: 20px; /* Rounded edges */
    color: #1B57DB; /* Blue text */
    margin: 15px;
    position: fixed;
    z-index: 6;
    padding: 10px 20px;
    text-decoration: none;
    transition: background-color 0.3s ease;
}

/* Button Hover Style */
.button:hover {
background-color: #E8E8E8; /* Lighter gray background */
}

.icon {
font-size: 20px;
margin-right: 10px;
}

.text {
font-size: 18px;
}
</style>
  