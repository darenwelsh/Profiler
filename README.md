# Profiler
An extension to MediaWiki providing a platform to measure and profile user activity

## GENERAL CONCEPT
There are many ways we can measure and quantify each user's wiki activity including viewing, reviewing, revising, participation, contribution, recognition, interaction, and persistance. This project will build a platform that provides new database tables and mechanisms to record this meta data so as to not strain the MediaWiki core functionality. For example, [Extension:UserJourney](https://github.com/darenwelsh/UserJourney) can run a query on the revision table to determine a user's history and it will generate various reports based on the scope. But each query is large and puts a strain on the server. So this project, at its core, is to provide a way for gathering and querying this data without straining the server. Upon this platform, many approaches to profile and even gamify each user's participation in the wiki will be added. UserJourney already provides several examples to get us started.

One major feature that would be useful in different applications would be to make use of [Wiki Blame](https://en.wikipedia.org/wiki/Wikipedia:WikiBlame). Ideally this tool would be converted into an extension and this Profiler extension would have a dependency on that new WikiBlame extension. With this capability, users could identify who actually contributed the content that answered their question. They could then thank the author(s) for their contribution.

Another major feature to include would be the ability to calculate the "value" of each contribution based on multiple factors. For example, if a user adds some content that has numerous incoming links (pages that link to it) then it would seem that content is valuable to others. The score should increase if those links are made from different contributors. Otherwise one person could artificially inflate the score of their revision by adding links. Furthermore, value could be calculated by how often other users view and thank the author for this bit of content.

## REQUIREMENTS
1. Provide a MediaWiki database modification that allows for tracking these meta data and calculating metrics without significant strain on the server.
1. Metrics should be updated as close to real-time as possible. A simple solution would be to run maintenance tasks at night to query the core database and update scores and other metrics in a separate table. But these values would only be updated nightly. It is more ideal if a user sees real-time feedback for their actions (positive reinforcement).
1. 
