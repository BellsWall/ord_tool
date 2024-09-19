
# 🎮 Bellscoin Ordinals Inscription Tool 🐉

Welcome, brave TypeScript wizards 🧙‍♂️, to the realm of Bellscoin Ordinals! Craft your inscriptions with the magic of taproot (P2TR) transactions.

## 🚀 Features

- ✨ **Craft Taproot Scripts**: Forge inscriptions for Ordinals.
- 🏰 **Transaction Kingdom**: Create one mighty Commit Transaction and numerous Reveal Transactions.

## 📦 Installation

Now, install the spellbook from npm:

```bash
npm install @bellswall/ord-tool
```

## 🛠️ Usage

### How to Cast:

```bash
import { OrdTool } from '@bellswall/ord-tool'
```

### Spell Workflow:

1. **🔮 Commit Spell**: Conjure a transaction that commits to your inscription.
2. **🖋️ Sign with Your Quill**: Use your wallet or code to sign this magical scroll.
3. **🌍 Broadcast to the World**: Send your signed commit transaction via the Mempool API.
4. **🕊️ Reveal the Magic**: After your commit, reveal your inscriptions to the blockchain.

### Example Grimoire:

```typescript
import { OrdTool, makeKeypairFromWIF } from '@bellswall/ord-tool'
// Configure your magical network and inscription runes
const network = 'mainnet'; // or 'mainnet' for the brave
const config: InscriptionConfig = {
  // Inscribe your config details here...
};

const tool = new OrdTool(config);

// Secure your private key in an enchanted .env file
// WIF=your_private_key_in_WIF_format
const wif = process.env.WIF;
const signer = makeKeypairFromWIF(wif, network);

// Generate and sign the commit transaction spell
let unsignCommitPsbt = await tool.makeUnsignedCommitPsbt();
// Sign with your magical powers or wallet
// ...

// Broadcast your spell and await its manifestation
const commitTransactionId = await tool.postCommitTransaction(signedCommitPsbt);
console.log("Commit transaction ID:", commitTransactionId);
await tool.waitUntilTransactionConfirm(commitTransactionId);

// Reveal your inscriptions to the world
await tool.postRevealTransactions();
```

## 🔐 Security and Best Practices

- **🔒 Key Guardianship**: Never expose your magical keys in code. Use enchanted hardware wallets or trusted spell-signing services.
- **🧪 Test in the Alchemist's Lab**: Always test on testnet before unleashing on mainnet.
- **👀 Confirm and Verify**: Double-check your spells and wait for their confirmation.

## 🤝 Contributions

Feel like adding more spells or enhancing our grimoire? Contributions are welcome! Follow the ancient coding scrolls and document your magic.

Follow our journey on [X](https://x.com/BitcoinIndexer) 🐦

Let's make blockchain inscriptions as fun as a barrel of monkeys 🐒! 
```

This version includes emojis to make the README more engaging and reflects the installation from npm, targeting TypeScript developers in modern web development environments.