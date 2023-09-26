<script>
  export let name;
  export let ccnumber;
  export let expMonth;
  export let expYear;
  export let cvc;
</script>

<form class="cc-form">
  <label>
    Cardholder Name
    <input bind:value={name} maxlength="18" placeholder="e.g. Jane Appleseed">
  </label>
  <label>
    Card Number
    <input bind:value={ccnumber} maxlength="16" placeholder="e.g. 1234 5678 9123 0000">
  </label>
  <div>
    <div class="expiration">
      <label for="expiration">
        EXP. DATE (MM/YY)
      </label>
      <div>
        <input name="expiration" maxlength="2" id="expMonth" bind:value={expMonth} placeholder="MM">
        <input name="expiration" maxlength="2" id="expYear" bind:value={expYear} placeholder="YY">
      </div>
    </div>
    <label>
      CVC
      <input bind:value={cvc} maxlength="3" placeholder="e.g. 123">
    </label>
  </div>
</form>

<style>
  .cc-form {
    max-width: 600px;
    margin-top: 90px;
    padding-left: 32px;
    padding-right: 32px;
    margin-left: auto;
    margin-right: auto;
  }
  .cc-form > div {
    display: flex;
    width: 100%;
    grid-gap: 12px;
    margin-top: 24px;
  }
  .cc-form .expiration > div {
    display: flex;
    flex-direction: row;
    grid-gap: 8px;
  }
  .cc-form > div > label {
    width: 50%;
  }
  .cc-form .expiration > div input {
    width: 100%;
  }
  label {
    font-size: 13px;
    font-weight: 600;
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    text-align: left;
    color: purple;
    letter-spacing: 0.1em;
  }
  label:not(:first-of-type) {
    margin-top: 24px;
  }
  input {
    margin-top: 8px;
    font-size: 22px;
    padding: 12px 16px;
    color: #666;
    border-radius: 8px;
    border: 1px solid #666;
  }
  input::placeholder {
    color: #ccc;
  }
</style>