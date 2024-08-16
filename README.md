<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<link rel="stylesheet" href="style.css">
</head>
<center>
<h1>Hi,Stinsik Ton App</h1>
<button class="Transfer" onclick="transaction()">Transfer Ton</button>
</center>
</html>

<script src="https://unpkg.com/@tonconnect/ui@latest/dist/tonconnect-ui.min.js"></script>
<div id="ton-connect" style="position: fixed; top: 10%; left: 35%;"></div>
<script>
    const tonConnectUI = new TON_CONNECT_UI.TonConnectUI({
        manifestUrl: 'https://raw.githubusercontent.com/Stttnsik1/ton/main/tonconnect-manifest.json',
        buttonRootId: 'ton-connect'
    });

    async function transaction() {
  const transaction = {
    validUntil: Math.round(Date.now() / 1000) + 10,
    messages: [
      {
        address: "UQBQ3GE8djotFZNWqLWz0cgSAE9j37c82Ll3yLqPKZes1goR",
        amount: "10000000"
      }
    ]
  };

  try {
    await tonConnectUI.sendTransaction(transaction);
  } catch (e) {
    console.error(e);
  }
}
</script>
