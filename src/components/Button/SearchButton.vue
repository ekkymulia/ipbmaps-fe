<template>
    <a href="#" class="search-button" @click.prevent="handleSearch">
      <span class="search-button-text">Search</span>
      <span class="search-button-icon"><i class="fa fa-search"></i></span>
    </a>
  </template>
  
  <style>
  .search-button {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #1B57DB;
    color: white;
    border-radius: 20px;
    padding: 10px 20px;
    text-decoration: none;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .search-button:hover {
    background-color: #0056b3;
  }
  
  .search-button:active {
    background-color: #073b85;
  }
  
  .search-button-text {
    margin-right: 10px;
  }
  
  .search-button-icon {
    font-size: 18px;
  }
  </style>
  
  <script>
  export default {
    methods: {
      handleSearch() {
        console.log('Perform search');
        // Redirect to search page
        window.location.href = '/search';
      },
    },
  };
  </script>
  