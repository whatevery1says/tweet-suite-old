# WE1S Tweet Suite

The WE1S Tweet Suite is a suite of tools for collecting and preprocessing data from Twitter, and for integrating that data into the WE1S Jupyter notebook workspace.Chomp is a client-side, human-assisted, generic-ish web scraper designed to collect broad data samples from specific websites based on specific Google queries. It should (eventually) be extensible, user-friendly, and capable of producing good, clean results at the scale of thousands or tens of thousands of queries.

## Scraper

The Scraper tools is a wrapper for the Python library [`twint`](https://github.com/twintproject/twint). Although Twint can be run on its own, the WE1S Scraper tool provides a handy notebook interface so that the user does not have to remember the Twint API.

*Notes on Twint:*

- Typical libraries that access the Twitter API require a Twitter developer account, which has become more complicated to obtain recently. The Twitter API also comes with limitations such as rate limits. Twint bypasses the Twitter API using [OSINT](https://en.wikipedia.org/wiki/Open-source_intelligence) tools to overcome these limitations.
- Twint is under active development, and frequent changes make installation strategies somewhat unreliable. We have found that the following commands work best:

```
pip install --user --upgrade -e git+https://github.com/twintproject/twint.git@origin/master#egg=twint

pip install nest_asyncio
```

## Preprocessor

The Preprocessor is a notebook that loads the Twint output and performs a variant of the WE1S preprocessing pipeline on the text of the tweets. The result is saved in a new `tidy_tweet` field. The preprocessing algorithm is described at the beginning of the notebook. The Preprocessor comes with a stoplist, which is a variant of the standard WE1S stoplist.

## Utilities

Once the data has been preprocessed, there are a myriad of methods for filtering the data to perform different analyses. Each method will require an ad hoc solution, but the `utilities` folder contains examples of methods we have already used to save on development time. These utilities will also typically produce outputs that can be read by the various modules in the WE1S Jupyter notebook workspace.
