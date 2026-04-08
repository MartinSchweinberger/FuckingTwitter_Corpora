# F%$# Twitter: A Corpus-Based Analysis of Vulgar Language on Twitter

[![R](https://img.shields.io/badge/R-%3E%3D4.0-blue.svg)](https://www.r-project.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Issues](https://img.shields.io/github/issues/MartinSchweinberger/FuckingTwitter_Corpora)](https://github.com/MartinSchweinberger/FuckingTwitter_Corpora/issues)
[![Forks](https://img.shields.io/github/forks/MartinSchweinberger/FuckingTwitter_Corpora)](https://github.com/MartinSchweinberger/FuckingTwitter_Corpora/network)

This repository contains all the code and resources associated with the paper:

**Schweinberger, M., M. Laitinen, M. Haugh, P. Rautionaho, M. Fatemi, S.Hames, & M. Takahashi. (2027). _F%$# Twitter: A corpus-based analysis of vulgar language on Twitter_. Corpora 27(1).** 

The repository allows researchers to explore, understand, and reproduce the analyses presented in the paper.

---

## Repository Structure

| Folder / File | Description |
|---------------|-------------|
| `data/`       | Raw and processed datasets used in the analysis. Due to Twitter’s Terms of Service, only aggregated or anonymized data are included. |
| `docs/`       | Documentation, notes, and supplementary material related to the analysis. |
| `images/`     | Figures and visualizations generated in the analysis. |
| `tables/`     | Result tables created during the analysis. |
| `renv/`       | R environment files to ensure reproducibility with exact package versions. |
| `.Rprofile`   | Project-specific R settings. |
| `.update`     | Miscellaneous scripts for updates and maintenance. |
| `FuckingTwitter.Rproj` | RStudio project file for easy project management. |
| `FuckingTwitter_Part01.Rmd` – `FuckingTwitter_Part04.Rmd` | Step-by-step R Markdown scripts for data processing, analysis, and visualization. |

---

## Getting Started

To reproduce the analyses, follow these steps:

1. **Clone the repository**  
   ```bash
   git clone https://github.com/MartinSchweinberger/FuckingTwitter_Corpora.git

2. **Open the R project**  
   Open `FuckingTwitter.Rproj` in RStudio.  

3. **Install dependencies**  
   The project uses `renv` to manage package versions. Install `renv` if necessary, and restore the environment:  
   ```R
   install.packages("renv")
   renv::restore()

4. **Run the analysis**  
The analysis is divided into four R Markdown scripts (`FuckingTwitter_Part01.Rmd` – `FuckingTwitter_Part04.Rmd`) which should be executed in order. These scripts cover:

- Data preprocessing and cleaning
- Corpus analysis and tokenization
- Statistical analysis and modeling
- Visualizations and result tables

---

## Reproducibility

This repository is designed to maximize reproducibility:

- All code is included and documented.
- The `renv` environment ensures that exact R package versions can be restored.
- Datasets comply with Twitter’s Terms of Service, ensuring ethical use and privacy protection.

---

## License

This project is licensed under MIT License.

---

## Citation

If you use this repository or the code in your research, please cite:

> Schweinberger, M., M. Laitinen, M. Haugh, P. Rautionaho, M. Fatemi, S.Hames, & M. Takahashi. (2027). _F%$# Twitter: A corpus-based analysis of vulgar language on Twitter_. *Corpora* 27(1). 

---

## Contact

For questions or collaboration requests, please contact:

**Martin Schweinberger**  
[m.schweinbergerATuq.edu.au / ORCID: 0000-0003-1923-9153 / University of Queensland]

