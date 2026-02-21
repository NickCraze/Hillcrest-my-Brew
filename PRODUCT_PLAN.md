# Hillcrest MyBrew — React Native Product Plan

## 1) Vision
Hillcrest MyBrew is a trusted hyperlocal platform for South African communities to discover what is happening nearby and contribute useful updates.

**Core purpose:** connect people, businesses, events, and trusted information in one place for each area/town.

## 2) Target users
- **Residents:** want fast local updates, events, meetups, safety notices, and trusted recommendations.
- **Community organizers:** share runs, gym challenges, charity drives, church/school events, and local announcements.
- **Small businesses:** advertise specials, promotions, and community campaigns.
- **Property stakeholders (future):** publish or browse local property listings.
- **Moderators/Admins:** ensure content quality, trust, and safety.

## 3) Value proposition
- One app for local updates instead of fragmented WhatsApp groups and social feeds.
- Verified local relevance by area-based feeds.
- Mix of community-driven content + official/trusted sources.
- Consistent experience on **mobile (React Native)** and **web app**.

## 4) Product pillars
1. **Hyperlocal feed** — area-first content discovery.
2. **Community trust** — moderation, verification, and reporting tools.
3. **Actionable local life** — events, specials, alerts, and services.
4. **Secure integrations** — connect approved APIs/services over time.

## 5) MVP feature set (Phase 1)
### A. Area onboarding
- Select country (South Africa) and town/suburb.
- Optional GPS assistance with manual override.
- Follow multiple areas (e.g., home + work).

### B. Home feed (by area)
- Tabs: **News**, **Community**, **Events**, **Specials**, **Safety**.
- Relevance ranking: distance + recency + engagement + trust score.
- Filter by date, category, and radius.

### C. Posting and contribution
- Post text, images, event cards, and basic listing cards.
- Category-based posting templates to keep structure clean.
- Business posts include offer validity dates.

### D. Events and activities
- Event detail page with date/time/location/map link.
- RSVP/Interested actions.
- Calendar integration (add to device calendar).

### E. Safety and alert updates
- Community alerts (road closures, outages, suspicious activity).
- Distinct visual treatment and urgency labels.
- Clear disclaimer + encourage official emergency channels when relevant.

### F. Trust and moderation
- Report content/users.
- Admin review queue.
- Verified badges for selected organizations/businesses.

### G. Profiles
- Personal and business profiles.
- Basic reputation signals (helpful posts, verified status).

## 6) Phase 2+ expansion
- **Property listings:** rentals/sales by area with contact actions.
- **Marketplace/service directory:** local services and professionals.
- **In-app messaging:** direct communication between users/businesses.
- **Partnership APIs:** municipality notices, weather, transport, load shedding.
- **Web dashboard for businesses/admins:** campaign and content management.

## 7) Information architecture
- **Area > Category > Content type** model.
- Primary entities:
  - User
  - Area
  - Post
  - Event
  - Business
  - Offer/Special
  - Alert
  - Listing (future)
  - Moderation report

## 8) UX principles
- Keep local context visible at all times (current area chip in header).
- Make contribution fast (1–2 tap post templates).
- Prioritize trust cues (source label, verification, post age).
- Accessibility: readable text sizing, contrast, icon+text labels.

## 9) Suggested React Native architecture
### Frontend
- **React Native (Expo)** for fast iteration.
- **TypeScript** for reliability.
- **React Navigation** for app structure.
- **TanStack Query** for server state.
- **Zustand/Redux Toolkit** for local app state (pick one).
- **NativeWind or styled-components** for consistent design tokens.

### Backend (recommended)
- **Node.js + NestJS** or **Supabase/Firebase** for initial speed.
- PostgreSQL data model with area and geo indexing.
- Object storage for media uploads.
- Role-based access control for moderators/admins.

### Web app strategy
- Build web with **Next.js** sharing design system and API contracts.
- Reuse business logic between mobile and web where possible.

## 10) Security and trust baseline
- Auth: email + OTP/social sign-in.
- Device/session controls and token rotation.
- Content moderation pipeline (auto + manual review).
- Abuse prevention: rate limits, spam detection, blocked keywords.
- Data protection aligned with POPIA principles.

## 11) Monetization options
1. Sponsored local posts (clearly labeled).
2. Business subscription tiers (analytics, boosted placement).
3. Featured event placements.
4. Property listing package fees (future).

## 12) KPI framework
- Activation: % users selecting an area and following 3+ categories.
- Engagement: DAU/WAU, session length, feed interactions.
- Supply: posts per area per week, event creation rate.
- Trust: report resolution time, moderation accuracy, spam rate.
- Commercial: paid business accounts, campaign CTR.

## 13) 90-day delivery roadmap (example)
### Month 1
- Product discovery interviews (residents, businesses, organizers).
- Finalize MVP scope + wireframes.
- Setup RN codebase, auth, area model, base API.

### Month 2
- Build feed, posting flows, events, and business specials.
- Implement moderation/reporting and admin tooling (basic).
- Closed alpha in one pilot area (e.g., Hillcrest).

### Month 3
- Improve ranking, trust signals, and onboarding.
- Launch beta in 2–3 nearby areas.
- Start business onboarding and first paid experiments.

## 14) Launch strategy
- Start with one high-engagement suburb/town.
- Partner with gyms, schools, and event organizers.
- Recruit “community champions” as early contributors.
- Weekly local highlights email + in-app digest.

## 15) Risks and mitigations
- **Low-quality content:** enforce templates + moderation + verification.
- **Cold start in new areas:** ambassadors + seeded content partnerships.
- **Misinformation:** source tags, escalation workflow, clear policy.
- **Feature creep:** strict MVP gates and monthly prioritization reviews.

---

## Quick MVP build checklist
- [ ] Confirm pilot area and audience
- [ ] Define top 5 categories for launch
- [ ] Build onboarding + area selection
- [ ] Build area feed with ranking
- [ ] Build post/event/special creation flows
- [ ] Implement reporting and moderation tools
- [ ] Setup analytics + KPI dashboard
- [ ] Run 4-week pilot and measure retention/trust
