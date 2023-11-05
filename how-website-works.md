# How indicozy's personal blog works
**TLDR**: Use [Obsidian Publish](https://obsidian.md/publish)

1. Obsidian has git extension, which commits and pushes automatically.
2. Git has `pre-commit` hook, which triggers markdown parser. It also backups notes in GitHub.
3. . Parser does many stuff:
	1. Generate global Gexf file of connection between all notes.
	2. Generates separate Gexf file for every note's connections.
	3. Generates JSON file for Orama search engine. 
	4. Converts Markdown to HTML.
	All generated data is then sent to CloudFlare R2 Bucket for caching. I decided to store cached data rather than Markdown files so server will skip conversion process.
4. Several API's bring life to the website:
	1. GitHub users API parses:
		1. Hireable am I or not;
		2. City I am located;
		3. Bio;
	2. Weather API shows the temperature in the city I am at.
	3. AQI shows the Air Quality Level in the city.
	4. Timezone API shows what timezone I am at.
5. Qwik then:
	1. Caches compiles and caches data from bucket and APII
	2. Clients require no JavaScript.
	4. Lazy loads JavaScript on need, without bloating the client's user experience
	5. Requires no hydration because Qwik works by Resumability;
	6. CSS is written from scratch, so it requires much less data and external libraries to be sent;
