# SureCrop 🌾
### Blockchain-Powered Contract Farming Platform

> **Smart India Hackathon 2024** — Problem Statement ID #1640  
> Theme: Agriculture, FoodTech & Rural Development

SureCrop is a mobile and web platform that connects farmers directly with buyers through **Ethereum smart contracts** — eliminating middlemen, ensuring transparent pricing, and guaranteeing secure, timely payments.

---

## 🌱 The Problem

- **86%** of Indian smallholder farmers struggle with market access (NSSO)
- Traditional contracts lack transparency, security, and payment reliability
- Farmers lose income to fluctuating demand and unreliable buyers
- Middlemen capture **15–20%** of procurement costs, reducing farmer earnings
- Contract farming models with assured pricing have shown income growth from ₹50,000 to ₹70,000 per hectare annually (FAO)

---

## ✅ What SureCrop Does

| Feature | Description |
|---|---|
| **Crop Listing & Search** | Farmers list crops; buyers filter by type, region, price |
| **Smart Contract Agreements** | Ethereum-based contracts auto-enforce payment terms |
| **Price Negotiation** | In-app negotiation with real-time market price insights |
| **Secure Payments** | Escrow-based payment release on contract fulfillment |
| **Regional Language Support** | Text-to-speech and UI in regional Indian languages |
| **In-App Chat** | Direct communication between farmers and buyers |
| **No Middlemen** | End-to-end direct farmer-to-buyer transactions |

---

## ⚙️ System Architecture

```
Flutter App (Farmer / Buyer)
          │
          ├── Farmer Role ─────────────────────┐
          └── Buyer Role ──────────────────────┤
                                               ▼
                                        Node.js + Express.js
                                        (REST API Backend)
                                               │
                    ┌──────────────────────────┼──────────────────┐
                    ▼                          ▼                  ▼
             Ethereum Blockchain          MongoDB / Firebase    Google Cloud
             (Smart Contracts             (User Profiles,       Text-to-Speech
              via Solidity)               Listings, History)    API
                    │
                    ▼
          Polygon Network (L2)
          Low gas fee alternative
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Mobile Frontend** | Flutter (Dart) |
| **Backend** | Node.js + Express.js |
| **Blockchain** | Ethereum (Solidity smart contracts) |
| **L2 / Low-fee alternative** | Polygon (MATIC) |
| **Database** | MongoDB / Firebase |
| **Payments** | Smart contract escrow (custodial wallets for farmers) |
| **TTS / Language** | Google Cloud Text-to-Speech API |
| **Version Control** | Git / GitHub |

---

## 📦 Installation

### Prerequisites
- Node.js `>=18.x`
- Flutter SDK `>=3.0.0`
- MongoDB instance (local or Atlas)
- MetaMask or custodial wallet setup
- Hardhat (for smart contract deployment)

### Clone & Setup

```bash
git clone https://github.com/YOUR_USERNAME/surecrop.git
cd surecrop
```

**Backend:**
```bash
cd backend
npm install
cp .env.example .env   # fill in your keys
node index.js
```

**Smart Contracts:**
```bash
cd contracts
npm install
npx hardhat compile
npx hardhat deploy --network polygon_mumbai   # testnet
```

**Flutter App:**
```bash
cd mobile
flutter pub get
flutter run
```

---

## 🗂️ Project Structure

...

---

## 📜 Smart Contract Overview

The core `SureCrop.sol` contract handles:

```solidity
// Key contract functions
function createContract(address buyer, uint cropId, uint amount, uint price) external;
function confirmDelivery(uint contractId) external;
function releasePayment(uint contractId) external;
function raiseDispute(uint contractId) external;
```

- Funds are held in escrow until delivery is confirmed
- Both parties must sign; neither can alter terms unilaterally
- Dispute resolution handled via arbitration logic

---

## 💡 Key Design Decisions

**Why Polygon over Ethereum mainnet?**  
Ethereum gas fees can be prohibitively expensive for small farmers. Polygon offers near-zero gas fees with the same smart contract security, making micro-transactions viable.

**Why custodial wallets for farmers?**  
Most farmers have no experience with crypto wallets. Custodial wallets abstract blockchain complexity — farmers interact with a familiar mobile UI while the platform manages wallet operations.

**Why regional language TTS?**  
Digital literacy is low in rural India. Voice-guided navigation in the farmer's native language dramatically reduces the adoption barrier.

---

## 📊 Impact Potential

| Stakeholder | Benefit |
|---|---|
| Farmers | Guaranteed buyers; income stability; 40–60% reduction in admin overhead |
| Buyers | Access to 50M+ tons of quality produce; save ₹10–15 lakhs/year in procurement |
| Both | Elimination of 15–20% middlemen fees |

---

## 🏆 Recognition

**Smart India Hackathon 2024** — Problem Statement ID #1640  
Category: Software | Theme: Agriculture, FoodTech & Rural Development  
Institution: JNTUH UCESTH

---

## 👥 Team

| Name | Role |
|---|---|
| Mohd Abdullah Junaid | Blockchain (Solidity), Backend (Node.js), Architecture |
| Mohd Jamaluddin | Firebase Integration, Flutter Frontend, UI/UX |
| Rashmi Kanna | Research, Design |


## 📄 References

- [Ethereum.org](https://ethereum.org) — Smart contracts documentation
- [AgriFin](https://www.agrifinfacility.org/contract-farming) — Contract farming overview
- [Google Cloud TTS](https://cloud.google.com/text-to-speech)
- NSSO Report on Smallholder Farmers
- FAO — Contract Farming in Developing Countries

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
