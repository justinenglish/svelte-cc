<script>
  import cardBack from '../assets/bg-card-back.png'
  import cardFront from '../assets/bg-card-front.png'

  export let name;
  export let ccnumber;
  export let expMonth;
  export let expYear;
  export let cvc;
</script>

<div class="cc-card-container">
  <div class="cc-card card-back">
    <img src={cardBack} alt="Credit card back" />
    <p>{cvc ? cvc : '000'}</p>
  </div>
  <div class="cc-card card-front">
    <img src={cardFront} alt="Credit card front" />
    <p>{ccnumber ? ccnumber.match(/.{1,4}/g).join(' ') : '0000 0000 0000 0000'}</p>
    <div class="name-ccv">
      <p>{name ? name : 'Jane Appleseed'}</p>
      <p>{expMonth && expYear ? `${expMonth}/${expYear}` : '00/00'}</p>
    </div>
  </div>
</div>

<style>
  .cc-card-container {
    display: flex;
    flex-direction: column;
    max-width: 375px;
    margin-left: auto;
    margin-right: auto;
  }
  .cc-card {
    position: relative;
    display: flex;
    letter-spacing: 0.1em;
  }
  .cc-card img {
    width: 285px;
  }
  .card-back p {
    position: absolute;
    z-index: 9;
    bottom: 57px;
    right: 36px;
    font-size: 10px;
    font-weight: 400;
  }
  .card-back {
    justify-content: flex-end;
  }
  .card-front {
    position: relative;
    z-index: 1;
    top: -68px;
  }
  .card-front::before {
    content: '';
    position: absolute;
    top: 16px;
    left: 22px;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background: white;
    z-index: 2;
  }
  .card-front::after {
    content: '';
    position: absolute;
    top: 22px;
    left: 64px;
    width: 14px;
    height: 14px;
    border-radius: 50%;
    border: 1px solid white;
    background: transparent;
    z-index: 2;
  }
  .card-front p {
    padding-left: 24px;
    padding-right: 2px;
  }
  .card-front .name-ccv {
    display: flex;
    justify-content: space-between;
    width: 265px;
    position: absolute;
    bottom: 0;
    font-size: 12px;
    font-weight: 400;
    text-transform: uppercase;
    padding-bottom: 8px;
  }
  .card-front > p {
    position: absolute;
    bottom: 40px;
    font-size: 18px;
  }
</style>