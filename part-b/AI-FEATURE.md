# AI Feature Specification: Smart Journey Recommendation Assistant

## Problem It Solves

This feature addresses **Problem 4: Availability Information Is Not Actionable** from Part A.

During exploration of IRCTC, train results frequently displayed statuses such as "NOT AVAILABLE", "REGRET", or waiting list numbers. Users were informed about the problem but were not guided toward alternative booking options. This resulted in repeated searches, higher frustration, and booking abandonment.

## Proposed Feature — User Perspective

When a user searches for trains and encounters unavailable seats, the platform automatically displays AI-generated recommendations.

Instead of only showing:

* NOT AVAILABLE
* WL13
* REGRET

The system additionally shows:

* Alternative trains
* Alternative travel dates
* Nearby boarding stations
* Predicted confirmation probability
* Fastest available route

The user can select one of the recommendations and continue booking without repeating the search process.

## Model or API Choice

### Google Vertex AI Gemini

Reason:

* Strong reasoning capability
* Handles structured railway data effectively
* Easily integrates with recommendation workflows
* Supports future multilingual expansion

Alternative options considered:

* OpenAI GPT-4
* Custom XGBoost Recommendation Engine

Gemini was selected because it can combine availability data, route information, and user context into understandable recommendations.

## Training or Input Data

### Required Data

* Historical train occupancy data
* Waiting list progression data
* PNR confirmation history
* Route and timetable information
* Station metadata
* Seasonal demand patterns

### Data Sources

* IRCTC booking database
* Railway availability APIs
* Historical reservation datasets

### Availability

Most operational data already exists within IRCTC systems and can be reused.

## How Output Is Shown to the User

Example:

---

## Suggested Alternatives

✓ Train 12137
Seats Available Tomorrow

✓ Train 12870
WL3 | 82% Confirmation Chance

✓ Travel on June 7
Confirmed Seats Available

✓ Nearby Station Option
Board from Lokmanya Tilak Terminus

---

The recommendation panel appears directly below the availability section.

Users can click any recommendation and continue booking immediately.

## Confidence Threshold and Fallback

### Show AI Recommendation

Confidence ≥ 70%

### Fallback

If confidence falls below 70%:

"Alternative recommendations currently unavailable. Please try another date or route."

The system then falls back to standard search functionality.

## Success Metrics

* 25% reduction in abandoned searches
* 20% increase in successful bookings
* Reduced repeated searches per user
* Higher user satisfaction scores

## Limitations and Risks

### Risks

* Incorrect confirmation predictions
* Sudden demand spikes affecting accuracy
* Incomplete historical data

### Mitigation

* Display confidence score
* Update predictions frequently
* Use fallback recommendations when confidence is low

### Constraint

Recommendations should assist users but must not guarantee ticket confirmation.
