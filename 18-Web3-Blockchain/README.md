# 18 — Web3 y Blockchain (opcional)

> Nicho, volátil, pero paga muy bien. Decidí si te interesa.

⚠️ **Honestidad:** El espacio crypto tiene mucho ruido y muchas estafas. Acá nos enfocamos en la **tecnología**, no en especular.

---

## 🧱 Conceptos clave

| Concepto | Qué es |
|----------|--------|
| **Blockchain** | Base de datos distribuida e inmutable |
| **Smart Contract** | Código que corre en la blockchain |
| **Wallet** | Tu identidad cripto (Metamask, Phantom) |
| **Gas** | Costo de ejecutar transacciones |
| **NFT** | Token único (arte, dominios, identidad) |
| **DeFi** | Finanzas descentralizadas |
| **DAO** | Organización autónoma descentralizada |
| **L1 / L2** | Blockchain principal / capa de escalado |

---

## 🌐 Las blockchains principales (para devs)

| Blockchain | Lenguaje | Comentario |
|------------|----------|-----------|
| **Ethereum** | Solidity, Vyper | El estándar, más caro |
| **Solana** | Rust, Anchor | Rápido, barato |
| **Polygon** | Solidity | L2 de Ethereum |
| **Arbitrum / Optimism** | Solidity | L2 de Ethereum |
| **Base** | Solidity | L2 de Coinbase |
| **Sui / Aptos** | Move | Nuevas, técnicas |
| **Bitcoin** | Bitcoin Script | Limitado para apps |

---

## 🎓 Cómo empezar

### Ruta sugerida
```
JS/TS → Ethereum básico → Solidity → Hardhat/Foundry → frontend (wagmi/viem)
```

### Recursos
- 📺 [Patrick Collins - Curso Solidity (32 hs gratis)](https://www.youtube.com/watch?v=gyMwXuJrbJQ) ⭐⭐⭐
- 📖 [Cryptozombies](https://cryptozombies.io/) — aprender Solidity jugando
- 📖 [Ethereum.org developers](https://ethereum.org/es/developers/)
- 📖 [Speed Run Ethereum](https://speedrunethereum.com/)
- 📺 [BuildSpace](https://buildspace.so/) — proyectos guiados
- 📖 [Solidity by Example](https://solidity-by-example.org/)

---

## 💻 Solidity — Lenguaje de smart contracts

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Storage {
    uint256 private number;

    function set(uint256 _num) public {
        number = _num;
    }

    function get() public view returns (uint256) {
        return number;
    }
}
```

---

## 🛠️ Herramientas

### Frameworks Solidity
- **Hardhat** — el más popular (JS-based)
- **Foundry** ⭐ — moderno, en Rust (más rápido)
- **Truffle** — viejo, en desuso

### Frontend Web3
- **wagmi** — hooks de React para Ethereum
- **viem** — librería TS para Ethereum (reemplaza ethers.js)
- **RainbowKit** — UI de wallet bonita
- **Web3Modal** — selector de wallets

### Testnets (gratis para probar)
- **Sepolia** (Ethereum testnet)
- **Mumbai** (Polygon testnet)
- **Base Sepolia**

### Faucets
Reciben ETH/tokens de prueba gratis para testnet.

---

## 🎯 Proyectos para portfolio Web3

### Principiante
1. **Contador on-chain** — set/get un número
2. **Tu propio ERC-20** — crear un token
3. **NFT mintable** — colección con metadata

### Intermedio
4. **Voting DAO** — propuestas + votos
5. **Multisig wallet** — wallet con varias firmas
6. **Marketplace de NFTs** — comprar/vender

### Avanzado
7. **DEX simple** — swap entre 2 tokens (Uniswap V2)
8. **Lending protocol** — prestar y pedir prestado
9. **Bridge** entre dos chains (cuidado, sensible)

---

## 💰 Carrera en Web3

### Roles
- **Smart Contract Developer** — Solidity / Rust
- **Frontend Web3** — React + wagmi
- **Auditor** — encuentra vulnerabilidades ($$$)
- **Protocol Engineer** — bajo nivel

### Sueldos
Suelen ser **muy** altos en remoto, pagados en stablecoins/tokens.
Top auditors: $200k-$500k USD/año.

### Trabajos
- **CryptoJobsList** — https://cryptojobslist.com/
- **Web3 Career** — https://web3.career/

---

## ⚠️ Cosas que tenés que saber

### Seguridad es CRÍTICA
- Un bug = millones perdidos sin retorno
- Auditá SIEMPRE antes de mainnet
- Patrones comunes: reentrancy, integer overflow, access control
- Recursos: [Solidity Security Considerations](https://docs.soliditylang.org/en/latest/security-considerations.html)

### El gas y los costos
- Cada operación cuesta gas
- Optimizar el código tiene IMPACTO REAL ($)

### Inmutabilidad
- Lo que subís a la blockchain queda PARA SIEMPRE
- Usá proxy patterns para upgrades

---

## 🤔 ¿Te conviene aprender Web3?

**SÍ si:**
- Te interesa cripto/finanzas + programación
- Querés salarios altos en remoto
- Te gusta el nicho técnico

**NO si:**
- Solo querés "hacerte millonario"
- No tenés bases sólidas de JS/TS
- Te molestan los ciclos especulativos
