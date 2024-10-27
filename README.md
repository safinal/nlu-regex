# Project Report (NLU, Fall 2024)

### Table of Contents
1. Abstract
2. Introduction
3. Tools and Dataset
4. Data Preprocessing Steps
5. Results and Analysis
6. Conclusions
7. References

### Abstract
In this project, we carried out text data preprocessing on a dataset from Yelp reviews. The main tasks included extracting specific information like dates, times, URLs, and prices, and then cleaning the text by removing URLs, emojis, numbers, stopwords, and punctuation, followed by lemmatization. Finally, we analyzed the text to count total words and identify the ten most common words in the corpus.

### Introduction
Natural Language Processing (NLP) plays a crucial role in extracting and cleaning text data, enabling better comprehension and usage in various applications. This project focuses on preprocessing Yelp review text data to facilitate further analysis or machine learning tasks. We detail the extraction of specific patterns from the text and transformation steps, resulting in a clean dataset usable for downstream tasks like sentiment analysis or topic modeling.

### Tools and Dataset
- **Programming Language**: Python
- **Libraries**: pandas, re (regular expressions), nltk (Natural Language Toolkit)
- **Dataset**: Yelp polarity dataset hosted at "hf://datasets/fancyzhx/yelp_polarity/"

The dataset comprises two primary splits: train and test. For this project, we focused on the training dataset.

### Data Preprocessing Steps
The preprocessing pipeline included several steps, each designed to clean and transform the text data.

#### Part 1: Extract Specific Patterns
1. **List the dates in the sentences**:
   - Using regular expressions, we searched for dates in formats like MM/DD/YYYY or January 1, 2020.
   
2. **List the hours in sentences**:
   - We used regular expressions to identify time patterns such as HH:MM AM/PM.
   
3. **List the web links**:
   - Regular expressions were employed to detect URLs starting with http, https, or www.
   
4. **List names starting with "Dr"**:
   - We targeted names starting with "Dr." followed by a capital letter and additional lowercase letters.
   
5. **List dollar price values**:
   - We extracted monetary values indicated by the $ symbol followed by digits.

#### Part 2: Clean the Text
1. **Remove web links**:
   - Used regular expressions to eliminate URLs from the text, enhancing readability.

2. **Remove emojis**:
   - Compiled an extensive regex pattern covering a wide range of emojis and non-text symbols to be removed.

3. **Remove numbers**:
   - Applied regex to strip out all numerical characters.

4. **Remove stopwords**:
   - Leveraged NLTK’s list of English stopwords to filter out common but uninformative words.

5. **Remove punctuation**:
   - Utilized Python’s string translation to expunge all punctuation marks.

6. **Lemmatization**:
   - Employed NLTK’s WordNetLemmatizer to convert words to their base or root form, standardizing the text.

### Results and Analysis
1. **Extracted Patterns**:
   - We successfully identified instances of dates, times, URLs, names starting with "Dr.", and monetary values within the text reviews. Such pattern extraction is vital for various analytical purposes, including temporal analysis or sentiment analysis by specific date ranges.
   
2. **Data Cleaning**:
   - By removing non-textual elements and standardizing the text, we improved the quality of the dataset, making it more suitable for further analysis or machine learning applications.
   
3. **Word Count and Most Common Words**:
   - The total count of words in the cleaned text was calculated.
   - The ten most frequent words were identified, providing insights into the common topics or themes prevalent in Yelp reviews.

### Conclusions
This project demonstrates a comprehensive approach to text data preprocessing, crucial for effective natural language processing and analysis. By extracting meaningful patterns and cleaning the text, we have transformed the Yelp review data into a cleaner and more analyzable format. The steps and methods outlined can be adapted and applied to other text datasets, showcasing the versatility of the techniques used.

### References
- NLTK: Natural Language Toolkit. Retrieved from http://www.nltk.org/
- pandas: Data manipulation and analysis library for Python. Retrieved from https://pandas.pydata.org/
- Yelp Polarity Dataset. Retrieved from https://huggingface.co/datasets/fancyzhx/yelp_polarity
