# Deploy a Program to Atlas Testnet

This guide will help you deploy a Solana program to the Atlas Testnet.

---

## Prerequisites

- Solana CLI (v1.18.xx or higher)
- Basic knowledge of Solana programs
- Wallet funded with Sepolia ETH (for Atlas testnet)

---

## Steps

### 1. Install Solana CLI

```bash
sh -c "$(curl -sSfL https://release.solana.com/v1.18.11/install)"
```

Check the version:

```bash
solana --version
```

Make sure it's 1.18.xx or higher.

---

### 2. Set Atlas Testnet RPC URL

```bash
solana config set --url https://testnet.atlas.xyz
```

Verify your config:

```bash
solana config get
```

---

### 3. Get Your Wallet Address

```bash
solana address
```

Or, if you are using a custom keypair file:

```bash
solana address -k ~/my_wallet.json
```

---

### 4. Airdrop Sepolia ETH

Use the Atlas Testnet Faucet to airdrop Sepolia ETH to your wallet address.  

Faucet Link -  https://faucet.atlas.xyz/

---

### 5. Prepare the Program

Clone a sample program (It's Sample program you can also create using hekp of their docs or you can also use this ):

```bash
solana program dump -um TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA program.so
```

This will create a `program.so` file.

---

### 6. Generate a Program ID

Create a new program keypair:

```bash
solana-keygen new -f -o program-keypair.json -s --no-bip39-passphrase
```

This will generate a `program-keypair.json` file.

---

### 7. Deploy to Atlas Testnet

Deploy your program using:

```bash
solana program deploy -u "https://testnet.atlas.xyz" program.so --program-id program-keypair.json --use-rpc
```

✅ Use the `--use-rpc` flag to ensure reliable deployment.

---

## Full Commands Summary

```bash
# Install Solana CLI
sh -c "$(curl -sSfL https://release.solana.com/v1.18.11/install)"

# Set Atlas RPC
solana config set --url https://testnet.atlas.xyz

# Get Wallet Address
solana address

# Fund Wallet via Atlas Faucet

# Clone a sample program
solana program dump -um TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA program.so

# Generate new program keypair
solana-keygen new -f -o program-keypair.json -s --no-bip39-passphrase

# Deploy to Atlas Testnet
solana program deploy -u "https://testnet.atlas.xyz" program.so --program-id program-keypair.json --use-rpc
```

---

## Troubleshooting

- **CLI Version Error:**  
  Ensure you are using Solana CLI v1.18.xx or higher.

- **QUIC/UDP Errors:**  
  Always use the `--use-rpc` flag during deployment.

- **Insufficient Funds:**  
  Make sure your wallet is funded with Sepolia ETH.

- **Wrong Network:**  
  Verify that your RPC URL is set to `https://testnet.atlas.xyz`.

---

## Useful Links

- [Install Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
- [Atlas Discord Community](https://discord.gg/atlas-xyz)

---

## License

This guide is open-source and free to use.


