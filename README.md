# ssq

## ABSTRACT

`ssq` (Seznam Slovník query) is a command-line front-end to the on-line dictionaries
at [slovnik.seznam.cz](http://slovnik.seznam.cz) with pronunciation playback.

## NOTICE

The original `ssq` was rewritten to Python in 2/2019. My original shell hack
is available as `ssq-old`.

## FEATURES

* Really convenient for terminal-based workflows
* Pronunciation playback for many words
* Contains, phrases and related words
* English, German, French, Italian, Spanish, Russian and Slovak dictionary
* "Did you mean" and fulltext results

## USAGE

Looking up a word in the dictionary is as simple as

```
% ssq this
this: [ðɪs]
 - ten(to), tenhle o právě zmíněném
 - to(hle)
 - to(hle), toto, tento zde
 - this is tady ... při představování v telefonu ap.
 - takto, takhle malý ap.
 - this much tolik
```

Use `-h` to display full usage message:

```
Usage: ssq [options] term [lang=en]

Command-line front-end to slovnik.seznam.cz.

Options:
  -h, --help  show this help message and exit
  -a          Show full dictionary listing
  -p          Pronounce the word

Bug reports welcome at https://github.com/dcepelik/ssq/issues.
```

## REMARKS

This simple Python 3 script only depends on `beautifulsoup4` (for HTML
processing) and on `mpv` optionally (for pronunciation playback).

As I percieve it, `ssq` is a rather limited web browser, and as such, I believe
it does not violate any terms of use. But that's just my opinion and you're
encouraged to check.

I would like to thank Seznam.cz, a.s., for providing the dictionaries on-line
free of charge. The dictionary content, provided by Lingea s.r.o., is great.

## EXAMPLES

### MATCH FOUND, BRIEF

```
% ssq šrot
šrot:
 - scrap (iron)
   scrapyard, scrapheap
 - groats, grout, coarse meal
 - swot
   grind
```

### MATCH FOUND, FULL

```
ssq -a šrot

šrot:
 - scrap (iron)
   scrapyard, scrapheap
 - groats, grout, coarse meal
 - swot
   grind

POKROČILÁ GRAMATIKA
rod mužský neživotné
 - (kovový odpad) scrap (iron)
   (šrotiště) scrapyard, scrapheap
 - (drcené zrní) groats, grout, coarse meal
rod mužský životné
 - (BrE) swot
   (hl.) (AmE) grind

SLOVNÍ SPOJENÍ
 - kovošrot

FULLTEXT
 - železný: železný šrot → scrap iron
 - scrapheap: být zralý do šrotu, být na vyhození přístroj ap. → be fit for the scrapheap
```

### PARTIAL MATCH

```
% ssq šel
šel:

DID YOU MEAN
 - shell - skořápka, louskat
 - jít - go
 - shall

ssq: šel not found in en dictionary
```

## INSTALLATION

Use common sense.

My setup:

  - `git clone git@github.com:dcepelik/ssq.git ~/sw/ssq`
  - `ln -s ~/sw/ssq/ssq ~/bin/ssq`

(I have `~/bin` in my `$PATH`.)

## LICENSE

[MIT](https://en.wikipedia.org/wiki/MIT_License)
