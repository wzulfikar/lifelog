# Information  Retrieval Technology
# Chapter 1
- The field of computer science that is most involved with R&D for search is information retrieval (IR)
- “Information retrieval is a field concerned with the structure, analysis, organization, storage, searching, and retrieval of information.” (Salton, 1968)
- example of bank db query vs sea rch engine query
	- bank db query : Find records with balance > $50,000 in branches located in Amherst, MA.
	- search engine query : bank scandals in western mass
- IR Core Issue: Comparing the query text to the document text and determining what is a good match
- Dimensions of IR : Content, Applications, Tasks
	- Content : text, image, video, audio, etc
	- Applications : Enterprise search, desktop search, P2P search, etc
	- Tasks : Ad-hoc search, classification, question answering
- Big Issues in IR : relevance, evaluation, users and information needs, 

>A search engine is the practical application of information retrieval techniques to large scale text collections

- Search Engine Issues: 
	- performance
	- incorporating new data
	- scalability
	- adaptability
	- specific problems, eg. spam

>New subfield called adversarial IR, since spammers are “adversaries” with different goals

# Chapter 2

- Search Engine Architecture : Effectiveness (quality of results) & Efficiency (response time & throughput)
- Indexing process : text acquisition, text transformation, index creation
- Query process : user interaction, ranking, evaluation

### Indexing Process
- Text Acquisition :
	- Crawler
	- Feeds
	- Conversion
	- Document Data Store
- Text Transformation :
	- Parser
	- Stopping
	- Stemming
	- Link Analysis
	- Information Extraction
	- Classifier
- Index Creation : 
	- Document Statistics
	- Weighting
	- Inversion (core of indexing process, converts document-term to term-document)
	- Index Distribution

### Query Process
- User Interaction
	- Query Input
	- Query Transformation
	- Results Output
- Ranking
	- Scoring
	- Performance Optimization
	- Distribution
- Evaluation
	- Logging
	- Rangking Analysis
	- Performance Analysis

# Chapter 3
