---
name: business-problem-to-blueprint
description: Transform any boring B2B business problem into a complete software blueprint with architecture, database schema, feature breakdown, and step-by-step implementation plan formatted as a CLAUDE.md file ready for development.
---

# Business Problem to Software Blueprint

Transform any boring B2B business problem into a complete, buildable software solution blueprint.

## What This Skill Does

You describe a business problem (e.g., "A gym needs to manage personal trainers, schedules, and client check-ins"), and this skill generates a **complete CLAUDE.md file** containing:

✅ **Software Architecture** - High-level system design
✅ **Database Schema** - Tables, relationships, and data structure
✅ **Feature Breakdown** - Organized by MVP, Phase 2, Phase 3
✅ **Tech Stack Recommendations** - Best technologies for this specific problem
✅ **Step-by-Step Implementation Plan** - Ordered tasks for Claude Code
✅ **Estimated Build Time** - Realistic timeline expectations
✅ **Deployment Strategy** - How to launch and host the software

## Who This Is For

**Software Tailors** who need to:
- Translate client problems into technical specifications
- Create professional project plans without being a developer
- Give Claude Code clear, structured instructions
- Estimate project scope and complexity
- Present technical solutions to non-technical clients

## How To Use This Skill

### Input Format

Describe the business problem in plain English:

**Example Input:**
```
Business: Fire inspection company
Problem: They manage 200+ inspections per month using Excel spreadsheets and paper forms. Inspectors waste 2 hours per day on paperwork. Office staff can't track which buildings are due for re-inspection. Clients call constantly asking for reports.

Key Requirements:
- Schedule and assign inspections to field inspectors
- Mobile app for inspectors to complete reports on-site
- Automatic reminders for upcoming inspections
- Generate PDF reports for clients
- Dashboard showing inspection status
```

### Output Format

The skill generates a **complete CLAUDE.md file** structured like this:

```markdown
# [Project Name] - Software Blueprint

## Project Overview
[Clear description of what you're building and why]

## Target Users
[Who will use this software]

## Core Problem Being Solved
[The specific pain points this addresses]

## Software Architecture

### System Components
1. **Frontend Application**
   - User interface for office staff
   - Mobile app for field workers

2. **Backend API**
   - Business logic and data management
   - Authentication and permissions

3. **Database**
   - Data storage and relationships

4. **Integrations**
   - Third-party services needed

### Tech Stack Recommendation
- **Frontend:** [Technology + why it's best for this project]
- **Backend:** [Technology + why]
- **Database:** [Technology + why]
- **Hosting:** [Platform + why]
- **Mobile:** [Approach + why]

## Database Schema

### Tables and Relationships

**inspections**
- id (primary key)
- building_id (foreign key → buildings)
- inspector_id (foreign key → users)
- scheduled_date
- status (scheduled, in_progress, completed)
- due_date
- created_at

**buildings**
- id (primary key)
- name
- address
- client_id (foreign key → clients)
- inspection_frequency (monthly, quarterly, annual)
- last_inspection_date
- next_inspection_due

[... complete schema with all tables]

### Relationships
- One building → Many inspections
- One inspector → Many inspections
- One client → Many buildings

## Feature Breakdown

### MVP Features (Phase 1) - Must-Have for Launch
**Estimated Build Time: 40-60 hours**

1. **User Authentication & Roles**
   - Admin login
   - Inspector login
   - Role-based permissions

2. **Building Management**
   - Add/edit/delete buildings
   - Store client information
   - Set inspection frequency

3. **Inspection Scheduling**
   - Create new inspections
   - Assign to inspectors
   - View upcoming inspections

4. **Basic Inspection Form**
   - Mobile-friendly checklist
   - Pass/fail items
   - Photo upload
   - Notes field

5. **Simple Dashboard**
   - Today's inspections
   - Overdue inspections
   - Inspector availability

### Phase 2 Features - Enhanced Functionality
**Estimated Build Time: 20-30 hours**

1. **PDF Report Generation**
   - Branded inspection reports
   - Photo attachments
   - Digital signatures

2. **Automated Reminders**
   - Email notifications for upcoming inspections
   - SMS alerts for inspectors
   - Client notification when inspection complete

3. **Advanced Dashboard**
   - Analytics and metrics
   - Revenue tracking
   - Inspector performance

### Phase 3 Features - Nice-to-Haves
**Estimated Build Time: 15-20 hours**

1. **Client Portal**
   - Clients can view their inspection history
   - Download past reports
   - Request new inspections

2. **Route Optimization**
   - Suggest efficient inspection routes
   - Map view of scheduled inspections

3. **Invoice Generation**
   - Automatic invoicing after inspection
   - Payment tracking

## Step-by-Step Implementation Plan

### Week 1: Foundation Setup
**Tasks for Claude Code:**

1. **Project Initialization**
   - "Set up a Next.js project with TypeScript and Tailwind CSS"
   - "Configure Supabase for database and authentication"
   - "Create basic folder structure: /components, /pages, /lib, /types"

2. **Database Setup**
   - "Create Supabase tables: users, buildings, clients, inspections"
   - "Set up row-level security policies for multi-tenant access"
   - "Create database relationships and foreign keys"

3. **Authentication**
   - "Implement Supabase authentication with email/password"
   - "Create login and signup pages"
   - "Add role-based middleware for admin vs inspector access"

### Week 2: Core Features
**Tasks for Claude Code:**

1. **Building Management**
   - "Create a buildings list page with search and filter"
   - "Build add/edit building form with client assignment"
   - "Implement CRUD operations for buildings"

2. **Inspection Scheduling**
   - "Create inspection scheduling interface"
   - "Build inspector assignment dropdown"
   - "Add calendar view of scheduled inspections"

[... detailed week-by-week breakdown continues]

## Deployment Strategy

### Recommended Hosting
- **Frontend + Backend:** Vercel (seamless Next.js deployment)
- **Database:** Supabase (managed PostgreSQL)
- **File Storage:** Supabase Storage (for photos)
- **Domain:** Client's domain via Vercel custom domains

### Deployment Steps
1. Push code to GitHub repository
2. Connect Vercel to GitHub repo
3. Configure environment variables in Vercel
4. Deploy production build
5. Set up custom domain (client's domain)

### Estimated Costs
- **Hosting:** $20/month (Vercel Pro + Supabase Pro)
- **Domain:** $12/year
- **Total Monthly Cost:** ~$20-25

## Testing & Quality Assurance

### Pre-Launch Checklist
- [ ] All user roles tested (admin, inspector)
- [ ] Mobile responsiveness verified
- [ ] Forms validate correctly
- [ ] Database backups configured
- [ ] Error handling implemented
- [ ] Loading states on all actions
- [ ] Client data secure and isolated

## Handoff to Client

### Training Materials Needed
- Admin user guide (how to add buildings, schedule inspections)
- Inspector user guide (how to complete inspections on mobile)
- Video walkthrough of core features

### Support Plan
- 30-day bug fix guarantee included
- Optional monthly maintenance package ($500-1500/month)

## Project Timeline Summary

**Total Estimated Build Time:** 75-110 hours
- MVP (Phase 1): 40-60 hours → 2-3 weeks
- Phase 2: 20-30 hours → 1-2 weeks
- Phase 3: 15-20 hours → 1 week

**Realistic Client Timeline:** 4-6 weeks from kickoff to launch

## Pricing Recommendation

Based on complexity and value delivered:
- **MVP Only:** $12,000 - $15,000
- **MVP + Phase 2:** $18,000 - $22,000
- **Full Build (All Phases):** $25,000 - $35,000

**Justification:**
- Saves 2 hours/day × 5 inspectors = 50 hours/week saved
- At $30/hour labor cost = $1,500/week saved
- Software pays for itself in 10-15 weeks
- Annual savings: $78,000

## Next Steps

1. **Review this blueprint with client** - Confirm it matches their needs
2. **Prioritize features** - Decide which phase to start with
3. **Sign contract** - Lock in scope and pricing
4. **Begin development** - Use this CLAUDE.md file to guide Claude Code
5. **Weekly check-ins** - Show progress and get feedback

---

**This blueprint is ready to use as your CLAUDE.md project instruction file. Simply copy this into your project and start building with Claude Code.**
```

## Best Practices

### When Creating Blueprints

**DO:**
- ✅ Ask clarifying questions about edge cases
- ✅ Identify technical constraints early (integrations, compliance)
- ✅ Break complex features into smaller, buildable pieces
- ✅ Include realistic time estimates
- ✅ Suggest phased delivery to reduce risk
- ✅ Think about mobile/tablet usage patterns
- ✅ Consider data security and privacy

**DON'T:**
- ❌ Over-engineer the solution
- ❌ Suggest bleeding-edge tech without justification
- ❌ Promise features that require custom hardware
- ❌ Ignore scalability for growing businesses
- ❌ Forget about user roles and permissions

### Common Business Problem Patterns

**Scheduling & Dispatch:**
- Field service businesses (HVAC, plumbing, inspections)
- Healthcare appointments
- Delivery route management

**Inventory & Asset Tracking:**
- Construction equipment
- Rental businesses
- Warehouse management

**Client/Project Management:**
- Agencies and consultancies
- Freelancer workflow
- Contractor job tracking

**Form Digitization:**
- Replace paper forms with mobile data collection
- Inspection checklists
- Audit and compliance reports

**Internal Tools:**
- Employee time tracking
- Resource allocation
- Approval workflows

## Output Quality Standards

Every blueprint must include:
- ✅ Clear problem statement
- ✅ Complete database schema
- ✅ Phased feature breakdown with time estimates
- ✅ Specific tech stack with reasoning
- ✅ Step-by-step implementation plan
- ✅ Realistic pricing recommendation
- ✅ ROI calculation for client justification

## Integration with Development Workflow

This blueprint becomes your **CLAUDE.md file** for the actual build:

1. **Save blueprint as CLAUDE.md** in project root
2. **Open Claude Code** and reference this file
3. **Copy/paste tasks** from implementation plan
4. **Build feature by feature** following the blueprint
5. **Check off completed items** as you progress

## Remember

You're not just creating a technical specification - you're creating a **business plan** for a software product. Every feature should solve a real problem and deliver measurable value. The blueprint should make the client say: "Yes, this is exactly what we need, and it's worth $15K."
