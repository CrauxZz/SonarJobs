SonarJobs — single-file local app
Open index.html in Chrome or Edge on Windows. No installation, account, backend, or database required. It requires internet access to query feeds and load the PDF/DOCX readers.

The interface is available in Spanish, English, and French via the header selector. The preference is retained only while the tab is open.

Features
Reads PDF, DOCX, or TXT CVs in the browser. The text lives only in memory while the page is open.

Queries public feeds from Remotive, Remote OK, Jobicy, and Arbeitnow; deduplicates, filters, and sorts results in the browser.

Compares CV words against each job’s title, tags, and description. Shows matching terms as evidence; the percentage is textual similarity, not a probability of being hired.

Prepares a short editable cover letter based on terms present in the CV; lets you copy or download it.

Opens the original posting so the person can complete and submit it directly to the employer.

Does not use localStorage, its own cookies, analytics, accounts, or a profile server. When the tab is closed, the CV and results in memory disappear.

Privacy and network
The document is never uploaded to SonarJobs or included in queries. Queries go to the Remotive and Arbeitnow endpoints; the optional job and location fields are filtered in the browser and are not sent. PDF.js and Mammoth are downloaded from cdnjs only when PDF or DOCX is selected. Accessing those sources may reveal the IP address to the provider/CDN, as with any web request.

Each source retains its attribution and posting link; Remotive, for example, requires linking to its original job posting and acknowledges delays of up to 24 hours. Remote OK and Jobicy allow public feeds, although the public URL usually leads first to the job board portal and not always to the ATS form. Jobs, coverage, feed availability, CORS, and each provider’s terms may change; always review the original offer.

Limitation of external submissions
From an HTML file opened as file://, the browser cannot universally complete forms on other domains: site isolation, logins, CAPTCHA, and each ATS’s own flows prevent it. That is why SonarJobs prepares the text and opens the official portal; the candidate reviews and clicks submit there. It does not use credentials, browser automation, or mass submissions.

To complete an application without intervention, each employer/ATS would need to be integrated through an authorized application API, typically with OAuth and a secure backend to protect credentials. That can no longer be done securely with a single local HTML file.

Scope
Search covers the vacancies exposed by these feeds; it cannot list the entire web. Many companies and job boards do not offer public APIs, and protected pages are not scraped. This format scales in distribution (one file that each person runs locally), but it is not a centralized service: it does not store CVs or sync state across devices. Adding more countries, job boards, or portals requires an API/feed permitted by each source.

