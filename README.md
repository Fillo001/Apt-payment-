# 🪙 Aptos Payment Protocol

## Overview
This project implements a simple payment logging protocol on the Aptos blockchain. It records payment details such as sender, recipient, amount, and a unique payment ID. **Note:** This version does not transfer funds—it only logs the payment metadata on-chain.

## Features
- ✅ Logs payments with unique IDs
- 📦 Stores sender, recipient, and amount
- 🔔 Emits events for off-chain tracking
- 🔐 Built with Move smart contracts on Aptos

## Smart Contract Design

### Structs
```move
struct PaymentDetails {
    sender: address,
    recipient: address,
    amount: u64
}

struct PaymentsTable {
    table: Table<vector<u8>, PaymentDetails>
}

event PaymentMade {
    payment_id: vector<u8>,
    sender: address,
    recipient: address,
    amount: u64
}
