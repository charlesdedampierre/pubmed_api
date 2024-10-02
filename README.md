# pubmed_api

1) Download the package to connect to the Pubmed API

```bash
sh -c "$(curl -fsSL https://ftp.ncbi.nlm.nih.gov/entrez/entrezdirect/install-edirect.sh)"
sh -c "$(wget -q https://ftp.ncbi.nlm.nih.gov/entrez/entrezdirect/install-edirect.sh -O -)"
```

Full documentation is here: <https://www.ncbi.nlm.nih.gov/books/NBK179288/>

2) Extract information as XML format on your computer (This can take up to 1/2 hours depending on the size of the database)

```bash
esearch -db pubmed -query "autism" | efetch -format xml > autism.xml
```

3) run convert_xml_to_json.ipynb to transform the .xml file into a directory (saved_json) of json files
4) run extract_info.ipynb to transform the json into a csv.
