## Problem 1: Tatkal Booking Failure During Peak Hours 
What is broken

The Tatkal booking experience becomes unreliable during peak booking hours due to extremely high traffic. Users often experience slow page loads, timeouts, booking failures, and a lack of meaningful feedback about system status. The platform does not provide queue positions, estimated waiting times, or clear explanations when requests fail.

Affected Users
Emergency travelers
Students traveling for exams or admissions
Working professionals booking last-minute journeys
Daily IRCTC Tatkal users across India
Frequency
Daily
Most commonly observed during Tatkal booking windows:
10:00 AM for AC classes
11:00 AM for Non-AC classes
Screenshot Reference

#### Figure 1: assets/screenshots/tatkal-search-results.png

The screenshot shows the Tatkal train search results page after selecting source station, destination station, journey date, and Tatkal quota. Users reach this stage before attempting to book tickets during the Tatkal booking window.

Current Flow — Step by Step
User opens IRCTC before the Tatkal booking window.
User logs into their account.
User enters source and destination stations.
User selects journey date.
User chooses the Tatkal quota.
User searches for available trains.
Train results are displayed (shown in Figure 1).
User selects a train and clicks "Book Now".
Passenger details are entered.
User submits the booking request during the Tatkal opening period.
The system becomes slow, unresponsive, or returns an error.
User refreshes repeatedly while ticket availability decreases.
The ticket may move to waiting list status or become unavailable.
Where Exactly It Breaks

Step 10–11

The failure occurs when booking requests are submitted during peak Tatkal demand. Large numbers of users attempt to book simultaneously, causing server congestion and slow response times. The system provides limited feedback about request status, leaving users uncertain whether their booking is still being processed or has failed.

Impact
High user frustration during time-sensitive bookings.
Increased booking abandonment.
Repeated page refreshes create additional server load.
Loss of trust in the Tatkal booking process.

## Problem 2: Search Filters Do Not Work Reliably 
What is broken

The train search page contains multiple filters such as Journey Class, Train Type, Departure Time, and Arrival Time. While filters can be applied successfully, the system does not clearly communicate which filters are active, and users may need to repeatedly verify whether the displayed results truly match all selected filter conditions. The filter experience becomes confusing when multiple filters are selected simultaneously.

Affected Users
Passengers comparing multiple train options
First-time IRCTC users
Users searching for specific classes or train categories
Users booking Tatkal tickets under time pressure
Frequency
Frequent during train search sessions
Affects users whenever multiple filters are applied
Screenshot Reference

#### Figure 2: assets/screenshots/filters.png

The screenshot shows the train search page with multiple Journey Class and Train Type filters selected. Although filters are applied, users must manually verify whether the displayed train results satisfy all selected criteria.

Current Flow — Step by Step
User enters source and destination stations.
User selects journey date and quota.
Search results are displayed.
User applies Journey Class filters.
User applies Train Type filters.
User expects results to clearly reflect the selected filters.
User manually checks each train result.
User may become uncertain about which filters are currently affecting the displayed results.
User modifies filters repeatedly to confirm the search outcome.
Where Exactly It Breaks

Step 6–8

The system does not provide strong visual confirmation of the active filtering logic. When multiple filters are selected, users must manually inspect train cards to determine whether the results truly match their selections, increasing cognitive effort and reducing confidence in the search results.

Impact
Increased search time
Reduced trust in filtering functionality
Additional effort required to validate search results
Poor experience during time-sensitive bookings such as Tatkal

## Problem 3: Navigation and Information Architecture Complexity 

### What is broken

The IRCTC platform exposes a large number of services through the primary navigation menu, including trains, meals, loyalty programs, e-wallets, buses, flights, hotels, holidays, and promotions. Important railway-related tasks such as PNR status, ticket cancellation, refund tracking, and TDR filing are not prominently surfaced, making navigation difficult for users whose primary goal is railway booking and ticket management.

### How I Found It

While exploring the homepage and attempting to locate common railway services, I opened the "Other Services" menu and observed that many unrelated services were mixed together with railway-related functions. Finding specific tasks required additional navigation and exploration.

### Screenshot Reference

**Figure 4:** `assets/screenshots/irtc home.png`

The screenshot shows the homepage navigation structure and the expanded "Other Services" dropdown menu containing multiple service categories. The interface presents many options simultaneously, increasing navigation complexity.

### Affected Users

* First-time IRCTC users
* Elderly passengers
* Occasional railway travelers
* Users trying to access ticket management services quickly

### Frequency

* Every visit to the homepage
* Whenever users attempt to locate non-booking services

### Current Flow — Step by Step

1. User opens the IRCTC homepage.
2. User wants to perform a task such as checking PNR status, cancellation status, refund tracking, or TDR filing.
3. User scans the top navigation bar.
4. User sees multiple service categories competing for attention.
5. User opens "Other Services" to search for the required feature.
6. User browses through several unrelated options.
7. User navigates through additional menus or pages.
8. User eventually locates the desired service after multiple interactions.

### Where Exactly It Breaks

**Step 4–6**

The information architecture does not prioritize common railway-related tasks. Users must spend additional time exploring menus because important actions are not clearly grouped or surfaced according to user intent.

### Impact

* Increased navigation time
* Higher cognitive load for users
* Difficulty for first-time and elderly passengers
* Reduced discoverability of important railway services
* Less efficient user experience overall

### Severity

Medium

## Problem 4: Availability Information Is Not Actionable 

### What is broken

When train seats are unavailable, IRCTC displays statuses such as "NOT AVAILABLE", "REGRET", or waiting list numbers (WL). However, the platform does not provide meaningful guidance on what users should do next. Users are left to manually search for alternative trains, dates, or routes without any assistance from the system.

### How I Found It

While searching for trains and checking seat availability, I observed that several trains displayed "NOT AVAILABLE" and waiting list statuses. The platform informed me that seats were unavailable but did not suggest alternative options or next steps.

### Screenshot Reference

**Figure 5:** `assets/screenshots/no availability.png`

The screenshot shows multiple trains displaying "NOT AVAILABLE" and "WL13" statuses. Although the system indicates seat availability problems, it does not provide recommendations or actionable alternatives.

### Affected Users

* Tatkal passengers
* Last-minute travelers
* First-time IRCTC users
* Users with urgent travel requirements

### Frequency

* Very common during peak travel seasons
* Frequently encountered on popular routes
* Daily for users searching high-demand trains

### Current Flow — Step by Step

1. User searches for trains between two stations.
2. Train search results are displayed.
3. User checks seat availability.
4. The system displays "NOT AVAILABLE" or waiting list status.
5. User looks for alternative travel options.
6. No recommendations or guidance are provided.
7. User manually opens other trains and dates.
8. User repeats the search process multiple times.
9. User eventually finds an alternative or abandons the booking.

### Where Exactly It Breaks

**Step 5–6**

The system identifies that seats are unavailable but fails to help the user move forward. There are no suggestions for nearby dates, alternative trains, nearby stations, or estimated confirmation chances.

### Impact

* Increased booking effort
* Longer search time
* Higher user frustration
* Greater likelihood of booking abandonment
* Poor support for urgent travel planning

### Severity

Medium–High

## Problem 5: Filter Panel Occupies Excessive Screen Space [Self-Discovered]

### What is broken

The train search page dedicates a large portion of the screen to filter controls such as Journey Class, Train Type, Departure Time, Arrival Time, and Station Filters. As a result, the actual train results receive limited space, making it harder for users to compare multiple trains efficiently.

### How I Found It

While exploring train search results and applying filters, I noticed that the filter section occupied a significant portion of the page width. This reduced the amount of visible train information and required additional scrolling to compare available options.

### Screenshot Reference

**Figure 6:** `assets/screenshots/filters.png`

The screenshot shows the filter panel occupying a large section of the left side of the interface while train search results are compressed into the remaining space.

### Affected Users

* Laptop users
* Tablet users
* Frequent travelers comparing multiple trains
* Users searching across several classes and quotas

### Frequency

* Every train search session
* Especially noticeable when multiple filters are expanded

### Current Flow — Step by Step

1. User searches for trains.
2. Search results are displayed.
3. User opens or applies filters.
4. The filter panel remains permanently visible.
5. Train result cards receive reduced horizontal space.
6. Fewer train options are visible at a time.
7. User scrolls repeatedly to compare trains.
8. User spends additional time evaluating options.

### Where Exactly It Breaks

**Step 4–6**

The interface prioritizes filter visibility over train result visibility. This creates an imbalance in screen space allocation and reduces the efficiency of train comparison.

### Impact

* Reduced information density
* Increased scrolling
* Slower train comparison
* Less efficient use of available screen space
* Lower usability on smaller displays

### Severity

Medium

## Problem 6: Seat Selection Resets [Given]

### What is broken

Users can select berth preferences such as Lower Berth, Upper Berth, Side Lower, or Side Upper during the booking process. However, the selected preference may not always remain visible or may appear to reset in later booking steps, causing uncertainty about whether the preference was successfully recorded.

### Affected Users

- Senior citizens
- Families traveling together
- Pregnant passengers
- Long-distance travelers

### Frequency

Intermittent; reported more frequently on mobile devices.

### Current Flow — Step by Step

1. User searches for trains.
2. User selects a train.
3. User clicks Book Now.
4. User enters passenger details.
5. User selects berth preference.
6. User proceeds to the next booking step.
7. User reviews booking details.
8. Selected berth preference is unclear or appears reset.

### Where Exactly It Breaks

Step 6–7 during the transition from passenger details to booking review screens.

### Impact

- Reduced booking confidence
- Passenger frustration
- Additional verification effort
- Poor experience for users with specific berth requirements
