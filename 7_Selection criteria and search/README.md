# Search Process in Science Direct and PubMed

This document outlines the search process in the two databases "Science Direct" and "PubMed," with an emphasis on the search criteria used.

## Science Direct and PubMed

### Search Criteria
1. **Keywords**: The following list of probiotics was used to search the databases:
    - Lactobacillus plantarum
    - Lactobacillus paracasei
    - Lactobacillus acidophilus
    - Lactobacillus casei
    - Lactobacillus rhamnosus
    - Lactobacillus crispatus
    - Lactobacillus gasseri
    - Lactobacillus reuteri
    - Lactobacillus bulgaricus
    - Propionibacterium jensenii
    - Propionibacterium freudenreichii
    - Peptostreptococcus productus
    - Bacillus coagulans
    - Bacillus subtilis
    - Bacillus laterosporus
    - Lactococcus lactis
    - Lactococcus reuteri
    - Lactococcus rhamnosus
    - Lactococcus casei
    - Lactococcus acidophilus
    - Lactococcus curvatus
    - Lactococcus plantarum
    - Enterococcus faecium
    - Pediococcus acidilactici
    - Pediococcus pentosaceus
    - Streptococcus sanguis
    - Streptococcus oralis
    - Streptococcus mitis
    - Streptococcus thermophilus
    - Streptococcus salivarius
    - Bifidobacterium longum
    - Bifidobacterium catenulatum
    - Bifidobacterium breve
    - Bifidobacterium animalis
    - Bifidobacterium bifidum
    - Bacteroides uniformis
    - Akkermansia muciniphila
    - Saccharomyces boulardii

2.  ### List of Cell Lines
    - Caco-2
    - HT-29

3. ### Search string
    "cancer" AND "colon" AND ("RNA-seq" OR "transcriptome")

### Search Process
1. **Build a specific query** for each combination of probiotic and cell line. To do this, each probiotic is taken from the list and combined with each cell line, along with the specific search string.

    **Example:**

    ```python
    cell_lines = ['Caco-2', 'HT-29']
    search_string = '"cancer" AND "colon" AND ("RNA-seq" OR "transcriptome")'
    all_articles_info_scopus = []

    for probiotic in probiotics:
        for cell_line in cell_lines:
            query = f'"{probiotic}" AND "{cell_line}" AND {search_string}'
    ```

2. **Configuring the database API URL**:
    ```python
                    scopus_url = 'https://api.elsevier.com/content/search/scopus'
    ```
3. **Configure the parameters of the request**:
    - `query`: Specific consultation built.
    - `apiKey`: Replace with your own API Key.
    **Example:**
    ```python
                    params = {
                        'query': query,
                        'apiKey': 'TU_API_KEY',  # Replace with your own API Key
                    }    
    ```
4. **Make an entry request** to the database API.
    **Example:**
    ```python
        response = requests.get(scopus_url, params=params)
        response.raise_for_status()  # Throw exception in case of HTTP error
    ```
5. **Getting the data** of the JSON response.
    **Example:**
    ```python
        data = response.json()
    ```
6. **Gathering information** of the articles found:
    - Probiotic
    - Cell_Line
    - Title
    - Authors
    - Journal
    - Year
    - DOI
    - Scopus_ID/PMID
    - URL
    - cited_by
7. **Create a Pandas DataFrame** with the collected information and save it in an Excel file.

## Conclusion

By following the above search processes and applying the specified search criteria, we can efficiently find relevant articles in both Science Direct and PubMed databases. This will help us gather the necessary information for this research on probiotics.