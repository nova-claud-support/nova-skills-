---
name: database-schema-design
description: Model relational data with clear entities, constraints, indexes, and migration strategies.
---

# Database Schema Design

## Purpose
Create relational schemas that preserve data integrity and support expected query patterns.

## Workflow
1. Gather entities, business rules, relationships, and expected data volume.
2. Define tables with stable primary keys and appropriate data types.
3. Model relationships with foreign keys and explicit delete/update behavior.
4. Add NOT NULL, UNIQUE, CHECK, and other constraints for enforceable rules.
5. Normalize to reduce duplication; denormalize only with a documented performance reason.
6. Design indexes from measured or expected query patterns, avoiding indiscriminate indexing.
7. Define migration and rollback considerations before changing production schemas.
8. Test constraints, representative queries, and migration behavior using synthetic data.

## Validation
- [ ] Every table has a clear purpose and key.
- [ ] Relationships and delete behavior are intentional.
- [ ] Constraints enforce important invariants.
- [ ] Indexes support real query patterns.
- [ ] Migrations preserve existing data or document transformations.

## Safety
Use parameterized queries. Never place credentials or real personal data in schema examples or test fixtures.
