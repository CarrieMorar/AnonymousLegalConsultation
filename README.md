# Anonymous Legal Consultation Platform

<div align="center">

![Legal Consultation](https://img.shields.io/badge/Legal-Consultation-red)
![FHE](https://img.shields.io/badge/FHE-Encrypted-blue)
![Blockchain](https://img.shields.io/badge/Blockchain-Enabled-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

**Privacy-Preserving Legal Services on Blockchain**

[Live Demo](https://anonymous-legal-consultation.vercel.app/) | [GitHub Repository](https://github.com/CarrieMorar/AnonymousLegalConsultation)

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Core Concepts](#core-concepts)
- [Key Features](#key-features)
- [Smart Contract](#smart-contract)
- [Technology Stack](#technology-stack)
- [Architecture](#architecture)
- [Screenshots](#screenshots)
- [Demo Video](#demo-video)
- [Use Cases](#use-cases)
- [Security](#security)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## 🌟 Overview

**Anonymous Legal Consultation Platform** is a revolutionary blockchain-based system that provides **fully encrypted, anonymous legal consultation services** using Fully Homomorphic Encryption (FHE) technology. Built on the Zama network, this platform ensures complete privacy for clients seeking legal advice while maintaining transparency and immutability of the consultation records.

The platform bridges the gap between traditional legal services and modern privacy-preserving technologies, enabling clients to submit sensitive legal questions without revealing their identity, while lawyers can provide professional responses in a secure and verifiable manner.

---

## 🔑 Core Concepts

### 1. **FHE-Powered Privacy**
Fully Homomorphic Encryption (FHE) allows computations on encrypted data without decryption. This means:
- Client questions remain encrypted on-chain
- Lawyer responses are stored in encrypted form
- Only authorized parties can decrypt the information
- No third party (including platform admins) can read private consultations

### 2. **Anonymous Identity Management**
- Clients use self-generated anonymous IDs (not linked to wallet addresses)
- Lawyer identities are encrypted using FHE
- Privacy is maintained throughout the entire consultation lifecycle
- No personal information is exposed on the blockchain

### 3. **Decentralized Legal Services**
- No centralized authority controls the consultations
- Smart contracts manage the entire workflow
- Transparent fee structure recorded on-chain
- Immutable record of all consultations for dispute resolution

### 4. **Lawyer Verification System**
- Admin-controlled lawyer verification process
- Rating system for lawyer performance (encrypted)
- Specialty-based lawyer categorization
- Active/inactive status management

### 5. **Multi-Category Legal Support**
The platform supports 8 major legal categories:
1. **Civil Law** - Contracts, property disputes, torts
2. **Criminal Law** - Defense, prosecution advice
3. **Family Law** - Divorce, custody, inheritance
4. **Corporate Law** - Business formation, M&A, compliance
5. **Employment Law** - Labor disputes, contracts
6. **Real Estate Law** - Property transactions, leases
7. **Immigration Law** - Visa, citizenship, asylum
8. **Tax Law** - Tax planning, disputes

---

## ✨ Key Features

### For Clients
- 🔒 **Anonymous Consultations** - Submit legal questions with complete privacy
- 🔐 **End-to-End Encryption** - FHE ensures your data is never exposed
- 💰 **Pay-per-Consultation** - Transparent fee structure (minimum 0.001 ETH)
- 📊 **Track Consultations** - Monitor status and receive responses
- 🎯 **Category-Based Matching** - Get matched with specialized lawyers

### For Lawyers
- ⚖️ **Professional Registration** - Register with specialty verification
- 💼 **Manage Consultations** - View assigned cases and provide responses
- ⭐ **Build Reputation** - Earn ratings based on performance
- 💸 **Earn Income** - Receive fees for successful consultations

### For Administrators
- 🔧 **Lawyer Verification** - Approve and verify lawyer credentials
- 📌 **Consultation Assignment** - Assign cases to qualified lawyers
- ⚡ **Platform Management** - Update ratings, deactivate lawyers
- 💵 **Fee Management** - Withdraw platform fees

---

## 📜 Smart Contract

### Contract Information
- **Contract Address**: `0xBA9Daca2dEE126861963cd31752A9aCBc5488Df7`
- **Network**: Zama Devnet (Chain ID: 9000)
- **Contract Name**: AnonymousLegalConsultation
- **Compiler**: Solidity ^0.8.24
- **License**: MIT

### Core Functions

#### Client Functions
```solidity
function submitConsultation(
    uint32 _clientId,
    uint32 _categoryId,
    string calldata _encryptedQuestion
) external payable
```

#### Lawyer Functions
```solidity
function registerLawyer(uint32 _specialty) external

function provideResponse(
    uint256 consultationId,
    string calldata _encryptedResponse
) external
```

#### Admin Functions
```solidity
function assignConsultation(uint256 consultationId, uint256 lawyerId) external
function verifyLawyer(uint256 lawyerId) external
function updateLawyerRating(uint256 lawyerId, uint32 newRating) external
function deactivateLawyer(uint256 lawyerId) external
function withdrawFees(uint256 amount) external
```

#### View Functions
```solidity
function getConsultationDetails(uint256 consultationId) external view
function getLawyerProfile(uint256 lawyerId) external view
function getClientStats(address clientAddress) external view
function getSystemStats() external view
```

---

## 🛠️ Technology Stack

### Blockchain & Cryptography
- **Zama FHE Library** - Fully Homomorphic Encryption
- **Solidity** - Smart contract development
- **Ethers.js** - Blockchain interaction
- **MetaMask** - Wallet integration

### Frontend
- **HTML5/CSS3** - Modern responsive design
- **JavaScript (ES6+)** - Interactive functionality
- **Custom UI/UX** - No default themes, fully customized

### Infrastructure
- **Vercel** - Hosting and deployment
- **GitHub** - Version control
- **Zama Devnet** - Blockchain network

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Client Interface                      │
│  (Submit Consultations, View Status, Track Responses)   │
└───────────────────┬─────────────────────────────────────┘
                    │
┌───────────────────▼─────────────────────────────────────┐
│                  Smart Contract Layer                    │
│                                                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │ Consultation │  │    Lawyer    │  │    Admin     │ │
│  │  Management  │  │  Management  │  │  Management  │ │
│  └──────────────┘  └──────────────┘  └──────────────┘ │
│                                                          │
│  ┌────────────────────────────────────────────────────┐ │
│  │         FHE Encryption/Decryption Layer            │ │
│  │   (euint32, eaddress, encrypted strings)           │ │
│  └────────────────────────────────────────────────────┘ │
└───────────────────┬─────────────────────────────────────┘
                    │
┌───────────────────▼─────────────────────────────────────┐
│              Zama Blockchain Network                     │
│        (Immutable, Encrypted, Decentralized)            │
└──────────────────────────────────────────────────────────┘
```

### Workflow Diagram

```
Client → Submit Encrypted Question → Smart Contract → Store on Blockchain
                                          ↓
Admin → Assign to Lawyer → Notify Lawyer via ID (encrypted)
                                          ↓
Lawyer → Provide Encrypted Response → Smart Contract → Update Blockchain
                                          ↓
Client → Retrieve Consultation → Decrypt Response → View Answer
```

---


### On-Chain Transaction Examples
---

## 🎥 Demo Video

### Watch the Platform in Action

[![Demo Video](AnonymousLegalConsultation.mp4)

**Video Highlights:**
- 00:00 - Platform overview and wallet connection
- 01:30 - Client submitting encrypted consultation
- 03:45 - Lawyer registration and verification
- 05:20 - Admin assigning consultation to lawyer
- 07:10 - Lawyer providing encrypted response
- 09:00 - Client viewing consultation results
- 10:30 - Platform statistics and analytics

---

## 💼 Use Cases

### 1. **Corporate Compliance Inquiries**
A multinational company needs confidential legal advice about regulatory compliance without exposing their strategy to competitors.

**Solution**: Submit encrypted questions about compliance requirements, receive private legal guidance.

### 2. **Personal Legal Matters**
Individuals facing sensitive family law issues (divorce, custody) need advice without public exposure.

**Solution**: Anonymous consultation system protects client identity while providing professional legal counsel.

### 3. **Whistleblower Protection**
Employees reporting corporate misconduct need legal advice without revealing their identity.

**Solution**: FHE encryption ensures complete anonymity while enabling legal consultation.

### 4. **International Legal Advice**
Clients in restrictive jurisdictions need legal consultation without government surveillance.

**Solution**: Decentralized, encrypted platform accessible globally with complete privacy.

### 5. **Small Business Legal Support**
Startups need affordable legal advice for contracts, employment, and intellectual property.

**Solution**: Pay-per-consultation model with transparent pricing and verified lawyers.

---

## 🔐 Security

### Encryption Standards
- **FHE Implementation**: Zama's fhevm library for fully homomorphic encryption
- **Data Privacy**: All sensitive data encrypted at rest and in transit
- **Key Management**: Client-side key generation and management
- **Access Control**: Smart contract-enforced permission system

### Smart Contract Security
- **Audited Code**: Following Solidity best practices
- **Access Modifiers**: Role-based access control (Admin, Lawyer, Client)
- **Reentrancy Protection**: Guards against common attack vectors
- **Gas Optimization**: Efficient storage and computation patterns

### Platform Security Headers
```javascript
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
```

### Privacy Features
- ✅ Anonymous client IDs (not linked to wallets)
- ✅ Encrypted lawyer identities (eaddress)
- ✅ Encrypted consultation content
- ✅ Encrypted responses
- ✅ Encrypted ratings and specialties
- ✅ No off-chain data storage
- ✅ Complete on-chain privacy

---

## 🗺️ Roadmap

### Phase 1: Foundation (Completed ✅)
- [x] Smart contract development with FHE
- [x] Frontend interface design
- [x] Wallet integration
- [x] Basic consultation workflow
- [x] Lawyer registration system
- [x] Admin management panel

### Phase 2: Enhancement (Q2 2025)
- [ ] Multi-language support (Spanish, Chinese, French)
- [ ] Mobile-responsive design improvements
- [ ] Advanced search and filtering
- [ ] Lawyer reputation dashboard
- [ ] Client review system
- [ ] Automated consultation assignment

### Phase 3: Advanced Features (Q3 2025)
- [ ] AI-powered lawyer matching algorithm
- [ ] Video consultation integration (encrypted)
- [ ] Document upload and sharing (encrypted)
- [ ] Multi-signature approval for high-value cases
- [ ] Dispute resolution mechanism
- [ ] Token incentive system

### Phase 4: Ecosystem Expansion (Q4 2025)
- [ ] Mainnet deployment
- [ ] Mobile app (iOS/Android)
- [ ] API for third-party integrations
- [ ] Legal document templates marketplace
- [ ] Cross-chain compatibility
- [ ] DAO governance implementation

### Future Vision
- Integration with legal tech ecosystems
- Partnership with law firms globally
- Regulatory compliance frameworks
- Insurance integration for legal services
- Academic partnerships for legal research

---

## 🤝 Contributing

We welcome contributions from the community! Whether you're a developer, lawyer, or privacy advocate, there are many ways to contribute:

### How to Contribute

1. **Fork the Repository**
   ```bash
   git clone https://github.com/CarrieMorar/AnonymousLegalConsultation.git
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**
   - Add features
   - Fix bugs
   - Improve documentation
   - Enhance UI/UX

4. **Commit Your Changes**
   ```bash
   git commit -m "Add: your feature description"
   ```

5. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Submit a Pull Request**
   - Describe your changes
   - Link related issues
   - Wait for review

### Contribution Guidelines
- Follow Solidity and JavaScript best practices
- Write clear, commented code
- Test thoroughly before submitting
- Update documentation as needed
- Respect the code of conduct

### Areas We Need Help
- 🔧 Smart contract optimization
- 🎨 UI/UX design improvements
- 📝 Documentation and tutorials
- 🌍 Internationalization and translations
- 🔒 Security audits and testing
- 📊 Data analytics and visualization

---

## 📄 License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2025 Anonymous Legal Consultation Platform

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Contact & Support

### Links
- **Live Application**: [https://anonymous-legal-consultation.vercel.app/](https://anonymous-legal-consultation.vercel.app/)
- **GitHub Repository**: [https://github.com/CarrieMorar/AnonymousLegalConsultation](https://github.com/CarrieMorar/AnonymousLegalConsultation)
- **Contract Explorer**: View on Zama Devnet Explorer

### Community
- **Issues**: Report bugs or request features on GitHub Issues
- **Discussions**: Join GitHub Discussions for community support
- **Twitter**: Follow us for updates and announcements

### Support
For technical support, security issues, or business inquiries, please open an issue on GitHub.

---

## 🙏 Acknowledgments

Special thanks to:
- **Zama** - For the revolutionary FHE technology and fhevm library
- **Ethereum Community** - For the robust smart contract infrastructure
- **Open Source Contributors** - For making this project possible
- **Legal Professionals** - For providing domain expertise and feedback
- **Privacy Advocates** - For inspiring the need for anonymous legal services

---

## ⚖️ Disclaimer

This platform is a technology demonstration and should not be considered a substitute for professional legal advice. Always consult with licensed legal professionals for important legal matters. The platform developers assume no liability for the accuracy, completeness, or reliability of any legal information provided through this system.

---

<div align="center">

**Built with ❤️ for Privacy and Justice**

![FHE](https://img.shields.io/badge/Powered%20by-Zama%20FHE-blue?style=for-the-badge)
![Blockchain](https://img.shields.io/badge/Built%20on-Blockchain-green?style=for-the-badge)
![Privacy](https://img.shields.io/badge/Privacy-First-red?style=for-the-badge)

[⬆ Back to Top](#anonymous-legal-consultation-platform)

</div>