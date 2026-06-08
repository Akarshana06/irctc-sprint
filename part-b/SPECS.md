# IRCTC Feature Specifications – Part B

## Feature Spec 1: Tatkal Virtual Queue System

### Problem Statement

In Part A, Problem 1 identified that Tatkal booking becomes unreliable during peak demand due to thousands of users attempting to book simultaneously. This causes slow response times, booking failures, and user frustration.

### Current State (from Part A)

Users search trains, select Tatkal quota, enter passenger details, and submit booking requests at opening time. The system often becomes slow or unresponsive during request submission.

### Proposed Solution

Introduce a Virtual Queue System. Instead of allowing all users to submit requests simultaneously, users are assigned queue positions and provided real-time status updates.

### Proposed User Flow

1. User selects Tatkal quota.
2. User clicks Book Now.
3. User joins virtual queue.
4. Queue number is displayed.
5. Estimated waiting time is shown.
6. User receives turn notification.
7. Booking form opens.
8. User completes booking.

### Technical Implementation Plan

**System Components Affected**

* Booking Service
* Queue Management Service
* Notification Service

**New Data Requirements**

* Queue ID
* User Position
* Estimated Wait Time

**API Changes**

* POST /tatkal/queue
* GET /tatkal/status

**Frontend Changes**

* Queue Status Screen
* Progress Indicator

### Success Metrics

* 50% reduction in booking failures
* 80% reduction in page refreshes
* Improved user satisfaction

### Edge Cases and Constraints

* Queue server failure
* User disconnects during waiting
* High concurrency spikes

---

## Feature Spec 2: Smart Filter Management

### Problem Statement

Part A identified that users struggle to understand active filters and verify whether results reflect their selected conditions.

### Current State

Users apply multiple filters and manually inspect train results.

### Proposed Solution

Introduce Active Filter Chips with clear visual indicators.

### Proposed User Flow

1. User applies filters.
2. Active filter chips appear above results.
3. User can remove filters individually.
4. Results update instantly.

### Technical Implementation Plan

**System Components Affected**

* Search Service
* Filter Service

**New Data Requirements**

* Active Filter State

**API Changes**

* Enhanced search parameters

**Frontend Changes**

* Filter Chips
* Clear All Filters button

### Success Metrics

* 30% faster search completion
* Reduced filter confusion

### Edge Cases

* Multiple filter combinations
* Empty result sets

---

## Feature Spec 3: Unified Navigation Dashboard

### Problem Statement

Part A found that important services such as PNR status and cancellations are difficult to locate.

### Current State

Users navigate through multiple menus and dropdowns.

### Proposed Solution

Create a Dashboard containing all common railway services in one place.

### Proposed User Flow

1. User opens homepage.
2. User sees Quick Actions Dashboard.
3. User selects PNR, Cancellation, Refund, or TDR.
4. Desired service opens immediately.

### Technical Implementation Plan

**System Components**

* Homepage
* Navigation Service

**Frontend Changes**

* Quick Actions Panel
* Service Categories

### Success Metrics

* Faster task completion
* Reduced navigation clicks

### Edge Cases

* Mobile responsiveness
* Service availability

---

## Feature Spec 4: Alternative Journey Recommendation System

### Problem Statement

Users see NOT AVAILABLE or WL status but receive no assistance.

### Current State

Users manually search alternative trains and dates.

### Proposed Solution

Recommend nearby dates, trains, and stations automatically.

### Proposed User Flow

1. User searches train.
2. Train unavailable.
3. Recommendation panel appears.
4. User selects alternative.
5. Booking continues.

### Technical Implementation Plan

**System Components**

* Search Service
* Recommendation Engine

**New Data Requirements**

* Historical availability
* Alternative routes

**API Changes**

* GET /recommendations

### Success Metrics

* Increased booking completion rate
* Reduced abandoned searches

### Edge Cases

* No alternatives available
* Outdated availability data

---

## Feature Spec 5: Collapsible Filter Drawer

### Problem Statement

The filter panel consumes excessive screen space.

### Current State

Filters remain permanently visible.

### Proposed Solution

Convert filters into a collapsible drawer.

### Proposed User Flow

1. User opens search results.
2. Filters remain collapsed.
3. User expands filters when needed.
4. Results receive more space.

### Technical Implementation Plan

**System Components**

* Search Results UI

**Frontend Changes**

* Filter Drawer
* Expand/Collapse Button

### Success Metrics

* More visible train results
* Reduced scrolling

### Edge Cases

* Accessibility
* Small screens

---

## Feature Spec 6: Persistent Berth Preference System

### Problem Statement

Users are unsure whether berth preferences remain saved.

### Current State

Selected berth preferences may appear lost during booking.

### Proposed Solution

Display berth preferences throughout the booking journey.

### Proposed User Flow

1. User selects berth preference.
2. Preference is saved instantly.
3. Confirmation badge displayed.
4. Preference visible on review page.

### Technical Implementation Plan

**System Components**

* Passenger Service
* Booking Service

**New Data Requirements**

* Saved berth preference

**Frontend Changes**

* Preference Confirmation Badge

### Success Metrics

* Reduced booking confusion
* Improved passenger confidence

### Edge Cases

* Preference unavailable
* Coach allocation changes
