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
4. **Local commerce convenience** — order-ahead and collection for nearby coffee spots.
5. **Secure integrations** — connect approved APIs/services over time.

## 5) Entry experience and fast navigation
Design the first in-app experience around **intent-based routing** so users can reach their goal in the fewest taps.

- After login, show a simple selector: **"What are you here for?"**
  - **Something to do** (community, events, updates)
  - **Food & coffee** (order-ahead and collection)
  - **Necessities** (alerts, key local services, urgent updates)
- Save a preferred default path, but allow users to switch at any time from a persistent quick-switch control.
- Keep a global search and area switcher visible for instant navigation.

## 6) MVP feature set (Phase 1)
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

### H. Coffee order-ahead and collection (MVP extension)
- Discover nearby participating coffee brands/shops by selected area.
- Place an order for **collection/pickup** with time-slot selection.
- In-app payment and digital proof of payment for pickup.
- "Ready for collection" status updates via push notifications.
- Merchant side receives orders in a simple queue workflow (received > preparing > ready > collected).

## 7) Phase 2+ expansion
- **Property listings:** rentals/sales by area with contact actions.
- **Marketplace/service directory:** local services and professionals.
- **In-app messaging:** direct communication between users/businesses.
- **Partnership APIs:** municipality notices, weather, transport, load shedding.
- **Web dashboard for businesses/admins:** campaign and content management.
- **Delivery partnerships (optional):** extend from collection-first to delivery in selected zones.

## 8) Information architecture
- **Area > Category > Content type** model.
- Primary entities:
  - User
  - Area
  - Post
  - Event
  - Business
  - Offer/Special
  - Alert
  - Merchant
  - Menu item
  - Order
  - Payment
  - Listing (future)
  - Moderation report

## 9) UX principles
- Keep local context visible at all times (current area chip in header).
- Make intent-routing explicit at entry (Something to do / Food & coffee / Necessities).
- Make contribution fast (1–2 tap post templates).
- Make ordering fast (reorder, saved favorites, 3-tap checkout target).
- Prioritize trust cues (source label, verification, post age).
- Accessibility: readable text sizing, contrast, icon+text labels.
- Adapt area theme and recommendations as location changes, with user permission and manual override.

## 10) Suggested React Native architecture
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
- Payments integration (e.g., Peach Payments, PayFast, or Stripe where available).
- Merchant order management endpoints with real-time order status updates.

### Web app strategy
- Build web with **Next.js** sharing design system and API contracts.
- Reuse business logic between mobile and web where possible.

## 11) Security and trust baseline
- Auth: email + OTP/social sign-in.
- Device/session controls and token rotation.
- Content moderation pipeline (auto + manual review).
- Abuse prevention: rate limits, spam detection, blocked keywords.
- Data protection aligned with POPIA principles.
- Payment security baseline: PCI-compliant provider usage, tokenized payments, and auditable order logs.

## 12) Monetization options
1. Sponsored local posts (clearly labeled).
2. Business subscription tiers (analytics, boosted placement).
3. Featured event placements.
4. Coffee order commission and/or merchant SaaS fee.
5. Property listing package fees (future).

## 13) KPI framework
- Activation: % users selecting an area and following 3+ categories.
- Engagement: DAU/WAU, session length, feed interactions.
- Supply: posts per area per week, event creation rate.
- Trust: report resolution time, moderation accuracy, spam rate.
- Commercial: paid business accounts, campaign CTR.
- Commerce: order conversion rate, repeat order rate, pickup SLA adherence.

## 14) 90-day delivery roadmap (example)
### Month 1
- Product discovery interviews (residents, businesses, organizers).
- Finalize MVP scope + wireframes.
- Setup RN codebase, auth, area model, base API, and intent-based entry flow.

### Month 2
- Build feed, posting flows, events, and business specials.
- Build coffee order-ahead flow: store discovery, menu, checkout, pickup status.
- Implement moderation/reporting and admin tooling (basic).
- Closed alpha in one pilot area (e.g., Hillcrest).

### Month 3
- Improve ranking, trust signals, and onboarding.
- Optimize quick navigation and reorder journey to reduce taps/time-to-order.
- Launch beta in 2–3 nearby areas.
- Start business onboarding and first paid experiments.

## 15) Launch strategy
- Start with one high-engagement suburb/town.
- Partner with gyms, schools, and event organizers.
- Partner with 3–5 coffee shops for pickup-first pilot.
- Recruit “community champions” as early contributors.
- Weekly local highlights email + in-app digest.

## 16) Risks and mitigations
- **Low-quality content:** enforce templates + moderation + verification.
- **Cold start in new areas:** ambassadors + seeded content partnerships.
- **Misinformation:** source tags, escalation workflow, clear policy.
- **Feature creep:** strict MVP gates and monthly prioritization reviews.
- **Order reliability issues:** start with collection-only, strict merchant SLAs, and fallback refund workflows.
- **Location confusion while traveling:** clear current-area indicator, smart auto-suggest, manual lock option.

---

## Quick MVP build checklist
- [ ] Confirm pilot area and audience
- [ ] Define top 5 categories for launch
- [ ] Define entry intents and first-screen routing logic
- [ ] Build onboarding + area selection
- [ ] Build intent-based quick navigation (Something to do / Food & coffee / Necessities)
- [ ] Build area feed with ranking
- [ ] Build post/event/special creation flows
- [ ] Build coffee ordering, payment, and collection status flow
- [ ] Implement reporting and moderation tools
- [ ] Setup analytics + KPI dashboard
- [ ] Run 4-week pilot and measure retention/trust
