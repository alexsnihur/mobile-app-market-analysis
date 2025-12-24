# Profitable App Profiles for the App Store and Google Play Markets

A data analysis project exploring app metadata from the App Store and Google Play to identify categories and features that correlate with high user engagement under an ad-revenue model.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Analysis Process](#analysis-process)
- [Results](#results)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview

This project analyzes free Android and iOS apps to guide developers toward building apps with the greatest potential to attract large user bases. The analysis focuses on apps that are free to download, where revenue is generated through in-app advertisements.

The validation strategy for an app idea follows three steps:
1. Build a minimal Android version and release on Google Play
2. Develop further if user response is positive
3. Create an iOS version after six months of profitability

The main goals were to:
1. Identify which app genres are most common on each platform
2. Determine which genres attract the most user engagement
3. Find categories with high potential but lower competition
4. Provide actionable recommendations for app development

## Dataset

Two datasets were obtained from Kaggle:

**Google Play Store Dataset**
- Source: [Kaggle - Google Play Store Apps](https://www.kaggle.com/datasets/lava18/google-play-store-apps/data)
- Original size: 10,841 apps
- Columns: `App`, `Category`, `Rating`, `Reviews`, `Size`, `Installs`, `Type`, `Price`, `Content Rating`, `Genres`, `Last Updated`, `Current Ver`, `Android Ver`

**Apple App Store Dataset**
- Source: [Kaggle - App Store Data Set](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps/data)
- Original size: 7,197 apps
- Columns: `id`, `track_name`, `size_bytes`, `currency`, `price`, `rating_count_tot`, `rating_count_ver`, `user_rating`, `user_rating_ver`, `ver`, `cont_rating`, `prime_genre`, `sup_devices.num`, `ipadSc_urls.num`, `lang.num`, `vpp_lic`

**After Cleaning:**
- Free iOS apps: 3,222
- Free Android apps: 8,864

## Key Findings

### App Store Genre Distribution
- **Games** dominate the market at 58.16% of free apps
- **Entertainment** is a distant second at 7.88%
- Most apps are designed for entertainment rather than practical use

### Google Play Category Distribution
- **Family** leads at 18.91%, followed by **Game** (9.72%) and **Tools** (8.46%)
- Distribution is more balanced between entertainment and practical categories

### Highest Engagement Genres (App Store)
Based on average user ratings:
| Genre | Avg. Ratings |
|-------|-------------|
| Navigation | 86,090 |
| Reference | 74,942 |
| Social Networking | 71,548 |
| Music | 57,327 |
| Weather | 52,280 |

### Highest Engagement Categories (Google Play)
Based on average installs:
| Category | Avg. Installs |
|----------|--------------|
| Communication | 38,456,119 |
| Video Players | 24,727,872 |
| Social | 23,253,652 |
| Photography | 17,840,110 |
| Productivity | 16,787,331 |

### Recommendation
**Books and Reference** and **Productivity** categories show strong engagement without being dominated by a few major apps, making them promising areas for new app development.

## Technologies Used

- **Python 3.13.5**
- **Jupyter Notebook** - for interactive analysis
- **Libraries**:
  - `csv` - reading CSV files

## Project Structure

```
profitable-app-profiles/
│
├── Profitable App Profiles for the App Store and Google Play Markets.ipynb
├── AppleStore.csv
├── googleplaystore.csv
└── README.md
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/profitable-app-profiles.git
cd profitable-app-profiles
```

2. Ensure you have Python 3.x installed

3. Download the datasets:
   - [Google Play Store Apps](https://www.kaggle.com/datasets/lava18/google-play-store-apps/data)
   - [Apple App Store Data Set](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps/data)

4. Update file paths in the notebook to match your local directory

## Usage

1. Open Jupyter Notebook:
```bash
jupyter notebook
```

2. Navigate to `Profitable App Profiles for the App Store and Google Play Markets.ipynb`

3. Run cells sequentially to reproduce the analysis

## Analysis Process

### 1. Data Loading and Exploration
- Read CSV files into lists
- Separate headers from data
- Display initial rows to understand structure

### 2. Data Cleaning
- Removed malformed row (index 10472) from Google Play dataset with missing Category column
- Verified App Store dataset had no structural issues

### 3. Duplicate Removal
- Identified 1,181 duplicate entries in Google Play dataset
- Kept only the entry with the highest review count for each app
- App Store dataset had no duplicates

### 4. Language Filtering
- Created function to detect non-English app names using ASCII values
- Allowed up to 3 non-ASCII characters to accommodate emojis and special characters
- Filtered to 6,183 iOS apps and 9,614 Android apps

### 5. Free App Isolation
- Filtered datasets to include only free apps
- Final counts: 3,222 iOS apps and 8,864 Android apps

### 6. Genre Frequency Analysis
- Built frequency tables for prime_genre (iOS) and Category/Genres (Android)
- Calculated percentage distribution across categories

### 7. Engagement Analysis
- App Store: Used average user ratings as proxy for popularity
- Google Play: Calculated average installs per category
- Identified top-performing and underserved categories

## Results

The analysis revealed distinct patterns across both platforms:

1. **Entertainment Dominates Supply**: Games and entertainment apps are the most common, but this creates intense competition and makes it difficult for new apps to stand out.

2. **Practical Apps Show Strong Engagement**: Categories like Navigation, Reference, and Productivity show high user engagement relative to their market share.

3. **Market Saturation Varies**: Communication and Social Networking are dominated by major players (WhatsApp, Facebook, etc.), while Books and Reference has a more distributed install base.

4. **Cross-Platform Opportunity**: Reference and Productivity categories perform well on both platforms, making them suitable for the three-step validation strategy.

5. **Strategic Recommendation**: A well-designed, focused app in the Reference or Productivity space could stand out more easily than competing in saturated entertainment categories.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- Datasets provided by [Kaggle](https://www.kaggle.com/)
  - Google Play data by [Lavanya Gupta](https://www.kaggle.com/datasets/lava18/google-play-store-apps)
  - App Store data by [Ramanathan Perumal](https://www.kaggle.com/datasets/ramamet4/app-store-apple-data-set-10k-apps)
- Market statistics from [Statista](https://www.statista.com/)
- Project completed as part of Dataquest's Data Analyst in Python learning path

---

**Note**: This analysis uses data from 2018. Current app market trends may differ.