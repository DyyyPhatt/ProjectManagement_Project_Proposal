
# ☁️ Cloud-Based Project Management Dashboard with AWS Microservices

## 📌 Subtitle: Scalable and Secure Task Collaboration Platform Using AWS & Modern Web Technologies

---

## 📄 Executive Summary

In the digital transformation era, many SMEs lack a secure and scalable platform for project and team management. This proposal presents a cloud-native Project Management Dashboard application built on modern technologies such as **Next.js, Node.js, PostgreSQL, and AWS services (EC2, RDS, Cognito, S3, Lambda, API Gateway, Amplify)**.

### Problem:
Most teams use fragmented tools (emails, spreadsheets, chat apps) to manage projects, leading to poor productivity, miscommunication, and delayed deliverables. Current SaaS options like Jira or Asana are either costly or lack customization for internal workflows.

### Solution:
A centralized platform enabling:
- Project creation and task management
- Role-based access control
- Realtime dashboards, notifications
- File attachments and visual charts

### Business Benefits:
- 25–40% improvement in team productivity
- 60% cost savings compared to commercial SaaS tools
- Supports remote collaboration and rapid scalability

### Investment and Timeline:
- Estimated Monthly Cost (AWS Free Tier): $0, Max Prod Cost: ~$50/month
- MVP completion within 9 working days

### Success Metrics:
- Uptime ≥ 99.9%, Response latency < 300ms
- Handle 10,000 active users/month
- ≥95% task operation success rate

---

## 1. 🎯 Problem Statement

### Current Situation
SMEs and startup teams face difficulties with:
- Scattered tools (Excel, Email, Trello)
- Lack of integrated user authentication and permissions
- No unified dashboard or visibility into task progress

### Pain Points
| Pain Point | Business Impact |
|------------|------------------|
| Lack of centralized task system | Missed deadlines, unclear ownership |
| No access control | Risk of unauthorized access |
| High SaaS cost | ~$10–20/user/month recurring expense |
| Poor data visualization | Lack of KPIs and decision-making support |

### Stakeholder Analysis
| Stakeholder | Needs |
|-------------|-------|
| Project Manager | Assign, track, analyze progress |
| Developer | View assigned tasks, deadlines |
| Admin | Manage users, access rights |
| CTO | Ensure security, cost, compliance |

### Market Opportunity
According to Gartner, 85% of enterprises will adopt cloud-first project tools by 2026. Cloud-native solutions save cost, reduce operational burden, and offer agility.

---

## 2. 🏗️ Solution Architecture

### System Overview
A 3-tier application deployed on AWS:

- **Frontend (Client)**: Next.js hosted via AWS Amplify
- **Backend (API)**: Node.js (Express) on Amazon EC2
- **Database**: PostgreSQL via Amazon RDS
- **Authentication**: AWS Cognito (JWT-based)
- **File Storage**: Amazon S3 (images, attachments)
- **Async Logic**: AWS Lambda
- **API Gateway**: Proxy secured access to backend or Lambda endpoints

### AWS Architecture Components
| Layer | AWS Service | Purpose |
|------|--------------|--------|
| UI | Amplify | Host React-based frontend |
| API | EC2 | Handle API requests |
| DB | RDS | Persistent structured data |
| Auth | Cognito | Manage users, tokens |
| Files | S3 | Store user avatars, attachments |
| Events | Lambda | Handle background events |
| Proxy | API Gateway | Secure access point, scalable routing |

### Security Architecture
- Cognito → access/refresh tokens → Express backend
- HTTPS + JWT headers → secure endpoints
- EC2 and RDS in private subnets
- S3 public access restricted by bucket policy

### Scalability
- Stateless backend with horizontal scaling (EC2 ASG)
- Amplify autoscales frontend
- RDS Multi-AZ optional
- S3 scalable with low latency

---

## 3. 🔧 Technical Implementation

### Implementation Phases

| Phase | Tasks |
|-------|-------|
| P1 | Setup VPC, subnets, IGW, Route Tables |
| P2 | Deploy EC2, RDS, setup Prisma, Node.js |
| P3 | Configure Cognito + API Gateway |
| P4 | Connect S3, deploy frontend via Amplify |
| P5 | Testing: unit, integration, performance |
| P6 | Monitor, seed data, finalize deployment |

### Dev Stack
- Frontend: Next.js, TailwindCSS, Redux Toolkit
- Backend: Express, Prisma ORM, Typescript
- DB: PostgreSQL, PgAdmin
- Auth: Cognito, JWT tokens
- DevOps: PM2, AWS CLI, Postman, GitHub Actions

### Testing
- Backend: Jest, Postman collection tests
- Frontend: React Testing Library + Playwright
- Load Testing: Apache Benchmark on EC2
- CI/CD: Amplify + GitHub auto redeploy

---

## 4. 📅 Timeline & Milestones

| Phase | Duration | Milestone |
|-------|----------|-----------|
| Infra Setup | 3 days | VPC, EC2, RDS ready |
| Backend/API | 2 days | Auth, CRUD APIs done |
| Frontend | 1 day | Amplify live, UI integrated |
| Integration | 1 day | Cognito + API secured |
| Testing & Optimization | 2 days | Finalized MVP |
| **Total** | **9 days** | **Deployable Solution** |

---

## 5. 💰 Budget Estimation

### Monthly Cost Estimate (AWS)

| Service | Est. Monthly Cost (USD) |
|---------|-------------------------|
| EC2 (t2.micro) | $0 (Free Tier) |
| RDS PostgreSQL (t3.micro) | $0 (Free Tier) |
| S3 (<=5GB) | $0 |
| Cognito (50k MAUs) | $0 |
| Amplify Hosting | $0 |
| Lambda + API Gateway | $0 |
| **Total** | **$0** (within Free Tier) |

### Cost Growth (after scaling)
- Est. Prod Cost: ~$30–50/month with 100+ users

### ROI and TCO
- Jira Pricing: $10/user/month → ~$100/month for 10 users
- Proposed: $0–$30/month → 60–90% cost savings
- Maintenance by 1 developer vs SaaS admin team

---

## 6. ⚠️ Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Cognito misconfig | Medium | High | Use official SDKs + test flows |
| EC2 down | Low | High | Add auto-recovery, AMI backup |
| RDS connection overload | Medium | Medium | Pooling + Retry + Read replica |
| API Gateway quota limit | Low | Medium | Enable throttling, scale plans |

---

## 7. 🎯 Expected Outcomes

### Success Metrics
- Avg API response < 300ms (p95)
- 10,000 MAU with < $50 infra
- 99.9% uptime with 1 EC2 instance
- <2s load time for dashboard

### Short-Term Benefits (0–6 months)
- Replace spreadsheet-based tracking
- Faster task assignment
- Role-based visibility

### Medium-Term (6–18 months)
- Scale to multi-team usage
- CI/CD automation
- Integrate chat/notifications

### Long-Term (18+ months)
- SaaS-like multi-tenant version
- Usage analytics and ML predictions

---

## 📎 Appendices

### A. Architecture Diagram
*(See `/architecture.png` in GitHub repo)*

### B. AWS Calculator Breakdown
*(Exported as CSV in `/cost/` folder)*

### C. Auth Flow
1. User login/signup (Cognito)
2. Receives JWT
3. Sends to API (via Gateway)
4. Validated in backend

### D. GitHub Repo
[https://github.com/DyyyPhatt/project-management](https://github.com/DyyyPhatt/project-management)
