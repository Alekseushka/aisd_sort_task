---
title: Multi-level Custom Sorting
weight: 2
authors:
- Гонцаревич Алексей
created: 2025
---

Main Concept: Sorting with multiple comparison criteria, where each subsequent criterion applies only when previous ones are equal.

## Key Elements:

    Comparator - object defining element order

    Criteria Priority - strict sequence of condition checks

    Stability - preserving relative order of equal elements

## Algorithm:

if (criterion1 ≠) → return comparison by criterion1
else if (criterion2 ≠) → return comparison by criterion2
else → return comparison by criterion3

Complexity: O(n log n) time, O(n) space

## Comparator with three comparison levels

Arrays.sort(array, (a, b) -> {
    // Level 1: Primary criterion
    int primary = Integer.compare(metric1(a), metric1(b));
    if (primary != 0) return primary;
    
    // Level 2: Secondary criterion  
    int secondary = Integer.compare(metric2(a), metric2(b));
    if (secondary != 0) return secondary;
    
    // Level 3: Tertiary criterion
    return Integer.compare(a, b);
});

