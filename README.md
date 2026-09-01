# AustriaVPI
Consumer Price Indices of Austria

## Update: Official Source
In the meantime, the data is also available via data.gv.at.
The repository will remain for now because my own developments are already based on it. If data is needed for a new development, the official data should be used if possible:

- [Consumer Price Index Base 1966](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-1966)
- [Consumer Price Index Base 1976](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-1976)
- [Consumer Price Index Base 1986](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-1986)
- [Consumer Price Index Base 1996](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-1996)
- [Consumer Price Index Base 2000](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-2000)
- [Consumer Price Index Base 2005](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-2005)
- [Consumer Price Index Base 2010](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-201001140)
- [Consumer Price Index Base 2015](https://www.data.gv.at/katalog/dataset/stat_verbraucherpreisindex-basis-2015)

## Motivation
Sometimes software requires (current) consumer price index values, but unfortunately I did not find a complete, current, and maintained list online. Although the values from Statistics Austria are available in various formats (Excel, PDF, HTML), they are unfortunately not in an easily interpretable format (for software), since all existing formats contain _disruptive_ formatting.

## Solution
A local service on one of my computers automatically fetches the current CPI values online from Statistics Austria, collects them and then makes them available in this repository. The values are saved as CSV. All other potentially required formats (e.g. XML, JSON, ...) must be derived locally from the CSV files and are not provided here.

### Data
* ~~`data/codes.csv` contains a list of the available indices and their full names.~~
* ~~`data/termine.csv` contains the next publication dates of the CPI values by Statistics Austria.~~
* `data/werte.csv` contains all available values for the indices. The respective latest (current) values of the indices are to be considered as preliminary values and may change under certain circumstances.

The values can be retrieved either by cloning the repo or directly (via GitHub).
https://raw.githubusercontent.com/wischi-chr/AustriaVPI/master/data/werte.csv

It is recommended to cache the data locally, since the index values (usually) only change on the mentioned dates and GitHub is not a file hoster (in the true sense). For technical reasons, however, it may happen that the index values appear here in the repository a few days after publication.

### Source
The values are obtained directly from the Statistics Austria website. Specifically, these are the HTML versions of the indices, which are downloaded and parsed locally. Afterwards, these are compiled into a CSV:
[http://www.statistik.at/.../zeitreihen_und_verkettungen/](http://www.statistik.at/web_de/statistiken/wirtschaft/preise/verbraucherpreisindex_vpi_hvpi/zeitreihen_und_verkettungen/index.html)

Although older indices are linked via so-called [chaining factors](http://www.statistik.at/web_de/statistiken/wirtschaft/preise/verbraucherpreisindex_vpi_hvpi/zeitreihen_und_verkettungen/022116.html), these are obtained from Statistics Austria and not calculated by myself to prevent potential rounding errors.

## Disclaimer
Although the compilation is done with great care, correctness, timeliness, and completeness cannot be guaranteed. You are welcome to use the data compiled here, but you do so at your own risk. If you discover an error, I would be very happy if you open a ticket and briefly describe the found error so that it can be fixed. - Thank you for your help.
