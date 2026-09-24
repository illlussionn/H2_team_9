# **Reddit Gambling Communities Analysis (May – October 2024)**

### **Project Overview**
This project is dedicated to extracting, processing, and analyzing large-scale Reddit dataset dumps focused on **gambling, sports betting, poker, and gambling addiction support communities**.

The analysis covers a 6-month timeframe (**May 2024 – October 2024**) and aims to explore user engagement, submission-to-comment ratios, and activity dynamics across key subreddits.


### **Team Members**
* **Polina Hubanova** (Months: May, June, July 2024)
* **Zubenko Heorhii** (Months: August, September, October 2024)


###  **Target Subreddits**
The dataset is filtered using regex patterns for the following specific subreddits:
* Gambling & Online Casinos: `gambling`, `slots`, `onlinecasino`, `casino`, `ChumbaCasino`, `casinoadvertising`
* Poker & Skill Games: `poker`, `Poker_Theory`, `GGPoker`, `pokerogue`
* Sports Betting: `sportsbook`, `sportsbetting`
* Recovery & Support: `problemgambling`, `casinoaddiction`, `compulsivegambling`



### Repository Structure
```
+-- config.json                       # Configuration file containing target subreddits
+-- reddit_zst_filter_zstandard.py    # Main Python script for filtering .zst dumps
+-- reddit_filter_utils.py            # Utility functions for parsing and formatting
+-- analysis.ipynb                    # Jupyter Notebook for data aggregation and visualization
+-- metrics_2024_05.csv               # Aggregated metrics for May 2024
+-- metrics_2024_06.csv               # Aggregated metrics for June 2024
+-- metrics_2024_07.csv               # Aggregated metrics for July 2024
+-- metrics_2024_08.csv               # Aggregated metrics for August 2024
+-- metrics_2024_09.csv               # Aggregated metrics for September 2024
+-- metrics_2024_10.csv               # Aggregated metrics for October 2024
`-- README.md                         # Project documentation
```

> **Note:** The full filtered CSV datasets (`RS_2024-XX.csv` and `RC_2024-XX.csv`) exceed Git storage limits and are hosted on **Google Drive** [Link in Submission PDF].


## Setup & Installation 

### Prerequisites
* Python 3.10+
* Required libraries: `zstandard`, `pandas`, `matplotlib`, `seaborn`

Install dependencies via Terminal:
```bash
pip install zstandard pandas matplotlib seaborn 
```


### How to Run the Pipeline
To process raw Reddit .zst dumps for a specific month, place the submission (RS_*.zst) and comment (RC_*.zst) files in the root folder and run:
```bash
python reddit_zst_filter_zstandard.py . --field subreddit --value "casino|casinoaddiction|casinoadvertising|gambling|problemgambling|compulsivegambling|poker|sportsbook|sportsbetting|slots|onlinecasino|pokerogue|ChumbaCasino|GGPoker|Poker_Theory" --regex --format csv --output_dir .
```


### Aggregating Metrics & Visualization
Open and execute `analysis.ipynb` in Jupyter Notebook / PyCharm to:
* Parse generated RS_*.csv and RC_*.csv files.
* Calculate total submissions, comments, and engagement metrics per subreddit.
* Export monthly metrics to metrics_2024_XX.csv.
* Plot activity distributions, submission vs. comment breakdown, and monthly trend lines.


### Summary Statistics
* **Timeframe:** May 2024 – October 2024 (6 months)
* **Total Records Matched:** ~1.5+ Million entries
* **Combined CSV Dataset Size:** ~1.5+ GB