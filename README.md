# ☁️ CloudWhisper

[![AI for Bharat Hackathon](https://img.shields.io/badge/AI%20for%20Bharat-Student%20Track-orange)](https://aiforBharat.org)
[![Problem Statement](https://img.shields.io/badge/Problem%20Statement-1%3A%20Developer%20Productivity-blue)](https://aiforBharat.org)
[![AWS](https://img.shields.io/badge/AWS-Powered-FF9900?logo=amazon-aws)](https://aws.amazon.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Natural Language Cloud Deployment for India's Next Generation of Builders**

CloudWhisper is an AI-powered platform that lets developers deploy applications to AWS using simple natural language prompts—no dashboards, no deep cloud expertise required. Built for India's 5M+ aspiring developers, especially those from tier-2/3 cities and non-metro areas.

```
You: "Mera React app deploy kar do AWS pe, budget low rakhna"
CloudWhisper: ✅ Deployed! Your app is live at https://xyz.cloudfront.net
              💰 Cost: ₹0/month (Free Tier)
```

---

## 🎯 Why CloudWhisper?

### The Problem
Developers building apps with AI tools (Cursor, VS Code, Claude) face steep barriers when deploying:
- **Complex cloud consoles** (AWS IAM, VPCs, scaling configs)
- **English-heavy technical docs** that exclude non-fluent developers
- **Cost fears** and lack of guided workflows
- **Context switching** from IDE to cloud platforms

This leads to "deployment dropout"—especially among students and self-taught developers from smaller towns, slowing innovation in India's growing tech ecosystem.

### The Solution
CloudWhisper democratizes cloud access by:
- 🗣️ **Natural language prompts** (English + Hinglish support)
- 🔐 **OAuth integration** for secure cloud authentication
- 💰 **Cost transparency** with Free Tier prioritization
- 🚀 **IDE integration** (VS Code/Cursor extensions)
- 📚 **Plain language explanations** tailored for Indian users
- 🌐 **Low-bandwidth friendly** design for rural connectivity

---

## 🇮🇳 Built for Bharat

CloudWhisper addresses India-specific pain points:

- **Language Inclusion**: Hinglish support for developers who think in Hindi but code in English
- **Cost Awareness**: Emphasizes AWS Free Tier to reduce financial barriers
- **Digital Inclusion**: Low-bandwidth design for tier-2/3 cities with limited connectivity
- **Skill Building**: Generated IaC includes plain language comments to teach cloud concepts
- **Local Context**: Recognizes Indian terms (₹, lakh, crore) and budget constraints

Perfect for building India-relevant apps: agri-tech marketplaces, vernacular edtech platforms, rural fintech solutions, and more.

---

## ✨ Features

### 🤖 AI-Powered Prompt Parsing
- Parse deployment requests in English or Hinglish
- Extract infrastructure requirements automatically
- Request clarification for ambiguous prompts
- Support for web apps, APIs, static sites, and containers

### 🏗️ Infrastructure-as-Code Generation
- Generate AWS CDK code with plain language comments
- Prioritize Free Tier eligible resources
- Include security best practices (least-privilege IAM, encryption)
- Preview IaC before deployment

### 💵 Cost Estimation
- Calculate estimated monthly costs in USD and INR
- Highlight Free Tier savings
- Warn about variable-cost resources
- Suggest alternatives when budget exceeded

### 🚀 One-Click Deployment
- Deploy to AWS with a single confirmation
- Real-time progress updates
- Post-deployment insights (URLs, endpoints, logs)
- Rollback support for failed deployments

### 🔌 IDE Integration
- VS Code/Cursor extension with sidebar panel
- Framework auto-detection
- Offline template caching for low-bandwidth
- In-editor notifications

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ and npm
- AWS account (Free Tier eligible)
- VS Code or Cursor IDE

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/cloudwhisper.git
cd cloudwhisper
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure AWS credentials**
```bash
aws configure
# Enter your AWS Access Key ID and Secret Access Key
```

4. **Deploy CloudWhisper infrastructure**
```bash
cd infrastructure
npm install
npx cdk bootstrap  # First time only
npx cdk deploy
```

5. **Install VS Code extension**
```bash
cd ../vscode-extension
npm install
npm run package
code --install-extension cloudwhisper-0.1.0.vsix
```

### Usage

#### From VS Code/Cursor

1. Open the CloudWhisper sidebar panel
2. Enter your deployment prompt:
   ```
   Deploy my React app to AWS with auto-scaling and CDN
   ```
   Or in Hinglish:
   ```
   Mera Next.js app deploy karo, free tier mein
   ```
3. Review the generated IaC and cost estimate
4. Click "Deploy" to execute

#### From CLI

```bash
cloudwhisper deploy "Deploy my Express API with DynamoDB database"
```

---

## 📖 Example Prompts

### English
```
"Deploy a static website to S3 with CloudFront CDN"
"Create a REST API with Node.js and DynamoDB, under $10/month"
"Deploy my React app with auto-scaling, keep costs minimal"
```

### Hinglish
```
"Mera portfolio website deploy kar do, free mein"
"API banao Express.js mein with database, ₹500 per month"
"React app ko AWS pe deploy karo, CDN ke saath"
```

---

## 🏗️ Architecture

CloudWhisper uses a serverless architecture on AWS:

```
┌─────────────────┐
│  VS Code/Cursor │
│    Extension    │
└────────┬────────┘
         │ HTTPS
         ▼
┌─────────────────┐
│  API Gateway    │
└────────┬────────┘
         │
    ┌────┴────┬────────┬──────────┬──────────┐
    ▼         ▼        ▼          ▼          ▼
┌────────┐ ┌──────┐ ┌──────┐ ┌────────┐ ┌────────┐
│ Prompt │ │ IaC  │ │ Cost │ │ Deploy │ │ OAuth  │
│ Parser │ │ Gen  │ │ Est  │ │ Orch   │ │Handler │
└───┬────┘ └──────┘ └──────┘ └────────┘ └────────┘
    │
    ▼
┌─────────────────┐
│  AWS Bedrock    │
│ (Claude Sonnet) │
└─────────────────┘
```

**Key Components:**
- **Prompt Parser**: AWS Bedrock (Claude 3 Sonnet) for multilingual NLP
- **IaC Generator**: AWS CDK for infrastructure code generation
- **Cost Estimator**: AWS Pricing API for accurate cost calculations
- **Deployment Orchestrator**: CloudFormation for resource provisioning
- **Storage**: DynamoDB (user data), S3 (templates), Secrets Manager (OAuth tokens)

**Estimated Monthly Cost**: $25-40 (after Free Tier)

---

## 🎓 For Students & Learners

CloudWhisper is designed to be educational:

- **Learn by Doing**: See the actual IaC code that gets deployed
- **Plain Language Comments**: Every resource explained in simple terms
- **Cost Awareness**: Understand cloud pricing from day one
- **Security Best Practices**: Learn IAM, encryption, and least-privilege principles
- **Incremental Complexity**: Start with static sites, progress to APIs and containers

Perfect for:
- 🎓 College students learning cloud computing
- 💻 Self-taught developers from tier-2/3 cities
- 🚀 Hackathon participants needing quick deployments
- 🛠️ Indie developers building MVPs
- 📱 Freelancers deploying client projects

---

## 🌟 Hackathon Context

**AI for Bharat Hackathon - Student Track**  
**Problem Statement 1: AI for Developer Productivity**

CloudWhisper aligns with the hackathon's vision of democratizing technology for India:

- **Breaks Language Barriers**: Like "Code explainer for local languages," but for deployment
- **Boosts Productivity**: Reduces deployment time from hours to minutes
- **Enables Innovation**: Lets developers focus on building, not infrastructure
- **Supports Digital India**: Empowers 5M+ aspiring developers across urban-rural divide
- **Builds for Bharat**: Enables creation of India-relevant apps (agri-tech, edtech, vernacular tools)

---

## 🛠️ Tech Stack

- **AI/ML**: AWS Bedrock (Claude 3 Sonnet), LangChain
- **Backend**: AWS Lambda (Node.js/TypeScript), API Gateway
- **Infrastructure**: AWS CDK, CloudFormation
- **Storage**: DynamoDB, S3, Secrets Manager
- **Security**: AWS KMS, IAM, OAuth 2.0
- **Monitoring**: CloudWatch, X-Ray
- **Frontend**: VS Code Extension API, React

---

## 📊 Success Metrics

- ✅ 80%+ successful deployments in beta tests
- ✅ User retention >50% after first use
- ✅ Feedback scores >4/5 on ease and inclusivity
- ✅ <10% error rate on prompt parsing (including Hinglish)
- ✅ Cost under $50/month for prototype
- ✅ Adoption by 10+ Indian student developers from non-metro areas

---

## 🗺️ Roadmap

### Phase 1: MVP (Current)
- [x] Natural language prompt parsing (English + Hinglish)
- [x] AWS deployment via CDK
- [x] Cost estimation with Free Tier awareness
- [x] VS Code extension
- [ ] Beta testing with 10+ Indian student developers

### Phase 2: Multi-Cloud
- [ ] GCP deployment support
- [ ] Azure deployment support
- [ ] Multi-cloud cost comparison

### Phase 3: Advanced Features
- [ ] Real-time monitoring dashboards
- [ ] Auto-scaling recommendations
- [ ] CI/CD pipeline integration
- [ ] Team collaboration features

### Phase 4: Full Localization
- [ ] Complete Hindi UI
- [ ] Regional language support (Tamil, Telugu, Bengali)
- [ ] Voice-based deployment prompts

---

## 🤝 Contributing

We welcome contributions from developers across India! Whether you're from a metro city or a small town, your perspective matters.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **AI for Bharat Hackathon** for inspiring this project
- **AWS** for providing the cloud infrastructure
- **Indian developer community** for feedback and testing
- **Tier-2/3 city developers** whose challenges shaped this solution

---

## 📞 Contact

- **Project Lead**: Mohammed Yousuf Ali Adnan
- **Email**: yousufaliadnan8@gmail.com

---

<div align="center">

**Built with ❤️ for India's Next Generation of Builders**

[Website](https://cloudwhisper.dev) • [Documentation](https://docs.cloudwhisper.dev) • [Demo Video](https://youtube.com/cloudwhisper)

</div>
