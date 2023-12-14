<script>
import { ref } from 'vue'

export default {
    setup() {
        return {
            showSocialMedia: ref(false),
        }
    }
}
</script>


<template>
    <div class="share_button" @click="showSocialMedia = !showSocialMedia">
      Share
    </div>
    
    <div v-if="showSocialMedia">
        <ul>
            <li>Facbook</li>
            <li>Twitter</li>
            <li>Copy Link</li>
        </ul>
    </div>
  </template>
  
  <style scoped>
  .share_button {
    cursor: pointer;
  }
  ul {
    list-style-type: none;
    background: rgba(0,0,0,0.5);
    padding-left: 0;
  }
  li {
    color: #fff;
    cursor: pointer;
    padding: 10px;
  }
  li:hover {
    background: red;
  }

  .item {
    margin-top: 2rem;
    display: flex;
    position: relative;
  }
  
  .details {
    flex: 1;
    margin-left: 1rem;
  }
  
  i {
    display: flex;
    place-items: center;
    place-content: center;
    width: 32px;
    height: 32px;
    color: var(--color-text);
  }
  
  h3 {
    font-size: 1.2rem;
    font-weight: 500;
    margin-bottom: 0.4rem;
    color: var(--color-heading);
  }
  
  @media (min-width: 1024px) {
    .item {
      margin-top: 0;
      padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
    }
  
    i {
      top: calc(50% - 25px);
      left: -26px;
      position: absolute;
      border: 1px solid var(--color-border);
      background: var(--color-background);
      border-radius: 8px;
      width: 50px;
      height: 50px;
    }
  
    .item:before {
      content: ' ';
      border-left: 1px solid var(--color-border);
      position: absolute;
      left: 0;
      bottom: calc(50% + 25px);
      height: calc(50% - 25px);
    }
  
    .item:after {
      content: ' ';
      border-left: 1px solid var(--color-border);
      position: absolute;
      left: 0;
      top: calc(50% + 25px);
      height: calc(50% - 25px);
    }
  
    .item:first-of-type:before {
      display: none;
    }
  
    .item:last-of-type:after {
      display: none;
    }
  }
  </style>
  