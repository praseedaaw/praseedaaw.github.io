 ---
title: Where Should You Start with Shift-Left Testing?
date: 2025-06-07T22:33:38+02:00
lastmod: 2025-06-07T22:33:38+02:00
author: Praseeda Achuthawarrier
avatar: /img/avatarnew.png
# authorlink: https://author.site
cover: /img/discovery-quality.png
images:
 - /img/wopee.png
categories:
  - QA Automation
tags:
  - Artificial Intelligence
  - QA
  - Playwright
# nolastmod: true
draft: false
---

# Where Should You Start with Shift-Left Testing? Discovery or Delivery?

<!--more-->

When I first started crafting testing strategies, I often wondered:  
**Where should shift-left testing begin — unit testing or Discovery?**

After observing challenges in my professional life, the answer became clear.

---

## The Problem: Late Testing, Repeated Questions

In many Agile teams, testing typically starts during grooming. But here's what I noticed:

- Frequent developer syncs to clarify requirements  
- Bugs linked to **missed requirements**  
- Prolonged grooming meetings with repeated questions from Product, UX, Devs, and QAs

This revealed the real issue:  
> **Testing was starting too late. It should begin during Discovery.**

---

## How to Shift Left Effectively

### 1. Move Testing to Pre-Grooming

**Grooming is too late** to validate requirements. A better approach is to start earlier — during Pre-grooming — using lightweight collaboration frameworks like:

#### 🔍 A. Behaviour-Driven Development (BDD) and the "3 Amigos"

BDD is often mistaken for just test automation tools like Cucumber. But in reality, it's a **mindset** — focusing on the **user’s perspective** throughout development.

Use the **3 Amigos** format — a pre-grooming meeting involving one person each from Product, Development, and QA. This session defines stories using **Gherkin syntax**:

```
Given <precondition>, When <action>, Then <expected outcome>
```

This approach:
- Encourages shared understanding
- Keeps discussions user-focused
- Reduces ambiguity before grooming

#### 🎨 B. Visual Acceptance Testing with Model-Based Testing (MBT)

Another strong addition to early testing is **Model-Based Testing**:

- Create **visual models** of the system during Discovery  
- Generate **optimal test cases** automatically using tools  
- Embed **system and test design** into product development from day one

This visual-first approach boosts collaboration and testability awareness early in the cycle. 

Like these there are some frameworks to help with adding quality early on. If it is a win in your team, this can even be propagated to further phases of testing - unit, integration & E2E.

---

## So, Where to Start?

Not at grooming. Not even at pre-grooming.

> **Quality should start at Discovery** — where the problem is known, but the solution is yet to be shaped.

Early testing helps evaluate:
- The **value to users**
- **Business impact**
- **Testability** of proposed solutions

To embed **quality and collaboration** right from the Discovery phase, consider adopting these lightweight frameworks and practices:

### 🔧 Frameworks & Practices for Quality in Discovery:
- **3 Amigos BDD sessions** – Mini discussions among Product, Dev, and QA to shape stories early  
- **Example Mapping** – Break down user stories with examples, rules, and questions  
- **Impact Mapping** – Visualize how features drive business goals and user behavior  
- **Model-Based Testing (MBT)** – Design system flows early and generate optimal tests  
- **Specification by Example (SBE)** – Use shared examples to define and validate behavior  
- **Pre-mortem workshops** – Proactively explore what could go wrong before solutioning  
- **Testing Personas** – Include QA in defining edge cases from real user perspectives

These practices encourage shared understanding, testability-driven design, and reduce last-minute surprises in delivery.

---

## Final Takeaway

> **Shift-left testing starts with Discovery.**  
> That’s where true quality begins — with shared thinking, early validation, and aligned goals.

---

## But Isn’t This a Lot of Extra Work?

Should we be afraid of adding these steps, because they *look like a lot*?

**Absolutely not.**  
A **30-minute planned meeting** during Discovery is far more valuable than a **2-hour unplanned firefight** during delivery.

> Prevention is better than cure. 🙂

And let’s not forget — we’re in the **AI era**. Many of these activities can soon be **assisted or even facilitated by intelligent bots**, making early collaboration even easier and smarter.

So let’s lean in, not hold back.  
Start early. Collaborate better. Deliver quality with confidence.
