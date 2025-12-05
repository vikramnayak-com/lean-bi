The process in gist:

We are building a dashboard wireframing system that helps BI teams collaborate with business users to better understand requirements and deliver more useful dashboards. Here is the flow of our system in a nutshell: 

First we conduct discovery interviews with stakeholders and users (outside of your system). 
After the discovery interviews, the Inputs Evaluator evaluates the answers and decides if all required criteria are fulfilled or not. if yes, it outputs a list of questions and answers. If not, it asks follow up questions and you repeat this above step. 
The collated output from Input Evaluator now goes into the Dashboard Requirement Document (DRD) Maker, which synthesizes it into a structured and well-formed DRD
The DRD becomes the input for the Dashboard Spec Maker. The spec maker outputs the equivalent of a bulleted indented list that entirely describes the structure, content and behaviour of the dashboard. 
The Spec is sent as an input for the Representation Chooser which chooses the best visual for each component. 
This augmented dashboard spec now becomes the input for Layout Generator and Mapper. It uses sizing intelligence and layout knowledge to generate the best layout for the dashboard, with a map of what components go where. 
This spec + representation + mapped layout then becomes the input for the Visual Renderer and Editor. We can edit the wireframe both with prompts and visually

Process in detail

0. Persona Simulator
The first box is a persona simulator, which acts, thinks, talks like the given persona. CEO is just an example here it could also be HR, Product Manager, Investor, etc. The role of this LLM instance is to simulate the behavior of the persona and to express it while answering questions.

We start with a pre-made set of questions. These questions are like an interview for the persona, in order to collect necessary information to create a Dashboard. The questions are like this:

Stakeholder Interview (key Q’s)
	- What dashboard do you want? 
	- What is the reason for wanting the dashboard?
	- Who will be using this dashboard? 
	- What systems are the source of truth for this? 
	- What business results or outcomes do you expect from it?
	- What decisions or actions do you want your team to be able to take once they have this dashboard?
	- What are the main things you want this to contain?
		- What metrics?
		- What analyses or charts or questions?

	- Can you tell me how this general area functions? Processes, people, etc. 
		- How do you view it and manage it?
		- How do you decide if things are going well or not?

User Interview (Key Q’s)
	- What is the purpose of this dashboard? 
	- How does this area fit into your overall role and responsibilities?
	- What systems are the source of truth for this? 
	- What decisions or actions do you want your team to be able to take once they have this dashboard?
	- How do you currently track this?
		- Metrics
		- Analyses or charts or questions
		- How do you receive the report? How frequently?
	- Do you want the dashboard organised and structured a certain way? (tabs)
	- What are the main things you want the dashboard to contain?
		- What metrics? How do you define it?
		- What analyses or charts or questions?
	- (Loop) For each of those metrics and analysis:
		- How important is it? (1. Mission-critical 2. Needed but can function without 3. Good to have)
		- Can you describe what the data question is or what fields you want to see?
		- Do you want a specific chart type?
		- What actions or decisions will you take based on it? What conditions or triggers for these actions?
		- What would make you want to deep dive into a component?
	- What urgent things do you want highlighted in the dashboard? 
	- Can you tell me how this general area functions? Processes, people, etc. 
		- How do you view it and manage it?
		- How do you decide if things are going well or not?
	- How recent does the data need to be? How frequently do you want it refreshed?


1. Input Evaluator

The collated answers to these questions then go to another LLM instance, Answer Evaluator. It does what it says - Evaluates. It evaluates the answers based on what information is provided and the quality of information. This is an LLM instance which can loop until it is satisfied with the answers. Every time it loops, it asks the Persona Simulator follow up questions. Here is the list of evaluation criteria:

✓ Business requirements and goals
✓ Project success criteria  
✓ Users and their goals
✓ Decisions and actions the dashboard will support
✓ Business questions to be answered
✓ Components needed (charts, tables, KPIs, etc.)
  - Data questions for each component
  - What decisions/actions each supports
  - Priority level of each component
✓ Data sources and systems of truth
✓ Metric definitions where not obvious (how metrics are calculated)
✓ Filters needed

2. DRD Maker

Once the Answer Evaluator LLM instance is satisfied, we have the final list of questions and answers and with that we move to the next LLM instance, Dashboard Requirement Document Maker or DRD Maker. As DRD is similar to a Product Requirement Document. The Output of the DRD Maker must take care of these things:

DRD
    - Business requirements and goals
    - Project success criteria
    - Users, Goals
    - Decisions and actions
    - Business questions
    - Filters
    - Components
        - Data questions
        - Decision/action supported
        - Priority Level
    - Data sources 
    - Metric definitions (only where not obvious)

3. Spec Generator

Once we get the final DRD, we move to the next LLM instance, Spec Maker. It goes something like this:

- Construct:
    - Think of it like a bulleted indented list that specifies the WHAT of the dashboard

- Tabs
    - Components
        - UUID (globally unique)
        - precise data questions
        - decision / action
        - suggested visual representation
        - Priority Level
- Filters
    - Fields
    - Type of filter (multi-select / drop-down / expression)
    - Condition (eg. Last 12 months)


4. Representation Chooser

Once we have the spec, we move to the next LLM instance, which is the Representation Chooser. It chooses the appropriate kind of representations for the spec. There are a few ways to represent:
1. Charts
2. KPIs
3. Tables
4. Maps
It chooses the best form of representation based on these notes:

- Construct:
    - Given the details of a component from the spec, what is the best representation for it?
    - Also accounts for user preferences/requests

- Type of representation
    - Chart
    - Table
    - KPI
    - Map

- Additional elements:
    - context elements 
    - highlight / storytelling elements
    - design choices

- (Loop)
    - For each component, get a ranked list of suitable representation options

This creates a list of representations for each component. 

5. Layout and Mapping

This becomes the input for the next LLM instance, the Layout Chooser. Based on the specs and available ways to represent, it creates a layout for the dashboard. It gives details of each box (combination of row and column, example: "Tab1!R1C2").  Use the notes here to understand how the layout chooser works:

- Layout Considerations:
    - KPIs present? Top or left?
    - Number of rows? 
    - Height of each row?
    - Number of columns in each row?
    - Size of each box? (small/big)
    - Filter location? Top or left?
    - Scrollable?

- Largely Depends on:
    - Dominant "Type" of dashboard
        - Strategic
        - Tactical
        - Operational

But it is also heavily dependent on our specific components in the spec

- Can have the same layout applied to all tabs, with specific adjustments then applied to each tab

- Fully-qualified Address of each box = Tab + Row Number + Column Number

We then use the priority of each component as well as the F-pattern and Z-pattern to decide where each component gets placed in the layout. It maps each component's representation to the Layout's boxes and returns a map of component to layout-box. If we want to make any visual edits in the dashboard, we do them here in the output of the component mapper.

6. Rendering

The system should use basic HTML to create the structure of the dashboard with its boxes, and then infer the best way to create each component based on its type. All of these are to be in grayscale, so don't waste too much capacity on color styling. 

For KPIs, think about the different possible elements (create with simple HTML):
Metric name (required)
Metric value in large font (required)
Comparison % against a target value with up/down arrow (optional)
Small text to indicate what is being compared against (optional)
Trend line to show how the metric has moved over some time period

For tables, think about the various possibilities (create with simple HTML):
Header format
Presence of horizontal / vertical border depending on what we want to compare
Column number formats and alignment 
Visual elements like action dots, indicator arrows, in-cell charts (sparkline, column, etc)
Emphasis elements like bold, italics, color

For charts, think about:
Type of use case (e.g., data over time, contribution of each category, etc)
Choose the best chart based on data and use case. 
Keep the list of possible charts simple and limited
Add only the key elements needed for a wireframe. Avoid unnecessary styling
Use a library that gives you a compact spec, like chart.js

Then render the created html as an artifact

Rules and important information
- Each box / step of our process is a separate LLM instance, just like you.
- The inter-instance format can be simply text with basic formatting.
- I will manually copy the follow up questions to the persona simulator, bring the new set of answers back and then the answer evaluator may either give another new set of questions or may give the question-answer list as its final output.
- Each system prompt should largely be standalone, but should understand what is it starting from and what it is creating and how is its output going to be consumed by the next LLM instance.
- The system prompts should explicitly mention that “strictly adhere to all rules”.

