#  DNS Log Analysis Using Splunk SIEM

![Splunk](https://img.shields.io/badge/Splunk-Enterprise-black?style=for-the-badge&logo=splunk&logoColor=green)
![Security](https://img.shields.io/badge/Security-SIEM-blue?style=for-the-badge&logo=shield&logoColor=white)
![DNS](https://img.shields.io/badge/DNS-Log%20Analysis-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

##  Overview

This project demonstrates how to upload, parse, and analyze **DNS (Domain Name System) log files** using **Splunk Enterprise SIEM**. DNS logs are a critical data source in cybersecurity, providing visibility into network activity and helping detect threats such as:

- DNS tunneling
- Command & Control (C2) communication
- Data exfiltration
- Malicious domain lookups

---

##  Screenshots

| Step | Description |
|------|-------------|
| ![Raw Events](raw_events.png) | Raw DNS events view (422,130 events) |
| ![Domain Stats](domain_stats.png) | Domain frequency statistics |
| ![Top Domains](top_domains.png) | Top 10 most queried domains |
| ![Most Queried](most_queried.png) | Most queried domain identified |

---

Screenshot 2026-03-10 163714.png
Screenshot 2026-03-10 163801.png
Screenshot 2026-03-10 163835.png
Screenshot 2026-03-10 164047.png
Analyzing DNS Log Files Using Splunk SIEM
Introduction
DNS (Domain Name System) logs are crucial for understanding network activity and identifying potential security threats. Splunk SIEM (Security Information and Event Management) provides powerful capabilities for analyzing DNS logs and detecting anomalies or malicious activities.
Prerequisites
Before analyzing DNS logs in Splunk, ensure the following:
* Splunk instance is installed and configured.
* DNS log data sources are configured to forward logs to Splunk.
Steps to Upload Sample DNS Log Files to Splunk SIEM
1. Prepare Sample DNS Log Files
* Obtain sample __DNS log file__ in a suitable format (e.g., text files).
* Ensure the log files contain relevant DNS events, including source IP, destination IP, domain name, query type, response code, etc.
* Save the sample log files in a directory accessible by the Splunk instance.
2. Upload Log Files to Splunk
* Log in to the Splunk web interface.
* Navigate to Settings > Add Data.
* Select Upload as the data input method.
3. Choose File
* Click on Select File and choose the sample DNS log file you prepared earlier.
4. Set Source Type
* In the Set Source Type section, specify the source type for the uploaded log file.
* Choose the appropriate source type for DNS logs (e.g., dns or a custom source type if applicable).
5. Review Settings
* Review other settings such as index, host, and sourcetype.
* Ensure the settings are configured correctly to match the sample DNS log file.
6. Click Upload
* Once all settings are configured, click on the Review button.
* Review the settings one final time to ensure accuracy.
* Click Submit to upload the sample DNS log file to Splunk.
7. Verify Upload
* After uploading, navigate to the search bar in the Splunk interface.
* Run a search query to verify that the uploaded DNS events are visible.

index=<your_dns_index> sourcetype=<your_dns_sourcetype>
Steps to Analyze DNS Log Files in Splunk SIEM
1. Search for DNS Events
* Open Splunk interface and navigate to the search bar.
* Enter the following search query to retrieve DNS events

index=* sourcetype=dns_sample
Extract Relevant Fields
Identify key fields in DNS logs such as source IP, destination IP, domain name, query type, response code, etc.
As mentioned below, | regex _raw="(?i)\b(dns|domain|query|response|port 53)\b": This regex searches for common DNS-related keywords in the raw event data.
Example extraction command:
index=* sourcetype=dns_sample | regex _raw="(?i)\b(dns|domain|query|response|port 53)\b"
Identify Anomalies
Look for unusual patterns or anomalies in DNS activity.
Example query to identify spikes
index=_* OR index=* sourcetype=dns_sample  | stats count by fqdn
Find the top DNS sources
Use the top command to count the occurrences of each query type:
index=* sourcetype=dns_sample | top fqdn, src_ip
Investigate Suspicious Domains
Search for domains associated with known malicious activity or suspicious behavior.
Utilize threat intelligence feeds or reputation databases to identify malicious domains such virustotal.com
Example search for known malicious domains:
index=* sourcetype=dns_sample fqdn="maliciousdomain.com"
Conclusion
Analyzing DNS log files using Splunk SIEM enables security professionals to detect and respond to potential security incidents effectively. By understanding DNS activity and identifying anomalies, organizations can enhance their overall security posture and protect against various cyber threats.
Feel free to customize these steps according to your specific use case and requirements.
Happy analyzing!

i work in this project and i finish it and iwan to do it in github okay

Show more
4:43 PM

Check available skills
Check available skills
I'll help you create a professional GitHub README and project structure for your DNS Log Analysis project. Let me create the files you need.


Created 2 files, read a file
Created 2 files, read a file
Here's your GitHub-ready project! 🎉 To publish it:

Steps to put it on GitHub:

Go to github.com → New Repository
Name it something like dns-splunk-analysis
Make it Public (so others can see your work)
Create this folder structure and upload:
README.md ← the file above
queries/spl_queries.md ← your SPL queries
screenshots/ ← add your 4 Splunk screenshots from this project
Tips to make it stand out:

Add your 4 screenshots to a screenshots/ folder — the README already references them
Write a short bio in the Author section with your LinkedIn if you have one
Pin the repo on your GitHub profile so recruiters see it
Your project is solid — 422K events analyzed, regex extraction, domain frequency ranking, and clear findings. That's great portfolio material! 💪

Readme
Document · MD 
Spl queries
Document · MD 

excerpt_from_previous_claude_message.txt
4 lines

txt

i create it how to uploed

4:50 PM
Here's how to upload your files to GitHub step by step:

1. Go to your repository on GitHub Click on your repo dns-splunk-analysis

2. Upload the README.md

Click "Add file" → "Upload files"
Drag and drop your README.md file
Click "Commit changes"
3. Create the screenshots/ folder & upload images

Click "Add file" → "Upload files"
Before dropping files, type screenshots/ in the path box at the top — GitHub will create the folder automatically
Upload your 4 Splunk screenshots
Click "Commit changes"
4. Create the queries/ folder & upload SPL file

Click "Add file" → "Upload files"
Type queries/ in the path box
Upload your spl_queries.md file
Click "Commit changes"
💡 Easier alternative — do it all at once:

On your computer, create a folder called dns-splunk-analysis
Inside it, put README.md, a screenshots folder with your 4 images, and a queries folder with spl_queries.md
Then on GitHub click "Upload files" and drag the entire folder — GitHub will preserve the structure automatically
After uploading, your repo will look professional and complete! Would you like help with anything else for the project?


excerpt_from_previous_claude_message.txt
1 line

txt

where

4:51 PM
On your GitHub repository page, look here:

Click the "Add file" button — it's near the top right of your repository, next to the green "Code" button:

Your repo page looks like this:
┌─────────────────────────────────────────┐
│  📁 dns-splunk-analysis                 │
│                                         │
│  [Add file ▾]  [<> Code ▾]              │  ← Click "Add file"
│                                         │
└─────────────────────────────────────────┘
Then a dropdown appears with 2 options:

"Create new file" — for typing content
"Upload files" ← click this one
If your repo is brand new and empty, you'll see a different screen with a direct link that says "uploading an existing file" — click that instead.

1773161553080_image.png
where

4:52 PM
Your repo is empty! I can see it. Click this link:

"uploading an existing file" — it's right there on your screen in the blue box:

"Get started by creating a new file or uploading an existing file"

Click those blue words "uploading an existing file" and it will take you directly to the upload page! 👆

ok than

4:58 PM
Great! Now on the upload page:

Drag and drop your files onto the page, or click "choose your files"
Upload these files:
README.md ← from the files I created for you
Your 4 Splunk screenshots (the images from this conversation)
At the bottom, you'll see "Commit changes" — click that green button
Refresh your repo page and everything will be there! ✅
Let me know if you get stuck at any step! 😊


1773162289817_dns (2).log.gz
gz

i want to add thas i work with this file

5:04 PM
Great! That's your actual DNS log file (dns_2_log.gz). You can add it to your GitHub repo too.

On the upload page, just drag and drop this file along with your other files, then commit.

Also, update your README to mention it. I'll add a note about the dataset:


Edited 2 files, viewed a file, read a file
Edited 2 files, viewed a file, read a file
README is updated! Now upload these to GitHub:

dns_2_log.gz → put it in a folder called sample_data/
Updated README.md → replace the old one
Your repo will now show the real log file you worked with, which makes it look much more professional! 💪

Readme
Document · MD 





Claude is AI and can make mistakes. Please double-check responses.
Readme · MD
Copy

# 🔍 DNS Log Analysis Using Splunk SIEM

![Splunk](https://img.shields.io/badge/Splunk-Enterprise-black?style=for-the-badge&logo=splunk&logoColor=green)
![Security](https://img.shields.io/badge/Security-SIEM-blue?style=for-the-badge&logo=shield&logoColor=white)
![DNS](https://img.shields.io/badge/DNS-Log%20Analysis-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

## 📌 Overview

This project demonstrates how to upload, parse, and analyze **DNS (Domain Name System) log files** using **Splunk Enterprise SIEM**. DNS logs are a critical data source in cybersecurity, providing visibility into network activity and helping detect threats such as:

- DNS tunneling
- Command & Control (C2) communication
- Data exfiltration
- Malicious domain lookups

---

## 📸 Screenshots

| Step | Description |
|------|-------------|
| ![Raw Events](screenshots/raw_events.png) | Raw DNS events view (422,130 events) |
| ![Domain Stats](screenshots/domain_stats.png) | Domain frequency statistics |
| ![Top Domains](screenshots/top_domains.png) | Top 10 most queried domains |
| ![Most Queried](screenshots/most_queried.png) | Most queried domain identified |

---

##  Dataset

| File | Format | Size | Events |
|------|--------|------|--------|
| `dns_2_log.gz` | Gzip compressed log | — | 422,130 |

- **File:** `dns_2_log.gz` — real DNS traffic log used in this analysis
- **Sourcetype:** `dns_sample`
- **Time Range:** 3/10/26 3:19:00 PM → 3:20:00 PM
- **Loaded into Splunk via:** Settings → Add Data → Upload

---
##  Prerequisites

- Splunk Enterprise (installed and running)
- DNS log sample file (`dns_sample` sourcetype)
- Basic knowledge of SPL (Splunk Processing Language)

---

##  Setup

### 1. Upload DNS Log File to Splunk

1. Log in to Splunk Web Interface
2. Go to **Settings → Add Data → Upload**
3. Select your DNS log file
4. Set **Source Type** to `dns_sample`
5. Configure index, host, and sourcetype
6. Click **Submit**

### 2. Verify the Upload

```spl
index=* sourcetype="dns_sample"
```

---

##  SPL Queries Used

### Basic Event Search
```spl
host=Abdelaziz sourcetype="dns_sample"
```
> Returns all 422,130 DNS events from the configured host.

---

### Extract Domain Names & Count by Domain
```spl
host=Abdelaziz sourcetype="dns_sample"
| rex field=_raw "(?<domain>[A-Za-z0-9.-]+\.(com|net|org|arpa|io|fr|ma))"
| stats count by domain
| sort -count
```
> Uses regex extraction to parse domain names from raw log data, then ranks them by frequency.

---

### Top 10 Most Queried Domains
```spl
host=Abdelaziz sourcetype="dns_sample"
| rex field=_raw "(?<domain>[A-Za-z0-9.-]+\.(com|net|org|arpa|io|fr|ma))"
| top domain
```
> Returns the top 10 domains with count and percentage.

---

### Most Queried Domain (Single Result)
```spl
host=Abdelaziz sourcetype="dns_sample"
| rex field=_raw "(?<domain>[A-Za-z0-9.-]+\.(com|net|org|arpa|io|fr|ma))"
| stats count by domain
| sort -count
| head 1
```
> Identifies the single most queried domain — `teredo.ipv6.microsoft.com` with **39,119 queries**.

---

## 📊 Key Findings

| Rank | Domain | Count | % of Total |
|------|--------|-------|------------|
| 1 | `teredo.ipv6.microsoft.com` | 39,119 | 12.94% |
| 2 | `tools.google.com` | 14,051 | 4.65% |
| 3 | `www.apple.com` | 13,069 | 4.32% |
| 4 | `time.apple.com` | 12,793 | 4.23% |
| 5 | `safebrowsing.clients.google.com` | 11,423 | 3.78% |
| 6 | `44.206.168.192.in-addr.arpa` | 7,157 | 2.37% |
| 7 | `stats.norton.com` | 5,537 | 1.83% |
| 8 | `imap.gmail.com` | 5,434 | 1.80% |
| 9 | `www.google.com` | 5,183 | 1.71% |
| 10 | `ratings-wrs.symantec.com` | 4,464 | 1.48% |

> **Total Events Analyzed:** 422,130 | **Unique Domains Found:** 3,947

---

##  Analysis Insights

- **`teredo.ipv6.microsoft.com`** dominates the traffic — this is Windows' IPv6 tunneling mechanism, normal in Windows environments but worth monitoring for volume anomalies.
- High queries to **Norton** and **Symantec** domains suggest endpoint security software is active on the network.
- **Reverse DNS lookups** (`in-addr.arpa`) appear frequently, which is typical behavior for internal network resolution.
- Traffic to **Google**, **Apple**, and **Microsoft** domains is expected in a corporate environment.

---


##  References

- [Splunk Documentation](https://docs.splunk.com)
- [DNS Security Best Practices](https://www.cisa.gov/dns-security)
- [MITRE ATT&CK - DNS](https://attack.mitre.org/techniques/T1071/004/)

---

##  Author

**Abdelaziz**  
Cybersecurity Analyst | Splunk SIEM  

---

##  License

This project is for educational purposes. Feel free to use and adapt.
