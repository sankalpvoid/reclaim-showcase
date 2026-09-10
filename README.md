<div align="center">
  <a href="https://reclaim-app-tawny.vercel.app/">
    <img src="https://raw.githubusercontent.com/sankalpvoid/reclaim-showcase/main/assets/hero.svg" width="100%" alt="Reclaim — behavior change companion for reducing and quitting smoking" />
  </a>
</div>

<br>

<div align="center">
  <a href="https://reclaim-app-tawny.vercel.app/"><b>Launch Reclaim ↗</b></a>
  &nbsp;&nbsp;·&nbsp;&nbsp;
  <a href="https://github.com/sankalpvoid">sankalpvoid</a>
</div>

<br>

# Reclaim

**Reclaim is a behavior-change companion for people trying to reduce or quit smoking.**

The product is built around a simple idea: quitting is not one decision. It is a sequence of difficult moments, changing motivation, repeated triggers, small wins and imperfect days.

Reclaim tries to make those moments easier to understand and act on — without turning progress into a guilt loop.

> This repository is a **public product case study**. The production source code and backend configuration remain private.

## The problem

Most smoking trackers are good at counting days or cigarettes. That is useful, but it only describes what already happened.

The more interesting product question is:

**What can the app do at the exact moment someone is struggling — and what can it learn from that moment afterward?**

That changes Reclaim from a counter into a feedback system.

<div align="center">
  <img src="https://raw.githubusercontent.com/sankalpvoid/reclaim-showcase/main/assets/journey.svg" width="100%" alt="Reclaim product loop" />
</div>

## Product principles

**Meet people where they are.** Reclaim supports three journeys — **Quit, Reduce and Track** — instead of assuming everyone is ready for the same commitment.

**Make progress visible, not performative.** Time smoke-free, cigarettes avoided, money saved and recovery milestones exist to create context rather than pressure.

**Treat cravings as data.** A craving is not only something to survive; over time it can reveal patterns around timing, mood, triggers and which coping tools actually help.

**Support imperfect behavior.** The product is designed around retries, partial days, changing plans and offline moments rather than assuming a perfectly linear journey.

## What exists today

<div align="center">
  <img src="https://raw.githubusercontent.com/sankalpvoid/reclaim-showcase/main/assets/system.svg" width="100%" alt="Reclaim product system" />
</div>

The current prototype includes:

- **Quit / Reduce / Track journeys** with different progress logic
- **daily mood and context check-ins**
- a **craving toolkit** with guided coping exercises and timers
- **recovery milestones**, smoke-free time and savings estimates
- **personalized insights** derived from recent behavior
- **Community Circles** organized around stages of the journey
- onboarding, authentication and returning-user flows
- a **local-first experience** with cloud synchronization for supported data
- product analytics, accessibility improvements and responsive mobile behavior

## A few product decisions I care about

### 1. Reduce is not treated as failed quitting

Some users are ready to stop immediately. Others are not. Reclaim treats reduction as a legitimate structured journey with targets, recorded days and periodic reviews rather than hiding it behind a quit-only interface.

### 2. Partial data should not pretend to be certainty

A half-recorded day is different from a completed day. Reduction reviews distinguish confirmed days from incomplete or untracked days so the product does not reward or punish users using misleading data.

### 3. Useful insights should come from behavior, not generic motivation

The goal is for Reclaim to eventually say things like:

- evenings tend to be harder than mornings
- a particular coping tool has helped repeatedly
- cravings appear more often after certain moods or situations

That is more valuable than another motivational quote.

### 4. Offline resilience matters

Behavior-change tools are used in real life, not ideal network conditions. Reclaim keeps core interactions local-first where possible and synchronizes supported records when the account/backend is available.

## System architecture

The current application is intentionally lightweight on the client while the product is still evolving.

```text
Browser / mobile web
        │
        ├── local state + offline-friendly interactions
        │
        ├── behavior / journey logic
        │
        ├── personalization + analytics events
        │
        └── Supabase client
                 │
                 ├── authentication
                 ├── user-owned application data
                 ├── community features
                 └── row-level security

Deployment: Vercel
```

**Current working set:** JavaScript · HTML/CSS · Supabase · PostgreSQL · Vercel · product analytics · automated regression tests

The private production repository also includes verification scripts, security cleanup, least-privilege database policies and browser-level test coverage for important flows.

## Safety and product responsibility

Reclaim is a **support tool, not medical treatment or a substitute for professional care**. Health and recovery content is framed as general guidance and estimates rather than individualized medical claims.

The product direction emphasizes privacy, user-owned data access, explicit moderation controls for community features, and conservative handling of sensitive behavioral information.

## Current build status

**Live prototype:** active development

**Strongest areas today:** core journeys, behavioral logging, recovery/progress surfaces, craving support, Supabase foundation and product experimentation.

**Currently improving:** dashboard personalization, quality of insights, responsive consistency, accessibility, analytics coverage, privacy UX and maintainability of the frontend architecture.

## What is next

The roadmap is less about adding more screens and more about making the existing system smarter and calmer:

1. make the dashboard adapt to what matters **today**
2. turn logs/check-ins into genuinely useful behavioral insights
3. learn which craving tools help each user most
4. deepen recovery and progress context without overstating health claims
5. continue simplifying the frontend and hardening security, accessibility and reliability

## Why I built it

Reclaim started as an app idea and gradually became a broader product exercise in **behavior change, systems thinking, interface design and software engineering**.

The interesting part is not the cigarette counter.

It is the question underneath it:

**Can software understand enough context to help someone make one better decision at the right moment?**

<br>

<div align="center">
  <a href="https://reclaim-app-tawny.vercel.app/"><b>Open the live prototype ↗</b></a>
</div>

<br>

---

<sub>Designed and built by <a href="https://github.com/sankalpvoid">Sankalp Kushwaha / sankalpvoid</a> · private source, public case study</sub>
