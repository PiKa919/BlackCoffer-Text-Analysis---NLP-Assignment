# BlackCoffer Text Analysis and Sentiment Scoring Project

## Overview
This project performs automated text analysis on articles from specified URLs. It extracts textual data from web articles and computes various metrics including sentiment scores, readability indices, and other text statistics. The analysis is performed using Python and various NLP techniques.

## Features
- Web scraping of articles from given URLs
- Text cleaning and preprocessing
- Sentiment analysis (positive/negative/polarity scores)
- Readability analysis (FOG index)
- Text statistics (word count, syllable count, etc.)
- Personal pronouns detection
- Automatic file encoding detection
- Comprehensive error handling

## Prerequisites
- Python 3.7+
- pip (Python package installer)

## Required Python Packages
```bash
pip install pandas
pip install requests
pip install beautifulsoup4
pip install nltk
pip install chardet
```

## Project Structure
```
project_folder/
├── Input.xlsx                     # Input file containing URLs
├── MasterDictionary/             # Directory containing word lists
│   ├── positive-words.txt        # List of positive words
│   └── negative-words.txt        # List of negative words
├── text_analysis.py              # Main Python script
├── extracted_articles/           # Directory for stored article texts
└── Output Data Structure.xlsx    # Output file with analysis results
```

## Input Format
The input file (`Input.xlsx`) should contain two columns:
- URL_ID: Unique identifier for each article
- URL: Web address of the article to analyze

## Output Metrics
The script calculates the following metrics:
1. POSITIVE SCORE
2. NEGATIVE SCORE
3. POLARITY SCORE
4. SUBJECTIVITY SCORE
5. AVG SENTENCE LENGTH
6. PERCENTAGE OF COMPLEX WORDS
7. FOG INDEX
8. AVG NUMBER OF WORDS PER SENTENCE
9. COMPLEX WORD COUNT
10. WORD COUNT
11. SYLLABLE PER WORD
12. PERSONAL PRONOUNS
13. AVG WORD LENGTH

## How to Run

1. Set up the project structure as shown above

2. Prepare the input files:
   - Place your `Input.xlsx` file in the project root directory
   - Ensure the MasterDictionary folder contains the required word lists

3. Run the script:
```bash
python text_analysis.py
```

4. Check the output:
   - Extracted articles will be saved in the `extracted_articles` directory
   - Analysis results will be saved in `Output Data Structure.xlsx`

## Error Handling
The script includes comprehensive error handling for:
- File encoding issues
- Web scraping failures
- Text analysis errors
- Invalid URLs
- Empty or malformed content

Failed analyses will be logged in the console and will contain default values (zeros) in the output file.

## Metrics Calculation Details

### Sentiment Scores
- **Positive Score**: Count of positive words in the text
- **Negative Score**: Count of negative words in the text
- **Polarity Score**: (Positive Score - Negative Score) / ((Positive Score + Negative Score) + 0.000001)
- **Subjectivity Score**: (Positive Score + Negative Score) / ((Total Words) + 0.000001)

### Readability Metrics
- **FOG Index**: 0.4 * (Average Sentence Length + Percentage of Complex Words)
- **Complex Words**: Words with more than two syllables
- **Average Sentence Length**: Total words / Total sentences

### Other Metrics
- **Word Count**: Total number of cleaned words (excluding stop words)
- **Syllable Count**: Based on vowel groups in words
- **Personal Pronouns**: Counts of I, we, my, ours, us (excluding US as country)
- **Average Word Length**: Total characters in words / Total words

## Troubleshooting

### Common Issues:
1. **Encoding Errors**:
   - The script automatically detects file encoding
   - If errors persist, check the encoding of your dictionary files

2. **Web Scraping Failures**:
   - Check internet connection
   - Verify URL accessibility
   - Consider adding delays between requests if getting blocked

3. **Missing Dependencies**:
   - Run `pip install -r requirements.txt` if provided
   - Install missing packages individually as needed

### Error Messages:
- Check console output for specific error messages
- Failed URLs will be logged with error details
- Results will still be generated with default values for failed analyses

## Author
Ankit Das

## Acknowledgments
- Blackcoffer for the project requirements and specifications
- NLTK for natural language processing tools
- Beautiful Soup for web scraping capabilities