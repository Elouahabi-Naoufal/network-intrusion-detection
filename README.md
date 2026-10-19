<a id="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<br />
<div align="center">
  <a href="https://github.com/Elouahabi-Naoufal/network-intrusion-detection">
    <h3 align="center">Network Intrusion Detection</h3>
  </a>

  <p align="center">
    Team PFA project (EMSI, fourth year): machine-learning notebooks for network intrusion detection on CIC-IDS2017.
    <br />
    <a href="https://github.com/Elouahabi-Naoufal/network-intrusion-detection"><strong>Explore the repository »</strong></a>
    <br />
    <br />
    <a href="https://github.com/Elouahabi-Naoufal/network-intrusion-detection/issues/new?labels=bug">Report Bug</a>
    &middot;
    <a href="https://github.com/Elouahabi-Naoufal/network-intrusion-detection/issues/new?labels=enhancement">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#where-the-work-lives">Where the work lives</a></li>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

This is the team repository for the fourth-year PFA at EMSI on network intrusion detection. The
target dataset is CIC-IDS2017; the work is organised as Jupyter notebooks covering data
exploration, preprocessing and machine-learning models.

The important detail for anyone opening this repository is that `main` only contains this README.
The notebooks are developed on per-contributor branches, so the real content is one `git switch`
away. Nothing in this README claims a benchmark result: the notebooks are working material, not a
final report.

### Where the work lives

| Branch | Contents |
| --- | --- |
| `main` | This README only. |
| `adnane` | `exportation_data.ipynb` |
| `alae` | `exploration_cicids2017_oulmidi.ipynb`, `pretraitement_cicids2017_alae.ipynb`, `XGboost_alae_final_checkpoint.ipynb` |
| `naoufal` | `test.txt` (scratch file at the time of writing) |
| `oulmidi` | `exploration_cicids2017_oulmidi.ipynb` |

The `alae` branch currently holds the most complete chain: exploration, preprocessing (infinite
values, missing values, scaling and encoding), then a binary XGBoost pipeline
(`0 = BENIGN`, `1 = ATTACK`) that expects pre-cleaned, pre-split data under an `ml_ready/`
directory.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

* [![Jupyter][Jupyter-badge]][Jupyter-url]
* [![Python][Python-badge]][Python-url]
* [![pandas][pandas-badge]][pandas-url]
* [![NumPy][NumPy-badge]][NumPy-url]
* [![scikit-learn][scikit-learn-badge]][scikit-learn-url]
* [![XGBoost][XGBoost-badge]][XGBoost-url]
* [![Matplotlib][Matplotlib-badge]][Matplotlib-url]
* [![seaborn][seaborn-badge]][seaborn-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

Because the notebooks live on branches, clone the repository and switch to the branch you need.

### Prerequisites

* Python 3.10+ with Jupyter, or a Google Colab account.
* The CIC-IDS2017 CSV files, obtained separately. The dataset is not stored in this repository.

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/Elouahabi-Naoufal/network-intrusion-detection.git
   cd network-intrusion-detection
   ```
2. Switch to the branch that holds the notebook you want
   ```sh
   git switch alae
   # or: git switch adnane / oulmidi / naoufal
   ```
3. Install the common dependencies
   ```sh
   python -m venv .venv
   source .venv/bin/activate
   pip install jupyter pandas numpy scikit-learn xgboost matplotlib seaborn
   ```

Some notebooks were written for Google Colab and mount Google Drive or import `google.colab`.
Either run those in Colab or adapt the data-loading cells to a local path.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

1. Start Jupyter from the repository root
   ```sh
   jupyter notebook
   ```
2. Open the notebook for the stage you need:
   * `exploration_cicids2017_oulmidi.ipynb` — dataset structure, class distribution and data quality.
   * `pretraitement_cicids2017_alae.ipynb` — cleaning, handling infinite/NaN values, encoding and scaling.
   * `XGboost_alae_final_checkpoint.ipynb` — binary XGBoost training and evaluation.
3. Point the loading cells at your local CIC-IDS2017 files (or your mounted Drive folder) before
   running them.

There is no single entry point or CLI. Each notebook is run top to bottom and keeps its output in
the notebook.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Roadmap

- [x] Explore CIC-IDS2017 and document data-quality issues
- [x] Preprocess the dataset (infinite values, missing values, encoding, scaling)
- [x] Train a binary XGBoost baseline
- [ ] Consolidate the notebooks onto `main` so the repository is usable without switching branches
- [ ] Add multiclass experiments and a comparison between models
- [ ] Record the final metrics and the exact train/test protocol in a report
- [ ] Add a reproducible data-preparation script instead of Colab-specific Drive mounts

See the [open issues](https://github.com/Elouahabi-Naoufal/network-intrusion-detection/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

Because this is a team project, coordinate branch ownership before pushing to an existing
contributor branch.

### Top contributors:

<a href="https://github.com/Elouahabi-Naoufal/network-intrusion-detection/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Elouahabi-Naoufal/network-intrusion-detection" alt="contrib.rocks image" />
</a>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

This project is not licensed — all rights reserved.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Naoufal Elouahabi - [LinkedIn](https://www.linkedin.com/in/elouahabi-naoufal/) - elouahabi-naoufal1@gmail.com

Project Link: [https://github.com/Elouahabi-Naoufal/network-intrusion-detection](https://github.com/Elouahabi-Naoufal/network-intrusion-detection)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

* [CIC-IDS2017 dataset](https://www.unb.ca/cic/datasets/ids-2017.html) — Canadian Institute for Cybersecurity, University of New Brunswick.
* [XGBoost Documentation](https://xgboost.readthedocs.io/)
* [scikit-learn Documentation](https://scikit-learn.org/stable/)
* [Jupyter Documentation](https://docs.jupyter.org/)
* [Img Shields](https://shields.io)
* [Choose an Open Source License](https://choosealicense.com)
* [Best-README-Template](https://github.com/othneildrew/Best-README-Template)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[contributors-shield]: https://img.shields.io/github/contributors/Elouahabi-Naoufal/network-intrusion-detection.svg?style=for-the-badge
[contributors-url]: https://github.com/Elouahabi-Naoufal/network-intrusion-detection/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Elouahabi-Naoufal/network-intrusion-detection.svg?style=for-the-badge
[forks-url]: https://github.com/Elouahabi-Naoufal/network-intrusion-detection/network/members
[stars-shield]: https://img.shields.io/github/stars/Elouahabi-Naoufal/network-intrusion-detection.svg?style=for-the-badge
[stars-url]: https://github.com/Elouahabi-Naoufal/network-intrusion-detection/stargazers
[issues-shield]: https://img.shields.io/github/issues/Elouahabi-Naoufal/network-intrusion-detection.svg?style=for-the-badge
[issues-url]: https://github.com/Elouahabi-Naoufal/network-intrusion-detection/issues
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/elouahabi-naoufal/
[Jupyter-badge]: https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white
[Jupyter-url]: https://jupyter.org/
[Python-badge]: https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white
[Python-url]: https://www.python.org/
[pandas-badge]: https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white
[pandas-url]: https://pandas.pydata.org/
[NumPy-badge]: https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white
[NumPy-url]: https://numpy.org/
[scikit-learn-badge]: https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white
[scikit-learn-url]: https://scikit-learn.org/
[XGBoost-badge]: https://img.shields.io/badge/XGBoost-189FDD?style=for-the-badge&logo=xgboost&logoColor=white
[XGBoost-url]: https://xgboost.readthedocs.io/
[Matplotlib-badge]: https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white
[Matplotlib-url]: https://matplotlib.org/
[seaborn-badge]: https://img.shields.io/badge/seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white
[seaborn-url]: https://seaborn.pydata.org/
