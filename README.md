# Linked Data & Archival Metadata to MARC21 Converter

An automated Python pipeline designed for Google Colab that converts Excel metadata of archival document collections (e.g., Francke Nachlass) into standardized MARC21 (`.mrk`) library records.

## Key Features

* **Automated Data Processing:** Normalizes raw archival metadata, extracts HTML links, cleans text formatting, and parses dates.
* **Authority URI Mapping:** Extracts linked data URIs from metadata (prioritizing LC, VIAF, Wikidata, and GeoNames) and formats them into appropriate MARC subfields (`$0` for LC URIs, `$1` for Wikidata, VIAF, and GeoNames URIs).
* **Location Standardization:** Normalizes historical sender locations in the output MARC records (MARC `264 $a` Place of production/publication) via a reference mapping file (`sender_place_new.xlsx`). This process ensures MARC/RDA compliance for institutional discovery.
* **Comprehensive MARC21 Coverage:** Maps control fields (`LDR`, `001`, `005`, `008`), title/creators (`100`, `245`, `246`), RDA carriers (`300`, `336`–`338`), notes (`500`, `505`, `506`, `520`, `524`, `530`, `540`), and subject access headings (`600`, `610`, `650`, `651`, `653`, `655`).
* **Audit & Execution Logging:** Generates detailed log files (`MARC_MASTER_LOG.csv` and `MARC_LOG_SUMMARY.csv`) tracking field generation, fallback rules, and skipped inputs.
