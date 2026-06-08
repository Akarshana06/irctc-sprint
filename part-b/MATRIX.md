# Impact vs Effort Matrix

## The Matrix

|                 | Low Effort                                                                                | High Effort                                                         |
| --------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **High Impact** | Smart Filter Management, Unified Navigation Dashboard, Persistent Berth Preference System | Tatkal Virtual Queue System, Smart Journey Recommendation Assistant |
| **Low Impact**  | Collapsible Filter Drawer                                                                 | None                                                                |

---

## How I Scored Each Dimension

### Impact Scoring (1–5)

I scored Impact based on:

* Number of users affected
* Frequency of occurrence
* Whether the issue exists in the booking flow
* Consequence when the issue occurs

### Effort Scoring (1–5)

I scored Effort based on:

* Number of system components affected
* Backend complexity
* API dependencies
* Infrastructure requirements
* Risk of disrupting existing services

---

## Placement Justifications

### Tatkal Virtual Queue System — High Impact / High Effort

Tatkal booking affects a large number of users every day and directly impacts successful ticket purchases. Implementing a virtual queue requires backend infrastructure, real-time updates, and queue management services. Because of its significant user impact, this feature should be treated as a strategic investment.

---

### Smart Filter Management — High Impact / Low Effort

Search filters are used by nearly every passenger searching for trains. The proposed solution mainly requires frontend improvements and minimal backend changes. This makes it a quick win that improves usability for a large audience.

---

### Unified Navigation Dashboard — High Impact / Low Effort

Navigation issues affect all users entering the platform. The solution primarily involves restructuring existing UI components rather than building new infrastructure. It provides significant usability gains with relatively low implementation effort.

---

### Smart Journey Recommendation Assistant — High Impact / High Effort

Users frequently encounter unavailable seats and receive little guidance. Building recommendation systems requires AI integration, historical data analysis, and additional backend services. The effort is high but the potential impact on booking success is substantial.

---

### Collapsible Filter Drawer — Low Impact / Low Effort

This issue affects usability rather than booking success. The implementation mainly involves UI changes and responsive layout improvements. Although useful, it does not solve a critical booking problem.

---

### Persistent Berth Preference System — High Impact / Low Effort

Passengers with berth preferences rely on clear booking confirmation. The solution mainly requires state persistence and UI visibility improvements. It provides strong trust benefits while requiring relatively small development effort.

---

## Recommended Sprint Order

### Sprint 1 (Quick Wins)

1. Smart Filter Management
2. Unified Navigation Dashboard
3. Persistent Berth Preference System

### Sprint 2 (Usability Improvements)

4. Collapsible Filter Drawer

### Sprint 3 (Strategic Features)

5. Tatkal Virtual Queue System
6. Smart Journey Recommendation Assistant

---

## Final Recommendation

The first sprint should focus on solving high-impact, low-effort issues because they improve user experience quickly with minimal engineering risk. Once those improvements are deployed, development resources can shift toward larger initiatives such as Tatkal Queue Management and AI-powered recommendations.
