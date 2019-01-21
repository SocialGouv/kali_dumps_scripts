# KALI Dumps scripts

This collection of scripts helps using KALI dumps (the French Conventions collectives nationales database).

Currently they let you:
- flatten and merge the XML files (deprecated)
- convert all the articles' XML files to individual JSON files
- parse the articles' XML files and import them to a MongoDB database

These scripts were created for the [Code Du Travail Numérique](https://incubateur.social.gouv.fr/startups/code-du-travail-numerique/) project.

You can see an example of a Convention Collective on Legifrance [here](https://www.legifrance.gouv.fr/affichIDCC.do;jsessionid=345B979AD534CB99791356E28B8A9CB0.tplgfr35s_1?idSectionTA=KALISCTA000005733781&cidTexte=KALITEXT000005639851&idConvention=KALICONT000005635890)

## Schema docs

You can find some work-in-progress docs on a [Google Spreadsheet here](https://github.com/SocialGouv/kali_dumps_scripts.git).

![docs screenshot](https://i.imgur.com/8XgOmhL.png)

The infos in this documentation come from:
- the DTD files available on Data Gouv
- exploring the MongoDB database that these scripts help create. The M3T tool is very helpful for this.

## Download source data dumps

You can find the original source KALI dumps on Data Gouv :
[https://www.data.gouv.fr/fr/datasets/kali-conventions-collectives-nationales/](https://www.data.gouv.fr/fr/datasets/kali-conventions-collectives-nationales/)

You should then extract the archive.

## Local setup

You need to install some light dependencies for the script :

```sh
mkvirtualenv cdtn-scripts
pip3 install -r requirements.txt
```

Then you can install the pip package in edit mode so that imports work properly

```sh
pip3 install -e .
```

## Usage

```sh
python3 kali_extractor/extract_kali_dumps.py --drop --mode mongodb /Users/jean/Downloads/kali_dump
```

you can use `python3 kali_extractor/extract_kali_dumps.py -h` to get more info on the accepted arguments
