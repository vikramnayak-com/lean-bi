## INTERVIEW 2: USER (Department HR Manager)

**Interviewee:** Michael Rodriguez, Department HR Manager (Engineering)
**Date:** November 18, 2024
**Duration:** 60 minutes

---

**Q: What is the purpose of this dashboard?**

A: I need to be able to monitor all my open positions in one place and understand where candidates are in the pipeline at any moment. Right now, I'm constantly jumping between our ATS, my email, spreadsheets, and Slack messages trying to piece together the status of 8 open positions. I need something that gives me the full picture quickly so I can focus my time on actually moving candidates through, not tracking them.

---

**Q: How does this area fit into your overall role and responsibilities?**

A: Recruiting is about 60-70% of my job right now. I'm managing anywhere from 5-10 open engineering positions at a time - everything from junior developers to senior architects. I work with hiring managers to define what they need, coordinate with our recruiting team on sourcing, schedule and track interviews, handle offer negotiations, and keep everyone informed on progress. I'm basically the orchestrator of the entire hiring process for my department.

---

**Q: What systems are the source of truth for this?**

A: Our ATS - that's where everything lives. Every candidate, every position requisition, all the stage transitions, interview feedback, offers. It's comprehensive but terrible for reporting. I can pull individual candidate profiles or position reports, but I can't easily see patterns or get the aggregate view I need to manage effectively.

---

**Q: What decisions or actions do you want to be able to take once you have this dashboard?**

A: Every morning I do a mental triage of my positions - which ones need attention today? With this dashboard, I want that triage to be instant and data-driven. If I see a position has been open for 30 days with only 2 active candidates, I know I need to push the recruiting team for more sourcing. If I see candidates piling up at the screening stage, I need to expedite phone screens. If I see our offer acceptance rate dropping, I need to flag that with my director because our compensation might not be competitive.

I also want to make smarter decisions about where to focus my sourcing efforts. If LinkedIn is working great for senior roles but employee referrals are better for junior roles, I should adjust my strategy accordingly.

---

**Q: How do you currently track this? What metrics do you track? What analyses do you do? How do you receive reports and how frequently?**

A: Honestly, it's a mess. I have a spreadsheet where I manually track each position - when it opened, how many candidates are at each stage, when the last movement happened. I update it a few times a week by pulling data from the ATS. For metrics, I track time-to-hire and number of active candidates, but it's all manual calculation. I look at where candidates are dropping off, but only when a position seems stalled - it's reactive, not proactive.

I get a weekly email report from the ATS with basic stats, but it's not actionable. It tells me I have 47 active candidates across all positions, but not where they are or which positions need help. For leadership reporting, I create a PowerPoint every Monday morning summarizing status - it takes me about 90 minutes and I hate it.

---

**Q: Do you want the dashboard organized and structured a certain way? Any specific tabs or sections?**

A: Yes, I think two tabs would work well. The first tab should be my daily operational view - "Hiring Pipeline" - showing me what's happening right now. That's where I need to see my open positions, active candidates, the funnel, time-to-hire, which positions are moving fast or slow. That's my morning check-in view.

The second tab could be "Recruiting Performance" - more strategic stuff that I review weekly or monthly. That's where source effectiveness, hiring velocity over time, cost per hire, and trend analysis would live. I don't need that every day, but I need it for planning and optimization.

---

**Q: What are the main things you want the dashboard to contain? What metrics specifically and how do you define them?**

A: Let me break this down by what I need:

**Mission-Critical Metrics:**
- **Open Positions** - simple count of how many reqs I'm actively working. This is my workload indicator.
- **Active Candidates** - total candidates currently in motion across all positions, from sourced through offer stage. Excludes anyone rejected or hired. This tells me if my pipeline is healthy or drying up.
- **Average Time-to-Hire** - calendar days from when the req opens to when the offer is accepted. This is our key efficiency metric. Right now we're running around 45-50 days and we want to be under 40.

**Needed Metrics:**
- **Offer Acceptance Rate** - percentage of offers that get accepted versus rejected. Calculated as accepted offers divided by total offers over the time period. If this drops below 80%, we have a problem with competitiveness.

---

**Q: For each metric or analysis, can you describe the data question, any specific chart type preferences, and what actions you'd take based on it? Let's go through them one by one.**

**Component: Candidate Pipeline Funnel**

A: **Data question:** How are candidates distributed across our recruitment stages, and where are we losing them?

**Chart preference:** Definitely a funnel chart. Stages should be: Sourced → Screening → Interview → Offer → Accepted. I want to see both the number at each stage and the conversion rates between stages.

**Importance:** Mission-critical. This is my #1 diagnostic tool.

**Actions:** If I see a bulge at screening with low conversion to interview, I know there's either a quality problem with our sourcing or a bottleneck in our screening process. If I see high drop-off after interviews, that's candidate experience or competitiveness. If candidates are getting stuck at offer negotiation, I need to talk to comp team.

**Deep dive trigger:** Any stage with less than 50% conversion to the next stage is a red flag that requires investigation.

---

**Component: Time-to-Hire by Position**

A: **Data question:** Which positions are taking the longest to fill and by how much?

**Chart preference:** Horizontal bar chart, sorted from longest to shortest time-to-hire. Makes it immediately obvious which roles are problematic.

**Importance:** Mission-critical. Some positions naturally take longer (senior architect versus junior developer), but I need to spot the outliers.

**Actions:** Any position over 60 days gets escalated. I'll dig into why - is it unrealistic requirements from the hiring manager? Lack of qualified candidates in the market? Interview scheduling bottlenecks? Then I adjust strategy - maybe we need external recruiters, or the job description needs tweaking, or we need to move faster on scheduling.

**Deep dive trigger:** Any position 2x the average time-to-hire for similar role types.

---

**Component: Open Positions Status Table**

A: **Data question:** What is the detailed status of each specific position - how long has it been open, and how many candidates are at each stage?

**Columns needed:** Position Title, Days Open, then a breakdown of candidates by stage (Sourced, Screening, Interview, Offer), and Total Active Candidates.

**Importance:** Mission-critical. This is my detailed operational view.

**Actions:** This is where I drill down for specific positions. If "Senior Backend Engineer" has been open 45 days with 1 candidate in screening and 0 in interview, that's a crisis requiring immediate sourcing action. If "Frontend Developer" has 8 candidates in interview stage, I need to accelerate decision-making with the hiring manager.

**Deep dive trigger:** I want to be able to click through from this table to see the actual candidate names and details in the ATS.

---

**Component: Candidates by Source**

A: **Data question:** Where are our candidates coming from - LinkedIn, referrals, job boards, recruiters, etc.?

**Chart preference:** Either pie chart or bar chart, whichever is clearer. I want to see the distribution.

**Importance:** Needed for strategic planning, but not daily operational.

**Actions:** If 70% of candidates are coming from LinkedIn and only 5% from referrals, I need to invest more in our referral program. If we're over-reliant on expensive external recruiters, I need to diversify. This informs my sourcing strategy and where I spend time.

**Deep dive trigger:** Any source over 50% of volume (over-reliance risk) or any source we're paying for that's under 10% (poor ROI).

---

**Component: Hiring Velocity**

A: **Data question:** Are we increasing or decreasing our rate of hiring over time? How many people are we actually getting hired per month?

**Chart preference:** Line chart or bar chart showing completed hires per month over the last 12 months.

**Importance:** Needed for capacity planning and trend identification.

**Actions:** If velocity is declining, that's an early warning sign of pipeline problems that will hit us in 30-60 days. If velocity is increasing, I can be more confident about future position fills. This also helps me identify seasonal patterns - maybe we always slow down in December, or summer is our peak hiring season.

**Deep dive trigger:** Month-over-month decline of more than 25% that isn't explained by planned hiring freezes or seasonality.

---

**Component: Cost per Hire by Channel**

A: **Data question:** What's our cost efficiency for each recruitment source - how much are we spending per successful hire?

**Chart preference:** Bar chart comparing cost per hire across different channels.

**Importance:** Good to have. Important for budget decisions but not daily operations.

**Actions:** If LinkedIn Recruiter costs us $5,000 per hire but employee referrals cost $1,000 per hire, that's a strong signal to invest more in referral programs. This directly informs recruitment budget allocation decisions during quarterly planning.

**Deep dive trigger:** Any channel with cost per hire more than 2x our average needs scrutiny about whether the quality justifies the cost.

---

**Q: What urgent things do you want highlighted in the dashboard? Any specific alerts or visual indicators?**

A: Yes! I want visual flags for:
- Positions open longer than 45 days - that's my threshold for "this is taking too long"
- Positions with fewer than 3 active candidates - the pipeline is dangerously thin
- Any stage in the funnel with conversion rate below 40% - something's broken
- Offer acceptance rate below 75% - our offers aren't competitive

I don't need formal alerts sent to my email, but visual highlighting on the dashboard itself - maybe red/yellow/green indicators - would help me spot problems immediately.

---

**Q: Can you tell me more about how the recruitment process functions? The stages, the people involved, typical timelines?**

A: Sure. It starts when a hiring manager gets approval to open a position - that creates a requisition in our ATS. Then we start sourcing candidates from multiple channels: LinkedIn searches, posting on job boards like Indeed and Dice, employee referral program, sometimes we engage external recruiters for hard-to-fill senior roles.

Once we have candidates, they go through screening - a 30-minute phone call with me or a recruiter to assess basic fit. If they pass, they move to interviews - usually 2-3 rounds depending on the role. First round is typically technical screening, second is deeper technical dive with the team, third (for senior roles) is with the hiring manager and sometimes their director. After interviews, we make a decision within a few days ideally, then extend an offer.

The whole process, when it works well, takes 30-35 days. But it often stretches to 45-50 days because of interview scheduling conflicts, slow hiring manager decision-making, offer negotiations, or pipeline gaps where we have to restart sourcing.

---

**Q: How do you view and manage this process day-to-day? How do you decide if things are going well or not?**

A: Right now it's very manual and intuition-based. I start my day by checking the ATS for any new applicants or status changes. I look at my spreadsheet to see which positions I haven't updated in a few days - that usually means something's stuck. I have standing check-ins with hiring managers, and I'm constantly following up via email and Slack about interview scheduling and feedback.

I decide things are going well if candidates are moving to the next stage within a week of entering the current stage. If someone's been in "interview scheduled" status for 2 weeks, something's wrong - either the interview didn't happen or feedback wasn't submitted. I also gauge health by hiring manager satisfaction - if they're not complaining about lack of candidates or slow progress, I assume I'm doing okay.

But honestly, I'm often reactive. I find out a position is in trouble when the hiring manager escalates to my boss, or when I realize we've had a req open for 60 days with no offer in sight. I want to be proactive instead - catching problems at 30 days when there's still time to fix them.

---

**Q: How recent does the data need to be? How frequently do you want it refreshed?**

A: For the operational stuff - the pipeline view - I need that updated daily, ideally overnight. If I look at it Monday morning, I need to see Friday's end-of-day status at minimum. Real-time would be amazing but probably overkill.

For the performance analytics - source effectiveness, cost per hire, velocity trends - weekly refresh is totally fine. That data doesn't change fast enough to need daily updates, and frankly there's probably some lag in the cost data anyway since that comes from finance systems.

Most important thing: show me when the data was last refreshed. I need to know if I'm looking at yesterday's data or last week's data so I can trust what I'm seeing.

---

**Q: Any other requirements around access, performance, or usability?**

A: A few things:
- I need to be able to access this on my phone. I'm often in meetings or interviews, and if a hiring manager asks me about a position, I want to pull up the dashboard right there rather than saying "I'll check and get back to you."
- Export capability for that open positions table would be great. Sometimes I need to drop it into an email or presentation.
- Load time matters - if it takes 30 seconds to load, I won't use it. Should be under 5 seconds.
- I want to be able to click through from the charts to see the underlying candidate lists. Like if the funnel shows 12 candidates at interview stage, I want to click that and see who they are.

---

**Q: Are there filters you need to slice the data different ways?**

A: Absolutely. I need to be able to filter by date range - sometimes I want to look at the last 30 days, sometimes the last quarter, sometimes year-to-date. I also need to filter by specific positions or role types - like "show me just the senior engineering positions" or "show me just frontend roles." 

These filters should apply across the whole dashboard, not just one chart. And the default view should probably be last 90 days, all active positions. That gives me a good working window without being overwhelming.

---

**Follow-up Q: What about the candidate stages? Are they standardized or do they vary by position type?**

A: They're standardized across all positions, which is good for consistency. Everyone goes through the same stages: Sourced → Screening → Interview → Offer → Accepted. The number of interview rounds might vary - junior roles might have 2 interviews, senior roles might have 3-4 - but they all roll up into the "Interview" stage in our ATS. So the funnel should be based on those five standard stages.

---

**Follow-up Q: When you calculate time-to-hire, what's the start and end point?**

A: Start point is when the requisition is officially opened and approved in the system. End point is when the candidate accepts the offer - not when they start working, but when they say yes. We don't count positions that are on hold or cancelled. It's purely active recruiting time. So if a position is opened, then put on hold for a month due to budget freeze, then reactivated, we'd only count the time it was actively being recruited.

---

**Follow-up Q: For offer acceptance rate, any nuances in how that should be calculated?**

A: Yeah, we only count final formal offers that are extended. So verbal offers or offers still in negotiation don't count until they're actually formally sent. And we calculate it over whatever time period is filtered - so if I'm looking at Q4 2024, it's offers sent and decided (accepted or rejected) within Q4. Offers that are still pending don't factor in yet.

---

**Follow-up Q: Who owns the cost data for recruitment channels, and how current is it?**

A: That's a bit of a mess right now, honestly. Our finance team tracks some of it - like job board subscriptions and LinkedIn Recruiter fees. External recruiter fees are tracked per engagement. Employee referral bonuses are tracked through payroll. It's not centralized, and there's probably a lag of a few weeks on some of the data. That's part of why I marked cost per hire as "good to have" rather than mission-critical - the data quality isn't great yet, but having it on the dashboard will force us to get better about tracking it.

---
