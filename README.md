# Resilient-Asynchronous-Redfin-Scraper-Make.com-Apify-
This project demonstrates how I built a fully automated, resilient, and scalable system to collect real-time property data from Redfin, using Make.com, Apify, and Google Sheets.
This project demonstrates how I built a fully automated, resilient, and scalable system to collect real-time property data from Redfin, using Make.com, Apify, and Google Sheets.

#🚀 Overview

The goal was to design a hands-free automation that continuously gathers property listings and their key data points (price, Redfin Estimate, address, etc.) — even with strong anti-scraping measures and dynamic JavaScript rendering on Redfin pages.

To achieve this, I combined:

Apify → running a full browser instance (playwright:adaptive) to simulate real users.

Make.com → orchestrating and scheduling the entire workflow.

Google Sheets → serving as a simple, reliable job queue.

#⚙️ System Architecture

The automation runs through a two-part asynchronous queue system:

#🧩 Scenario 1 – “Collector”

Runs once per day:

Finds new Redfin property URLs.

Adds them to a Google Sheet “To-Do” list.

#🔁 Scenario 2 – “Scraper”

Runs every 15 minutes:

Fetches one URL from the sheet.

Uses Apify Playwright crawler to extract data.

Saves it to the main database and removes it from the queue.

#This structure ensures:

✅ No timeouts

⚡ Efficient performance

🧱 Scalable 24/7 operation

🧭 Zero manual intervention

#🧠 Key Highlights

Used Playwright browser engine to bypass anti-bot systems.

Captured JavaScript-rendered data invisible to standard scrapers.

Built a queue-based asynchronous workflow to distribute load.

Achieved continuous, reliable scraping without failures.

Designed for resilience, scalability, and clarity in automation.

#📊 Example Output
URL	                                                                                      Price	      estimated price	Sale history
https://www.redfin.com/CA/San-Francisco/2926-25th-St-94110/home/197009327	                $999,000	  $1,046,404	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/2122-Mason-St-94133/home/543274                  	$2,680,000	$2,675,353	    Nov 6, 2025
https://www.redfin.com/CA/San-Francisco/2926-2930-25th-St-94110/unit-2928/home/198885893	$899,000	  $921,643	      Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/1661-Palou-Ave-94124/home/1122090	                $1,300,000	$1,277,659	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/1942-24th-Ave-94116/home/1652561	                $1,649,000	$1,818,474	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/448-Pennsylvania-Ave-94107/home/734267	          $1,995,000	$1,705,000	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/3539-Fillmore-St-94123/home/1803888	              $3,595,000	$3,580,838	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/1647-24th-Ave-94122/home/1894673	                $1,195,000	$1,540,049	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/425-1st-St-94105/unit-5404/home/17304781	        $2,500,000	$1,200,000	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/988-Harrison-St-94107/unit-ZB6/home/198874846	    $649,000	  $649,296	      Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/310-Townsend-St-94107/unit-305/home/17305528	    $999,000	  $1,000,900	    Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/988-Harrison-St-94107/unit-ZE5/home/198874451	    $639,000	  $638,558	      Nov 5, 2025
https://www.redfin.com/CA/San-Francisco/988-Harrison-St-94107/unit-XC8/home/198873942	    $1,029,000	$1,026,079	    Nov 5, 2025

#💡 Learnings

This project reinforced the importance of:

Asynchronous architecture in workflow automation.

Breaking large jobs into smaller, independent tasks.

Designing for failure tolerance and scalability from the start.

#🧰 Tools & Platforms

🧠 Make.com

🌐 Apify (Playwright Crawler)

📊 Google Sheets API

🗃️ Database Integration (SQL/NoSQL)

🕒 Asynchronous Scheduling
