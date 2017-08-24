# `ssq`: Seznam Slovník Query

(This page is of interest to Czech speakers only I'm afraid.)

## What's That?

`ssq` is a command-line front-end to [slovnik.seznam.cz](http://slovnik.seznam.cz)
(Czech/English, Czech/German, etc. dictionary). I have used
[sdcv](http://dushistov.github.io/sdcv/) for a while, but the free StarDict dictionaries are poor.
Seznam's dictionaries, provided by Lingea s.r.o., are much better and contain idioms
and example language usage, too.

As I percieve it, `ssq` is a rather limited web browser, and as such, I don't think
it violates any terms of use. But if you're in doubt, feel free to consult it.

## Features

* KISS
* Multilingual support
* Support for idioms, language use examples
* Support for failed queries ("did you mean") and non-exact matches

## Usage

    ssq SEARCH-TERM [LANG]

The valid values for `LANG` are `en`, `de`, `fr`, `it`, `es`, `ru`, `sk`. The default
is `en`.

### Exact Match

Hope this software isn't `$(ssq mizerný)`!

    user@machine ~ % ssq mizerný
    mizerný:
            ⚫very poor 
            ⚫lousy 
            ⚫wretched, rotten, rubbishy, trashy 
            ⚫miserable 
            ⚫(god)damned, bloody, darned 
            ⚫miserable, paltry 
            ⚫measly 
    
    ADVANCED GRAMMAR:
            ⚫(nekvalitní) very poor 
            ⚫(i částka ap.) (hovor.) lousy 
            ⚫(prachšpatný) wretched, rotten, rubbishy, trashy 
            ⚫(počasí, život) miserable 
            ⚫(zatracený) (hovor.) (god)damned, bloody, darned 
            ⚫(nepatrný) miserable, paltry 
            ⚫(hovor.) measly 
    
    RELATED WORDS:
            ⚫bezcharakterní, nevalný, špatný, ubohý, hanebný, ničemný, nedostatečný 
            ⚫špičkový, prvotřídní, zásadový, poctivý, kvalitní, čestný, vynikající 
    
    FULLTEXT:
            ⚫spirit: v mizerné náladě, být sklíčený, bez nálady -> in low spirits 

### Non-exact Match

    user@machine ~ % ssq šel
    šel (non-perfect match):
            ⚫shell - skořápka, louskat
            ⚫jít - go
            ⚫shall


### Failed Query

    user@machine ~ % ssq bba
    ssq: bba: not found
    ssq: hint: did you mean any of the following?
            ⚫dva, dvě - two 
            ⚫bio - organic 
            ⚫BA - bakalářský stupeň 
            ⚫BBC 
            ⚫MBA - magisterský titul 
            ⚫bra - podprsenka 
            ⚫oba, obě - both of them 
            ⚫boa - boa 
            ⚫bob - bean plant, bobsleigh 
            ⚫BBQ - opékání 
            ⚫ba - yeah 

## Installation

Well, just `chmod u+x` the script. The script has no dependencies besides `curl`
and GNU `coreutils`.

## License

[The MIT License.](https://en.wikipedia.org/wiki/MIT_License)
