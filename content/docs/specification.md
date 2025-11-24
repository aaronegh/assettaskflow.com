---
title: Asset–Task Flow Specification
weight: 3
icon: file-text
---

In the ATF framework, not all work is created equal. Every hour an engineer spends falls into one of three distinct categories. Understanding the balance between these categories is the key to strategic resource allocation.

1. Flow Tasks (Value Generation): These are tasks explicitly linked to a Business Flow.

Example: “Ingest new demographic signals for the Churn Prediction Model.”

The Reality: This is the work that shows up on the roadmap. It is the work stakeholders think we are doing 100% of the time.

2. Ad Hoc Tasks (Demand Signals): Stakeholders often bypass roadmaps for quick answers. The traditional engineering instinct is to block these requests. ATF takes a different approach: Ad Hoc is data.

The Strategy: Instead of building process walls, we track “Ad Hoc” tasks against the specific Asset they touch.

The Insight: If you see 20 ad hoc requests hitting the booking_logs table in a month, you haven’t found a nuisance; you have found a Shadow Flow. This is empirical evidence of business demand that justifies building a self-service tool or automating a formal Flow.

3. Flowless Tasks (The Operational Reality): This is the most critical category for measuring Cost of Ownership. A Flowless Task is any work required to keep an Asset operational that does not add new features.

Crucially, this is not a penalty.

In many organizations, maintenance is viewed as “fixing bugs” or “cleaning up bad code.” This is a reductive view. Flowless tasks represent the operational reality of a living system. When an asset generates a high volume of operational work, it triggers a specific diagnostic question: Is this Rot, or is this Growth?

Scenario A (Rot): A pipeline breaks weekly because the code is brittle or dependencies are circular.

Diagnosis: Technical Debt.

Action: Refactor or Deprecate.

Scenario B (Growth): A core transaction table is experiencing exponential data growth. The team is spending hours optimizing queries, partitioning storage, and scaling compute to keep up with ingestion volume.

Diagnosis: Scale.

Action: This is a signal for Infrastructure Investment.

By categorizing Flowless Tasks, we move the conversation from “why is the team so slow?” to “Asset X is growing exponentially and requires architectural investment to sustain.”