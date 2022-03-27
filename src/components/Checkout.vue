<template>
  <div class="shopping-cart-page">
    <div class="hero-banner">
      <div class="text">
        <h2 class="text-1">Shopping Cart</h2>
      </div>
    </div>
    <section class="main-catalog page">
      <div class="catalog-body">
        <div class="catalog-header">
          <h2>All Selected Lessons</h2>
        </div>
        <div class="lessons-catalog">
          <div v-for="(lesson, index) in cart" class="lesson-card">
            <img v-bind:src="`images/${lesson.image}`" alt="">
            <div class="lesson-info">
              <div class="lesson-info-top">
                <div class="lesson-topic-and-price">
                  <span class="lesson-topic">
                    {{ lesson.topic }}
                  </span>
                  <span class="lesson-price">
                    ${{ lesson.price }}
                  </span>
                </div>
                <div class="lesson-location">
                  {{ lesson.location }}
                </div>
              </div>
              <div class="lesson-info-bottom">
                <div class="stars">
                  <svg v-for="star in lesson.stars" class="star-filled" width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M18.2892 7.64918C18.2368 7.4949 18.1404 7.35934 18.0119 7.25923C17.8833 7.15912 17.7283 7.09884 17.5659 7.08585L12.815 6.70835L10.7592 2.15751C10.6937 2.01094 10.5872 1.88645 10.4526 1.79906C10.3179 1.71167 10.1608 1.66513 10.0003 1.66504C9.83978 1.66495 9.68266 1.71132 9.5479 1.79856C9.41314 1.8858 9.30651 2.01018 9.24088 2.15668L7.18504 6.70835L2.43421 7.08585C2.27459 7.09849 2.12199 7.15685 1.99467 7.25395C1.86735 7.35106 1.7707 7.48278 1.71629 7.63337C1.66187 7.78396 1.65199 7.94704 1.68783 8.1031C1.72367 8.25916 1.80371 8.40159 1.91838 8.51335L5.42921 11.9358L4.18754 17.3125C4.14984 17.4753 4.16192 17.6456 4.22223 17.8014C4.28253 17.9572 4.38826 18.0913 4.52571 18.1862C4.66316 18.2812 4.82597 18.3326 4.99303 18.3339C5.16008 18.3352 5.32366 18.2862 5.46254 18.1933L10 15.1683L14.5375 18.1933C14.6795 18.2876 14.8469 18.3361 15.0172 18.3324C15.1876 18.3286 15.3527 18.2728 15.4904 18.1725C15.6281 18.0721 15.7317 17.9319 15.7873 17.7709C15.843 17.6099 15.848 17.4357 15.8017 17.2717L14.2775 11.9383L18.0575 8.53668C18.305 8.31335 18.3959 7.96501 18.2892 7.64918Z" fill="#FFA113"/>
                  </svg>
                  <svg v-for="star in 5-lesson.stars" class="star-outlined" width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M5.42998 11.9358L4.18831 17.3125C4.14987 17.4753 4.16141 17.6459 4.22143 17.8021C4.28146 17.9582 4.38718 18.0926 4.52479 18.1878C4.6624 18.2829 4.82549 18.3343 4.99278 18.3353C5.16006 18.3363 5.32375 18.2868 5.46248 18.1933L9.99998 15.1683L14.5375 18.1933C14.6794 18.2876 14.8468 18.3361 15.0172 18.3324C15.1875 18.3286 15.3526 18.2728 15.4903 18.1724C15.628 18.0721 15.7316 17.9319 15.7873 17.7709C15.8429 17.6098 15.848 17.4356 15.8016 17.2717L14.2775 11.9383L18.0575 8.53666C18.1785 8.42765 18.265 8.28554 18.3062 8.12792C18.3473 7.97029 18.3414 7.80406 18.2891 7.64978C18.2367 7.49549 18.1404 7.35993 18.0118 7.25985C17.8833 7.15976 17.7282 7.09955 17.5658 7.08666L12.815 6.70833L10.7591 2.15749C10.6936 2.01095 10.587 1.88652 10.4523 1.79921C10.3176 1.7119 10.1605 1.66544 9.99998 1.66544C9.83945 1.66544 9.68235 1.7119 9.54764 1.79921C9.41293 1.88652 9.30637 2.01095 9.24081 2.15749L7.18498 6.70833L2.43415 7.08583C2.27453 7.09847 2.12193 7.15683 1.99461 7.25393C1.86729 7.35104 1.77064 7.48276 1.71623 7.63335C1.66181 7.78394 1.65193 7.94702 1.68777 8.10308C1.72361 8.25914 1.80365 8.40157 1.91831 8.51333L5.42998 11.9358V11.9358ZM7.80748 8.33083C7.95623 8.31911 8.09908 8.26759 8.22107 8.18167C8.34305 8.09575 8.43968 7.9786 8.50081 7.84249L9.99998 4.52499L11.4991 7.84249C11.5603 7.9786 11.6569 8.09575 11.7789 8.18167C11.9009 8.26759 12.0437 8.31911 12.1925 8.33083L15.5025 8.59333L12.7766 11.0467C12.54 11.26 12.4458 11.5883 12.5325 11.895L13.5766 15.5492L10.4633 13.4733C10.3267 13.3816 10.1658 13.3326 10.0012 13.3326C9.83665 13.3326 9.6758 13.3816 9.53915 13.4733L6.28581 15.6425L7.16081 11.8542C7.1929 11.7148 7.18859 11.5696 7.14831 11.4324C7.10803 11.2952 7.03313 11.1707 6.93081 11.0708L4.39915 8.60249L7.80748 8.33083V8.33083Z" fill="#FFA113"/>
                  </svg>
                </div>
                <button class="primary-btn remove-btn" v-on:click="removeFromCart(index)">
                  <span>Remove from Cart</span> <span>-</span>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="checkout-box page">
      <div class="inner">
        <div v-if="orderLoading" class="loader"></div>
        <h2>Checkout</h2>
        <form>
          <label v-bind:class="{ 'error-input': !nameValid }" for="name">
            Name
            <input type="text" v-model.trim="name" name="name" id="name">
            <span class="come-up">
              Name must contain only letters
            </span>
          </label>
          <label  v-bind:class="{ 'error-input': !phoneNumberValid }" for="name">
            Phone
            <input type="number" v-model.number="phone" name="phone" id="phone">
            <span class="come-up">
              Phone Number must contain only numbers
            </span>
          </label>
          <button v-bind:disabled="!(nameValid && phoneNumberValid)" type="button" class="primary-btn" v-on:click="submitOrdersForAllLessons">
            Checkout
          </button>
        </form>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'CheckoutPage'
}
</script>

<style scoped>

</style>
