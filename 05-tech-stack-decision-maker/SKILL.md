---
name: tech-stack-decision-maker
description: Get confident tech stack recommendations for any software project based on requirements, with justification for each choice, Claude Code prompts to build with that stack, deployment strategy, and cost breakdown.
---

# Tech Stack Decision Maker

Stop guessing. Get confident tech recommendations backed by reasoning.

## What This Skill Does

You describe the project requirements, and this skill recommends:

✅ **Exact Tech Stack** - Specific technologies for frontend, backend, database, hosting
✅ **Why Each Choice** - Clear reasoning tied to project needs
✅ **Claude Code Prompts** - Ready-to-use prompts for building with this stack
✅ **Deployment Strategy** - Where and how to host
✅ **Cost Breakdown** - What it will cost the client monthly/annually
✅ **Alternatives** - When to consider different options

## Who This Is For

**Software Tailors** who:
- Feel overwhelmed by technology choices
- Want to make confident recommendations to clients
- Need to justify tech decisions professionally
- Want to use modern, AI-friendly tech stacks
- Avoid picking the wrong stack and having to rebuild

## How To Use This Skill

### Input Format

**Example Input:**
```
Project: Fire inspection management system

Requirements:
- Web app for office staff (desktop primarily)
- Mobile-friendly interface for field inspectors
- User authentication with different roles (admin, inspector)
- Database for buildings, inspections, users
- File uploads (photos from inspections)
- PDF report generation
- Email notifications
- Real-time dashboard

Expected Users: 10-15 concurrent users max
Data Volume: ~200 inspections/month, growing slowly
Budget: Mid-range (client can afford hosting, but not enterprise costs)
Timeline: Need to launch in 4-6 weeks
```

### Output Format

---

## Tech Stack Recommendation: Fire Inspection Management System

### Recommended Stack (Modern & AI-Friendly)

```
Frontend:     Next.js 14 (React framework)
Backend:      Next.js API Routes
Database:     PostgreSQL (via Supabase)
Auth:         Supabase Auth
File Storage: Supabase Storage
Hosting:      Vercel
Styling:      Tailwind CSS
```

---

### Why This Stack?

#### ✅ Next.js 14 (Frontend + Backend)

**Reasons:**
- **All-in-one:** Frontend and backend in one codebase (simpler for Claude Code to build)
- **Fast development:** React components + built-in routing = quick builds
- **Mobile-friendly:** Responsive by default
- **SEO-ready:** Server-side rendering if needed
- **Claude Code loves it:** Widely documented, Claude handles it perfectly

**Perfect for:** Projects that need both a web interface and API logic

**Alternative:** Separate React + Express if you need API used by multiple frontends

---

#### ✅ PostgreSQL (via Supabase)

**Reasons:**
- **Relational data:** Your project has clear relationships (buildings → inspections → users)
- **Robust:** Handles complex queries, transactions, data integrity
- **Supabase = managed:** No database administration headaches
- **Built-in features:** Real-time subscriptions, row-level security, auto-generated REST API
- **Affordable:** Free tier for small projects, $25/month for production

**Perfect for:** Projects with structured data and relationships

**Alternative:** MongoDB if data structure is super flexible/undefined

---

#### ✅ Supabase (Auth + Storage + Database)

**Reasons:**
- **Complete backend:** Auth, database, storage all in one
- **Fast setup:** No backend server to configure
- **Secure by default:** Row-level security policies protect data
- **File storage included:** Photo uploads handled easily
- **Great docs:** Claude Code knows how to integrate it

**Perfect for:** Projects that don't need complex custom backend logic

**Alternative:** Firebase (similar features, Google ecosystem) or custom backend if complex logic

---

#### ✅ Vercel (Hosting)

**Reasons:**
- **Made for Next.js:** Seamless deployment (literally one click)
- **Automatic deployments:** Push to GitHub = instant deploy
- **Edge network:** Fast globally (CDN built-in)
- **Free tier:** Generous (perfect for small projects)
- **Easy custom domains:** Client's domain setup is trivial

**Perfect for:** Next.js projects (it's made by the same company)

**Alternative:** Railway or Render if using non-Next.js stack

---

#### ✅ Tailwind CSS (Styling)

**Reasons:**
- **Fast styling:** Utility classes = rapid UI development
- **Responsive built-in:** Mobile-friendly by default
- **Consistent design:** Design system in your HTML
- **Claude Code's preference:** Most AI code generation uses Tailwind

**Perfect for:** Fast prototyping and modern UI design

**Alternative:** Plain CSS or styled-components if you prefer

---

### Complete Tech Stack Breakdown

| Layer | Technology | Monthly Cost | Why This Choice |
|-------|-----------|-------------|-----------------|
| **Frontend** | Next.js 14 | Free (included in hosting) | All-in-one React framework, fast development |
| **Backend** | Next.js API Routes | Free (included in hosting) | Backend logic in same codebase as frontend |
| **Database** | PostgreSQL (Supabase) | $25 | Relational data, managed service |
| **Authentication** | Supabase Auth | Included | Secure user login, role-based access |
| **File Storage** | Supabase Storage | Included | Photo uploads for inspections |
| **Hosting** | Vercel | $20 (Pro plan) | Seamless Next.js deployment |
| **Domain** | Custom domain | $12/year (~$1/month) | Client's branded URL |
| **Email** | Resend or SendGrid | $0-10 | Transactional emails (notifications) |
| **Total** | | **~$46-56/month** | Mid-range, scalable |

**Annual Cost: ~$552-672/year**

---

### Claude Code Prompts for This Stack

#### 1. Project Initialization

```
Create a Next.js 14 project with TypeScript, Tailwind CSS, and ESLint.
Use the App Router (not Pages Router).
Set up folder structure: /app, /components, /lib, /types, /public.
```

#### 2. Supabase Setup

```
Install Supabase client library.
Create a Supabase project and get the project URL and anon key.
Set up environment variables for NEXT_PUBLIC_SUPABASE_URL and NEXT_PUBLIC_SUPABASE_ANON_KEY.
Create a Supabase client utility function in /lib/supabase.ts.
```

#### 3. Database Schema

```
In Supabase, create the following PostgreSQL tables:
- users (id, email, role, created_at)
- buildings (id, name, address, client_name, inspection_frequency, created_at)
- inspections (id, building_id, inspector_id, scheduled_date, status, notes, created_at)

Set up foreign key relationships:
- inspections.building_id → buildings.id
- inspections.inspector_id → users.id

Create row-level security (RLS) policies so users can only see their own data.
```

#### 4. Authentication

```
Implement Supabase authentication with email/password.
Create a login page at /login and signup page at /signup.
Add middleware to protect routes (redirect to /login if not authenticated).
Store user session in cookies for persistence.
```

#### 5. Dashboard Page

```
Create a dashboard page at /dashboard.
Show today's inspections, upcoming inspections, and overdue inspections.
Use Supabase to fetch data with real-time subscriptions.
Style with Tailwind CSS - use cards and a clean layout.
```

#### 6. Buildings Management

```
Create a page at /buildings that shows a list of all buildings.
Add search and filter functionality.
Create a form to add/edit buildings with fields: name, address, client_name, inspection_frequency.
Implement CRUD operations using Supabase.
```

#### 7. Inspection Scheduling

```
Create an inspection scheduling page at /inspections/new.
Form fields: building (dropdown), inspector (dropdown), scheduled_date (date picker).
On submit, create a new inspection record in Supabase.
Show success notification and redirect to dashboard.
```

#### 8. File Uploads

```
Add photo upload functionality to inspection forms.
Use Supabase Storage to handle file uploads.
Create a storage bucket called "inspection-photos".
Allow inspectors to upload multiple photos per inspection.
Display uploaded photos in a grid with lightbox functionality.
```

#### 9. PDF Report Generation

```
Install @react-pdf/renderer library.
Create a PDF template for inspection reports that includes:
- Company logo and branding
- Building and client information
- Inspection details and results
- Photos (if any)
Generate PDF on demand when user clicks "Download Report" button.
```

#### 10. Email Notifications

```
Install Resend library for sending emails.
Create API route at /api/send-email.
Send email when:
- Inspection is scheduled (notify inspector)
- Inspection is completed (notify client)
Use email templates with dynamic data (building name, date, etc).
```

---

### Deployment Steps

#### Step 1: Push to GitHub
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin [your-github-repo-url]
git push -u origin main
```

#### Step 2: Connect Vercel
1. Go to vercel.com and sign up
2. Click "Import Project"
3. Connect your GitHub repository
4. Vercel auto-detects Next.js and configures build settings

#### Step 3: Add Environment Variables in Vercel
- `NEXT_PUBLIC_SUPABASE_URL` = [your Supabase project URL]
- `NEXT_PUBLIC_SUPABASE_ANON_KEY` = [your Supabase anon key]
- `RESEND_API_KEY` = [your Resend API key]

#### Step 4: Deploy
- Vercel automatically deploys on every push to main branch
- Production URL: `your-project.vercel.app`

#### Step 5: Custom Domain
- In Vercel dashboard, go to Settings → Domains
- Add client's custom domain (e.g., `inspections.clientcompany.com`)
- Follow DNS configuration instructions

**Total Deployment Time:** 10-15 minutes

---

### When to Use Alternatives

#### Use MongoDB instead of PostgreSQL if:
- ❌ Data structure is highly variable/unpredictable
- ❌ Need extreme flexibility in schema
- ❌ Storing lots of nested JSON objects

**Example:** Social media app with diverse user-generated content

#### Use Firebase instead of Supabase if:
- ❌ Client is heavily invested in Google ecosystem
- ❌ Need Google Cloud integrations
- ❌ Want Firestore's offline-first mobile SDKs

**Example:** Mobile app that needs offline functionality

#### Use React + Express instead of Next.js if:
- ❌ Backend logic is very complex (heavy business rules)
- ❌ Need separate API consumed by mobile apps + web
- ❌ Team already knows Express well

**Example:** Complex ERP system with intricate business logic

#### Use Render/Railway instead of Vercel if:
- ❌ Using backend other than Next.js (like Django, Rails)
- ❌ Need more control over server configuration
- ❌ Want to host database and app on same platform

**Example:** Python/Django project

---

### Stack Complexity Levels

#### 🟢 Beginner-Friendly (Recommended for new software tailors)

**Stack:** Next.js + Supabase + Vercel + Tailwind
**Why:** Minimal configuration, great docs, Claude Code handles it perfectly
**Best for:** 80% of B2B software projects

#### 🟡 Intermediate

**Stack:** React + Node.js/Express + PostgreSQL + AWS/Railway
**Why:** More control, separate frontend/backend
**Best for:** Projects with complex backend logic or existing infrastructure

#### 🔴 Advanced (Avoid unless necessary)

**Stack:** Custom microservices + GraphQL + Kubernetes + AWS
**Why:** Overkill for most projects, high maintenance
**Best for:** Enterprise systems with huge scale requirements

**For software tailors:** Stick to 🟢 Beginner-Friendly unless client has specific needs

---

### Tech Stack Red Flags

**Avoid these unless you have good reason:**

❌ **PHP/WordPress** - Outdated, hard to maintain, Claude Code struggles with it
❌ **Ruby on Rails** - Less common, fewer Claude Code examples
❌ **Angular** - More complex than React, steeper learning curve
❌ **MySQL** - PostgreSQL is better for modern projects
❌ **Shared hosting** - Slow, unreliable, use cloud platforms instead
❌ **Self-hosted everything** - Maintenance nightmare, use managed services

---

### Quick Stack Recommendations

**Simple CRUD App (basic data management):**
- Next.js + Supabase + Vercel
- Cost: $25-50/month
- Build time: 2-3 weeks

**Mobile-First Field Service:**
- Next.js (responsive) + Supabase + Vercel
- Consider PWA (progressive web app) before native mobile
- Cost: $25-50/month
- Build time: 3-4 weeks

**Complex Project Management:**
- Next.js + Supabase + Vercel + Advanced features (Stripe, Twilio, SendGrid)
- Cost: $50-100/month
- Build time: 6-8 weeks

**E-Commerce / Customer Portal:**
- Next.js + Supabase + Stripe + Vercel
- Cost: $50-100/month (+ Stripe fees)
- Build time: 4-6 weeks

---

## Remember

**The best tech stack is:**
1. ✅ **Simple** - Fewer moving parts = fewer bugs
2. ✅ **Well-documented** - Claude Code can help effectively
3. ✅ **Managed services** - Less maintenance = more time building
4. ✅ **Cost-effective** - Under $100/month for most B2B projects
5. ✅ **Proven** - Use battle-tested tech, not bleeding edge

**Default recommendation for 80% of projects:**
**Next.js + Supabase + Vercel + Tailwind**

This stack is modern, AI-friendly, affordable, and scalable.

Stop overthinking tech choices. Use this stack, build fast, get paid.
