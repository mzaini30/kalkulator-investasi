<script>
  let modal;
  let bitcoin = 0;
  let ethereum = 0;
  let smartContract = 0;
  let defi = 0;
  let emas = 0;
  let sahamAmerika = 0;

  if (localStorage.modal) {
    modal = localStorage.modal;
  }

  function tampilan(x) {
    let angka = ~~x;
    // @ts-ignore
    angka = angka.toLocaleString("id-ID");
    return angka;
  }

  $: {
    if (modal) {
      localStorage.modal = modal;
      bitcoin = tampilan(modal * 0.18);
      ethereum = tampilan(modal * 0.18);
      smartContract = tampilan(modal * 0.12);
      defi = tampilan(modal * 0.12);
      emas = tampilan(modal * 0.2);
      sahamAmerika = tampilan(modal * 0.2);
    }
  }
</script>

<div class="wadah">
  <div class="card">
    <label for="">Uang yang Akan Diinvestasikan</label>
    <input type="tel" bind:value={modal} placeholder="100000" />
  </div>

  <div class="card">
    <label for="">Bitcoin (18%)</label>
    <input type="text" value={bitcoin} readonly />
    <label for="">Ethereum (18%)</label>
    <input type="text" value={ethereum} readonly />
    <label for="">Smart Contract (12%)</label>
    <input type="text" value={smartContract} readonly />
    <label for="">DeFi (12%)</label>
    <input type="text" value={defi} readonly />
  </div>

  <div class="card">
    <label for="">Emas (20%)</label>
    <input type="text" value={emas} readonly />
    <label for="">Saham Amerika (20%)</label>
    <input type="text" value={sahamAmerika} readonly />
  </div>

  <div class="tengah">
    <a href="https://zenzen.web.id/komunitas" target="_blank">Join Komunitas</a>
  </div>
</div>

<style>
  .tengah {
    display: flex;
    justify-content: center;
  }
  a {
    background: var(--green-500);
    color: #fff;
    padding: 10px;
    border-radius: 5px;
  }
  .wadah {
    padding: 10px;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  .card {
    padding: 10px;
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  label,
  input {
    display: block;
    width: 100%;
  }
  input {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    outline: none;
  }
</style>
