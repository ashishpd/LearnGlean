# Glean's Analytical Capabilities and Limitations

## Table of Contents
1. [Overview of Analytical Capabilities](#overview-of-analytical-capabilities)
2. [What Glean Can Do with Data](#what-glean-can-do-with-data)
3. [What Glean Cannot Do (Current Limitations)](#what-glean-cannot-do-current-limitations)
4. [Use Case Analysis: Budget Questions](#use-case-analysis-budget-questions)
5. [How to Use Glean for Analytical Questions](#how-to-use-glean-for-analytical-questions)
6. [Future Capabilities](#future-capabilities)
7. [Best Practices](#best-practices)

---

## Overview of Analytical Capabilities

### Core Function: Search and Information Retrieval

Glean's primary strength is **unified search and information retrieval** across organizational data sources. It excels at:

- **Finding Information**: Locating documents, reports, and data across all connected systems
- **Synthesizing Information**: Combining information from multiple sources into coherent answers
- **Understanding Context**: Understanding queries and providing relevant results
- **Personalization**: Tailoring results to user context and permissions

### Analytical Capabilities: Current State

Glean's analytical capabilities exist **within the context of search and information synthesis**, not as a standalone analytical engine. The platform can:

✅ **Retrieve and Synthesize Data**: Find and combine information from multiple sources
✅ **Answer Questions Based on Content**: Provide answers from existing documents and reports
✅ **Multi-Step Reasoning**: (Third-generation assistant) Perform multi-step tasks
✅ **Data Discovery**: Help users find where data exists
✅ **Contextual Understanding**: Understand analytical questions and find relevant data

❌ **Perform Calculations**: Not designed for complex numerical calculations
❌ **Real-Time Data Analysis**: Cannot analyze live data streams directly
❌ **Financial Modeling**: Not a financial analysis tool
❌ **Budget Management**: Cannot directly manage or modify budgets
❌ **Data Visualization**: Limited visualization capabilities

---

## What Glean Can Do with Data

### 1. Information Retrieval and Synthesis

#### Finding Relevant Data

**Capabilities**:
- Search across all connected financial systems
- Find budget documents, reports, and spreadsheets
- Locate project financial data
- Discover historical budget information
- Access real-time data from connected systems

**Example Queries**:
- "Find all budget reports from Q4 2024"
- "Show me project financial data for Project X"
- "What was the budget for Marketing in 2023?"

#### Synthesizing Information

**Capabilities**:
- Combine information from multiple sources
- Create summaries from multiple documents
- Answer questions using data from various systems
- Provide context from related documents

**Example**:
- Query: "What was our total marketing spend last quarter?"
- Glean can: Find marketing budget documents, expense reports, and financial statements, then synthesize the information to provide an answer

### 2. AI Answers with Data Context

#### How AI Answers Work with Data

**Process**:
1. **Query Understanding**: Understands the analytical question
2. **Data Retrieval**: Finds relevant financial documents, reports, and data
3. **Information Synthesis**: Combines data from multiple sources
4. **Answer Generation**: Provides a synthesized answer with citations

**Example**:
- **Query**: "How is my budget looking compared to last year?"
- **Glean's Process**:
  1. Understands this is a budget comparison question
  2. Finds current budget documents
  3. Finds previous year's budget documents
  4. Extracts relevant numbers
  5. Synthesizes a comparison answer
  6. Cites source documents

**Limitations**:
- Depends on data being in searchable documents/reports
- Cannot perform complex calculations
- May not have real-time data (depends on sync frequency)
- Cannot create new analyses, only synthesize existing ones

### 3. Multi-Step Task Execution (Third-Generation Assistant)

#### Enhanced Capabilities

The third-generation Glean Assistant (September 2025) introduced multi-step task execution:

**Capabilities**:
- **Multi-Step Reasoning**: Can break down complex questions into steps
- **Task Orchestration**: Can coordinate multiple actions
- **Context Preservation**: Maintains context across steps
- **Autonomous Actions**: Can take actions based on prompts

**Example Workflow**:
- **Query**: "Which project is over budget and how can I fund it from another project?"
- **Potential Steps**:
  1. Find all project budgets
  2. Identify projects over budget
  3. Find projects with available budget
  4. Suggest funding reallocation options
  5. Provide recommendations

**Current Limitations**:
- Still primarily information retrieval and synthesis
- Cannot directly modify budgets or financial systems
- Cannot perform complex financial modeling
- Depends on data availability in connected systems

### 4. Data Discovery and Navigation

#### Helping Users Find Data

**Capabilities**:
- **Data Location**: Help users find where financial data is stored
- **System Navigation**: Guide users to the right systems
- **Related Information**: Find related financial documents
- **Expert Discovery**: Find who has expertise in financial data

**Example**:
- Query: "Where can I find project budget information?"
- Glean can: Direct users to the right systems, documents, or people

---

## What Glean Cannot Do (Current Limitations)

### 1. Direct Data Analysis

#### Limitations

**Cannot Perform**:
- ❌ Complex numerical calculations
- ❌ Statistical analysis
- ❌ Financial modeling
- ❌ Real-time data processing
- ❌ Data transformations
- ❌ Advanced analytics

**Why**:
- Glean is a search and information platform, not an analytical engine
- Designed for information retrieval, not computation
- Focuses on finding and synthesizing, not calculating

### 2. Budget Management

#### Cannot Directly Manage Budgets

**Limitations**:
- ❌ Cannot modify budgets
- ❌ Cannot create budget allocations
- ❌ Cannot transfer funds between projects
- ❌ Cannot approve budget changes
- ❌ Cannot update financial systems directly

**What It Can Do**:
- ✅ Find budget information
- ✅ Show budget comparisons
- ✅ Identify budget documents
- ✅ Suggest where to make changes (in source systems)

### 3. Real-Time Financial Operations

#### Limitations

**Cannot**:
- ❌ Access real-time financial data (depends on sync)
- ❌ Perform live calculations
- ❌ Update financial systems in real-time
- ❌ Execute financial transactions
- ❌ Modify financial records

**What It Can Do**:
- ✅ Access data as frequently as connectors sync
- ✅ Find most recent financial information available
- ✅ Guide users to systems where changes can be made

### 4. Advanced Financial Analysis

#### Limitations

**Cannot Perform**:
- ❌ Financial forecasting
- ❌ Budget optimization
- ❌ Cost-benefit analysis
- ❌ Financial risk analysis
- ❌ Advanced financial modeling

**What It Can Do**:
- ✅ Find existing financial analyses
- ✅ Synthesize information from financial reports
- ✅ Answer questions based on existing data

---

## Use Case Analysis: Budget Questions

### Question 1: "How is my budget looking compared to last year?"

#### What Glean Can Do

**Capabilities**:
1. **Find Budget Documents**:
   - Current year budget documents
   - Previous year budget documents
   - Budget comparison reports (if they exist)

2. **Synthesize Information**:
   - Extract budget numbers from documents
   - Compare current vs. previous year
   - Provide summary of differences

3. **Provide Answer**:
   - "Based on the budget documents, your current budget is X% higher/lower than last year"
   - Cite source documents
   - Show key differences

**Limitations**:
- Depends on budget documents being available and searchable
- Cannot perform calculations if numbers aren't in documents
- May not have real-time data (depends on sync)
- Cannot create new comparison reports (only finds existing ones)

**Best Approach**:
- Ensure budget documents are in connected systems
- Use consistent document formats
- Keep documents up to date
- Create comparison reports that Glean can find

### Question 2: "Which project is over budget?"

#### What Glean Can Do

**Capabilities**:
1. **Find Project Financial Data**:
   - Project budget documents
   - Project expense reports
   - Project financial dashboards (if accessible)

2. **Identify Over-Budget Projects**:
   - Find documents that indicate over-budget status
   - Locate project financial reports
   - Find alerts or notifications about over-budget projects

3. **Synthesize Answer**:
   - List projects that are over budget
   - Show budget vs. actuals (if in documents)
   - Provide context from project documents

**Limitations**:
- Cannot calculate over-budget status if not already in documents
- Depends on project financial data being searchable
- May not have real-time project status
- Cannot directly query project management systems for calculations

**Best Approach**:
- Ensure project financial data is in connected systems
- Use project management tools that Glean can index
- Create regular budget status reports
- Use systems that provide over-budget alerts

### Question 3: "How can I fund a project by taking money from another project?"

#### What Glean Can Do

**Capabilities**:
1. **Find Funding Information**:
   - Projects with available budget
   - Projects with surplus funds
   - Budget allocation documents
   - Funding policies and procedures

2. **Identify Options**:
   - Find projects with available budget
   - Locate budget reallocation procedures
   - Find historical examples of budget transfers
   - Identify approval processes

3. **Provide Recommendations**:
   - Suggest projects with available funds
   - Explain reallocation procedures
   - Guide users to systems where changes can be made
   - Provide context from similar situations

**Limitations**:
- Cannot directly transfer funds
- Cannot modify budgets
- Cannot approve budget changes
- Cannot perform budget optimization calculations
- Cannot guarantee fund availability

**Best Approach**:
- Use Glean to find information and options
- Use dedicated financial systems for actual transfers
- Ensure budget data is current and searchable
- Create clear budget reallocation procedures that Glean can find

---

## How to Use Glean for Analytical Questions

### Strategy 1: Information Discovery

#### Use Glean to Find Data

**Approach**:
1. Ask Glean where data is located
2. Use Glean to find relevant documents
3. Navigate to source systems for analysis
4. Use Glean to find related information

**Example Workflow**:
- Query: "Where can I find project budget data?"
- Glean: Directs to Jira, financial systems, or budget documents
- User: Accesses source system for detailed analysis

### Strategy 2: Synthesis and Summary

#### Use Glean to Synthesize Existing Analyses

**Approach**:
1. Ensure analyses exist in documents/reports
2. Ask Glean to find and synthesize them
3. Get answers based on existing work
4. Use source systems for new analyses

**Example Workflow**:
- Query: "What was our Q4 budget performance?"
- Glean: Finds and synthesizes Q4 budget reports
- User: Gets summary, can access full reports for details

### Strategy 3: Multi-Step Information Gathering

#### Use Third-Generation Assistant for Complex Queries

**Approach**:
1. Ask complex, multi-part questions
2. Let Glean break down into steps
3. Get synthesized information from multiple sources
4. Use information to make decisions

**Example Workflow**:
- Query: "Which projects are over budget and what are my options to fix it?"
- Glean: 
  - Step 1: Finds over-budget projects
  - Step 2: Finds available budget sources
  - Step 3: Finds reallocation procedures
  - Step 4: Synthesizes recommendations
- User: Gets comprehensive answer with options

### Strategy 4: Hybrid Approach

#### Combine Glean with Analytical Tools

**Best Practice**:
1. **Use Glean for Discovery**: Find where data is, what exists
2. **Use Glean for Context**: Understand background, history, policies
3. **Use Analytical Tools for Analysis**: Perform calculations, create models
4. **Use Glean for Sharing**: Find who needs information, share insights

**Example**:
- **Glean**: "Find all Q4 budget documents and show me the approval process"
- **Analytical Tool**: Perform detailed budget analysis and calculations
- **Glean**: "Who should I share this budget analysis with?"

---

## Future Capabilities

### Potential Enhancements

Based on Glean's roadmap and third-generation assistant capabilities:

#### 1. Enhanced Data Analysis

**Potential**:
- More sophisticated data synthesis
- Better numerical reasoning
- Improved multi-step calculations
- Integration with analytical tools

#### 2. Real-Time Data Access

**Potential**:
- More frequent data syncs
- Real-time connector updates
- Live data queries
- Streaming data support

#### 3. Action Capabilities

**Potential**:
- Direct integration with financial systems
- Ability to trigger actions (with approval)
- Workflow automation
- Budget update capabilities (with proper controls)

#### 4. Advanced Reasoning

**Potential**:
- Financial modeling assistance
- Budget optimization suggestions
- Predictive analytics
- Scenario planning

### Current Development Focus

Based on recent releases:
- **Multi-Step Tasks**: Already improving
- **Desktop Integration**: Better workflow integration
- **AI Capabilities**: Enhanced reasoning
- **Enterprise Graph**: Better relationship understanding

---

## Best Practices

### For Budget and Financial Questions

#### 1. Data Preparation

**Ensure**:
- Budget documents are in connected systems
- Financial data is searchable
- Reports are regularly updated
- Consistent naming and formatting

#### 2. Document Structure

**Best Practices**:
- Use clear, descriptive document names
- Include dates and periods in document titles
- Create comparison reports regularly
- Maintain historical budget documents

#### 3. Query Formulation

**Effective Queries**:
- "Find budget comparison reports for 2024 vs 2023"
- "Show me projects that are over budget"
- "What is the process for reallocating project budgets?"

**Less Effective**:
- "Calculate my budget variance" (if calculation doesn't exist)
- "Transfer $10K from Project A to Project B" (action not supported)
- "Optimize my budget allocation" (requires analysis tool)

#### 4. Integration Strategy

**Recommended Approach**:
- Connect financial systems to Glean
- Ensure budget data is indexed
- Create regular budget status reports
- Use Glean for discovery, source systems for actions

#### 5. Expectation Management

**Understand**:
- Glean excels at finding and synthesizing information
- Glean is not a financial analysis tool
- Use Glean for discovery and context
- Use dedicated tools for calculations and actions

---

## Summary

### What Glean Can Do for Budget Questions

✅ **Find Budget Information**: Locate budget documents, reports, and data across all systems
✅ **Synthesize Answers**: Combine information from multiple sources to answer questions
✅ **Compare Data**: Compare budgets if comparison data exists in documents
✅ **Identify Issues**: Find projects over budget if that information is available
✅ **Provide Context**: Understand policies, procedures, and historical context
✅ **Multi-Step Reasoning**: Break down complex questions and gather information from multiple sources
✅ **Guide Users**: Direct users to systems where actions can be taken

### What Glean Cannot Do (Currently)

❌ **Perform Calculations**: Cannot do complex numerical analysis
❌ **Modify Budgets**: Cannot directly change budget allocations
❌ **Real-Time Analysis**: Cannot analyze live data streams
❌ **Financial Modeling**: Not a financial analysis tool
❌ **Execute Actions**: Cannot transfer funds or approve changes
❌ **Create New Analyses**: Can only synthesize existing information

### Recommended Approach

**For Budget Questions**:

1. **Use Glean for Discovery**: "Where is my budget data? What projects are over budget?"
2. **Use Glean for Synthesis**: "How does this year's budget compare to last year's?" (if reports exist)
3. **Use Glean for Context**: "What's the process for reallocating budgets?"
4. **Use Source Systems for Actions**: Make actual budget changes in financial systems
5. **Use Analytical Tools for Analysis**: Perform calculations and modeling in dedicated tools

### The Bottom Line

Glean is **excellent at finding and synthesizing information** about budgets and financial data, but it's **not a financial analysis or budget management tool**. It can help you:

- **Discover** where budget information is
- **Understand** budget status and context
- **Synthesize** information from multiple sources
- **Navigate** to systems where actions can be taken

But for actual budget calculations, modifications, and financial analysis, you'll need to use:
- Dedicated financial management systems
- Business intelligence tools
- Spreadsheet applications
- Financial analysis software

Glean enhances your ability to **find and understand** financial information, making it easier to then use the right tools for **analysis and action**.

---

**Note**: Glean's capabilities are evolving, especially with the third-generation assistant. Some limitations may be addressed in future releases. For the most current capabilities, consult Glean's official documentation or contact their support team.

