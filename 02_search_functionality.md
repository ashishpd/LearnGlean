# Search Functionality in Glean

## Table of Contents
1. [Intelligent Search Overview](#intelligent-search-overview)
2. [Search Types and Capabilities](#search-types-and-capabilities)
3. [Query Understanding](#query-understanding)
4. [Result Ranking and Relevance](#result-ranking-and-relevance)
5. [Personalization](#personalization)
6. [Search Interface Features](#search-interface-features)
7. [Advanced Search Features](#advanced-search-features)

---

## Intelligent Search Overview

### Beyond Keyword Matching

Traditional search tools rely primarily on keyword matching - finding documents that contain the exact words in a query. Glean's intelligent search goes far beyond this, using AI to understand:

- **Intent**: What the user is really trying to find
- **Context**: The user's role, current work, and history
- **Meaning**: Semantic understanding of queries and content
- **Relationships**: Connections between people, content, and topics

### Core Search Principles

Glean's search is built on several key principles:

1. **Semantic Understanding**: Understanding meaning, not just words
2. **Multi-Source Federation**: Searching across all connected sources simultaneously
3. **Permission-Aware**: Only showing results users are authorized to access
4. **Contextual Ranking**: Personalizing results based on user context
5. **Continuous Learning**: Improving relevance through usage patterns

---

## Search Types and Capabilities

### 1. Natural Language Search

#### Overview
Users can search using natural, conversational language rather than needing to construct complex queries with operators.

#### Examples
- **Simple Query**: "How do I submit an expense report?"
- **Complex Query**: "Find the Q4 sales presentation that Sarah shared with the marketing team last month"
- **Question Format**: "Who is the expert on machine learning in our organization?"

#### Benefits
- No training required - users search as they would ask a colleague
- Handles ambiguity through context understanding
- Supports multiple languages
- Understands company-specific terminology

### 2. Semantic Search

#### What is Semantic Search?
Semantic search understands the meaning and intent behind queries, not just keyword matches. It can:

- Find content using synonyms and related terms
- Understand concepts even when different words are used
- Recognize domain-specific terminology
- Handle queries that don't contain exact keywords from relevant documents

#### How It Works
- Uses vector embeddings to represent content and queries in a semantic space
- Finds content with similar meaning, even if different words are used
- Leverages knowledge graphs to understand relationships
- Considers context and user history

#### Example
**Query**: "employee benefits enrollment"
**Finds**: Documents about "health insurance sign-up", "benefits selection", "enrollment process" even if they don't contain the exact phrase "employee benefits enrollment"

### 3. Federated Search

#### Definition
Federated search queries multiple data sources simultaneously and combines results into a unified view.

#### How Glean Implements It
1. **Parallel Querying**: Sends search requests to all relevant connectors simultaneously
2. **Permission Filtering**: Applies user permissions at each source
3. **Result Aggregation**: Combines results from all sources
4. **Unified Ranking**: Ranks results across sources based on relevance
5. **Deduplication**: Handles cases where the same content exists in multiple sources

#### Benefits
- Users don't need to know which system contains information
- Single interface for all organizational data
- Consistent experience regardless of source
- Efficient - queries sources in parallel

### 4. People Search

#### Overview
People search helps users find colleagues and identify experts on specific topics.

#### Capabilities
- **Expertise Discovery**: Identifies who has knowledge or experience with specific topics
- **Based on**: Content creation, contributions, mentions, engagement patterns
- **Profile Information**: Role, team, contact information
- **Content Connections**: Shows what content people have created or contributed to
- **Activity Insights**: Recent work and contributions

#### Use Cases
- Finding subject matter experts
- Discovering who worked on similar projects
- Identifying team members with specific skills
- Understanding organizational structure and relationships

### 5. Content Type Search

#### Supported Content Types
Glean can search across various content types:

- **Documents**: PDFs, Word docs, presentations, spreadsheets
- **Emails**: Email threads and conversations
- **Messages**: Slack, Teams, and other messaging platforms
- **Wikis and Knowledge Bases**: Confluence, Notion, etc.
- **Code Repositories**: GitHub, GitLab, etc.
- **Databases**: Structured data and records
- **Media**: Images (with OCR), videos (with transcription)
- **Social Content**: Posts, comments, discussions

#### Content Understanding
- Extracts text from various file formats
- Performs OCR on images
- Transcribes audio and video
- Understands structured data
- Indexes metadata and properties

---

## Query Understanding

### How Glean Understands Queries

#### 1. Natural Language Processing (NLP)

**Tokenization**: Breaking queries into meaningful units
**Part-of-Speech Tagging**: Identifying nouns, verbs, adjectives, etc.
**Named Entity Recognition**: Identifying people, places, organizations, dates
**Dependency Parsing**: Understanding grammatical relationships

#### 2. Intent Classification

Glean classifies queries into different intent types:

- **Informational**: "What is our vacation policy?"
- **Navigational**: "Find the HR portal"
- **Transactional**: "Submit a help desk ticket"
- **Expertise Discovery**: "Who knows about Python?"
- **Content Discovery**: "Show me Q4 reports"

#### 3. Entity Extraction

Identifies important entities in queries:
- **People**: Names, roles, teams
- **Topics**: Subjects, domains, technologies
- **Time**: Dates, time periods, relative time ("last month")
- **Locations**: Offices, regions, countries
- **Organizations**: Departments, teams, external companies

#### 4. Query Expansion

Automatically adds related terms to improve search coverage:

- **Synonyms**: "car" → "automobile", "vehicle"
- **Related Concepts**: "benefits" → "insurance", "healthcare", "retirement"
- **Domain Terms**: Company-specific terminology and acronyms
- **Morphological Variants**: "run" → "running", "ran"

#### 5. Ambiguity Resolution

When queries are ambiguous, Glean uses:

- **User Context**: Role, team, recent activity
- **Organizational Knowledge**: Common queries, popular content
- **Temporal Context**: Current time, recent events
- **Query History**: Previous searches by the user

### Example: Query Understanding Process

**Query**: "Find the budget proposal from finance"

**Understanding Process**:
1. **Entities Identified**: "budget proposal" (document type), "finance" (department)
2. **Intent**: Navigational/Content Discovery
3. **Expansion**: "budget" → "financial plan", "spending proposal", "budget request"
4. **Context**: User's department, recent work, access permissions
5. **Time Context**: May prioritize recent proposals
6. **Source Prioritization**: Likely in finance team's storage or shared documents

---

## Result Ranking and Relevance

### Ranking Factors

Glean uses multiple signals to rank search results:

#### 1. Semantic Relevance
- How well content matches the query's meaning
- Vector similarity scores
- Concept alignment

#### 2. Content Quality Signals
- **Authority**: Source reliability and importance
- **Freshness**: Recent content often more relevant
- **Completeness**: Comprehensive documents rank higher
- **Engagement**: Content that others find useful

#### 3. User Context Signals
- **Role Relevance**: Content relevant to user's job function
- **Team Alignment**: Content from user's team or related teams
- **Recent Activity**: Content related to user's current work
- **Access Patterns**: Types of content user typically accesses

#### 4. Organizational Signals
- **Popularity**: Frequently accessed or shared content
- **Expertise**: Content from recognized experts
- **Recency**: Recently created or updated content
- **Relationships**: Content connected to user's work through knowledge graph

#### 5. Source Prioritization
- **Authoritative Sources**: Official documentation, approved content
- **Source Reliability**: Trusted applications and repositories
- **Source Freshness**: Systems with more recent updates

### Ranking Algorithm

Glean's ranking algorithm:

1. **Initial Retrieval**: Finds candidate results from all sources
2. **Relevance Scoring**: Calculates semantic and keyword relevance
3. **Contextual Adjustment**: Applies user context and personalization
4. **Quality Boosting**: Enhances scores for high-quality content
5. **Final Ranking**: Combines all signals for final ordering

### Result Diversity

To avoid result pages dominated by one source or type:

- **Source Diversity**: Ensures results from multiple sources
- **Content Type Diversity**: Mixes documents, emails, messages, etc.
- **Temporal Diversity**: Includes both recent and historical content
- **Perspective Diversity**: Shows different viewpoints or versions

---

## Personalization

### How Personalization Works

Glean personalizes search results for each user based on multiple factors:

#### 1. User Profile
- **Role**: Job function and responsibilities
- **Department**: Organizational unit
- **Team**: Direct team membership
- **Location**: Office or region
- **Seniority**: Level in organization

#### 2. Behavioral Signals
- **Search History**: What the user has searched for
- **Click Patterns**: Which results users click on
- **Time Spent**: How long users engage with content
- **Content Access**: What content users regularly access
- **Sharing Patterns**: What content users share

#### 3. Work Context
- **Current Projects**: Active work and initiatives
- **Recent Activity**: Recent documents, emails, messages
- **Collaboration Patterns**: Who the user works with
- **Tools Used**: Which applications the user frequently uses

#### 4. Organizational Knowledge
- **Team Content**: Content from user's team ranks higher
- **Related Teams**: Content from collaborating teams
- **Expertise Areas**: Content in user's areas of expertise
- **Common Queries**: Popular searches in user's domain

### Personalization Examples

**Same Query, Different Results**:

**Query**: "budget"
- **Finance Team Member**: Sees financial budgets, budget proposals, budget reports
- **Engineering Manager**: Sees engineering project budgets, resource allocation
- **Marketing Employee**: Sees marketing campaign budgets, ad spend

**Why**: Each user's role and context influences what "budget" means to them.

### Balancing Personalization

Glean balances personalization with:

- **Relevance**: Highly personalized but still relevant to query
- **Discovery**: Not over-personalizing to miss important content
- **Freshness**: Including new content even if outside user's typical patterns
- **Diversity**: Ensuring variety in results

---

## Search Interface Features

### 1. Search Box and Autocomplete

#### Autocomplete/Suggestions
- **Real-time Suggestions**: As users type, Glean suggests:
  - Popular queries
  - Recent searches
  - Content titles
  - People names
  - Topics and concepts

#### Benefits
- Faster query entry
- Discovery of common searches
- Spelling correction
- Query refinement guidance

### 2. Search Results Display

#### Result Components
- **Title**: Document or content title
- **Snippet**: Relevant excerpt showing query context
- **Source**: Which application or system it's from
- **Metadata**: Author, date, content type
- **Actions**: Open, share, save options
- **Highlights**: Query terms highlighted in snippet

#### Result Types
- **Documents**: Files, PDFs, presentations
- **Messages**: Email, chat messages
- **People**: Colleagues and experts
- **Conversations**: Email threads, message threads
- **Web Pages**: Internal sites and portals

### 3. Filters and Facets

#### Available Filters
- **Content Type**: Documents, emails, messages, etc.
- **Source**: Which application or system
- **Date Range**: Created or modified date
- **Author**: Who created the content
- **Department/Team**: Organizational unit
- **File Type**: PDF, Word, Excel, etc.
- **Language**: Content language

#### Faceted Search
- **Multiple Dimensions**: Filter by multiple criteria simultaneously
- **Result Counts**: Shows how many results match each filter
- **Dynamic Updates**: Results update as filters are applied
- **Clear Filters**: Easy way to remove filters

### 4. Search History

#### Features
- **Recent Searches**: Quick access to previous queries
- **Saved Searches**: Bookmark frequently used searches
- **Search Suggestions**: Based on history and popular queries
- **Privacy**: Users can clear their search history

### 5. Advanced Search Options

#### Query Operators (Optional)
While natural language is primary, advanced users can use:
- **Quotes**: Exact phrase matching
- **Boolean**: AND, OR, NOT operators
- **Field Search**: Search specific metadata fields
- **Wildcards**: Pattern matching

#### Advanced Filters
- **Complex Date Ranges**: Specific time periods
- **Multiple Authors**: Content from several people
- **Combined Filters**: Multiple filter types together

---

## Advanced Search Features

### 1. AI Answers

#### Overview
Instead of just showing a list of documents, Glean can provide direct answers to questions by synthesizing information from authorized content.

#### How It Works
1. **Query Analysis**: Understands the question being asked
2. **Content Retrieval**: Finds relevant content the user can access
3. **Synthesis**: AI generates an answer from multiple sources
4. **Citation**: Provides links to source documents
5. **Permission Check**: Only uses content user is authorized to access

#### Example
**Query**: "What is our company's remote work policy?"
**AI Answer**: "According to company policy documents, employees can work remotely up to 3 days per week with manager approval. Remote work requests should be submitted through the HR portal at least two weeks in advance. [Link to policy document]"

#### Benefits
- **Immediate Answers**: No need to open multiple documents
- **Synthesized Information**: Combines information from multiple sources
- **Transparent**: Cites sources for verification
- **Secure**: Respects permission boundaries

### 2. Related Content Discovery

#### How It Works
After viewing a result, Glean suggests:
- **Similar Documents**: Content with similar topics or themes
- **Related People**: Experts or contributors on the topic
- **Follow-up Content**: Related discussions, updates, or versions
- **Knowledge Graph Connections**: Content connected through relationships

#### Benefits
- **Serendipitous Discovery**: Find information you didn't know you needed
- **Context Building**: Understand topics more completely
- **Expertise Discovery**: Find people working on related topics

### 3. Trending Topics

#### Overview
Glean can identify and surface trending topics within the organization.

#### Signals
- **Search Frequency**: Topics being searched more often
- **Content Creation**: New content on specific topics
- **Engagement**: High interaction with certain content
- **Time Patterns**: Topics gaining attention recently

#### Use Cases
- Stay informed about organizational focus areas
- Discover emerging topics
- Find timely information
- Understand organizational priorities

### 4. Search Analytics (User View)

#### Available Metrics
Users can see (if enabled):
- **Search History**: Their own search patterns
- **Result Effectiveness**: Which results they clicked
- **Time Saved**: Estimates of time saved through efficient search

### 5. Mobile Search

#### Mobile Features
- **Voice Search**: Speak queries instead of typing
- **Mobile-Optimized Interface**: Touch-friendly design
- **Offline Capabilities**: Access to recently viewed content
- **Push Notifications**: Alerts for saved searches or important content

---

## Best Practices for Effective Search

### For Users

1. **Use Natural Language**: Search as you would ask a colleague
2. **Be Specific When Needed**: Add context if results are too broad
3. **Use Filters**: Narrow results by type, date, source, etc.
4. **Review Snippets**: Read result previews before opening
5. **Provide Feedback**: Rate results to help improve relevance
6. **Explore Related Content**: Use suggestions to discover more
7. **Save Frequent Searches**: Bookmark searches you use often

### For Administrators

1. **Monitor Search Analytics**: Understand what users are searching for
2. **Identify Content Gaps**: Find topics with few or no results
3. **Curate Important Content**: Promote critical information
4. **Configure Source Prioritization**: Ensure authoritative sources rank well
5. **Train Users**: Help users understand search capabilities
6. **Gather Feedback**: Collect user input on search quality
7. **Optimize Connectors**: Ensure all important sources are connected

---

## Summary

Glean's search functionality represents a significant advancement over traditional enterprise search. By combining:

- **Semantic Understanding**: Understanding meaning, not just keywords
- **Multi-Source Federation**: Searching across all organizational data
- **AI-Powered Ranking**: Intelligent relevance scoring
- **Personalization**: Context-aware results
- **Natural Language Interface**: Easy-to-use conversational search

Glean makes organizational knowledge easily discoverable, helping employees find information faster and more effectively, regardless of where it's stored or how it's described.

