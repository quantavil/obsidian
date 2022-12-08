## Google search operators cheat sheet

You can find all of the major organic search operators below, broken up into three categories: “Basic”, “Advanced”, and “Unreliable”. Basic search operators are operators that modify standard text searches.

### Basic search operators 
---
| Operator | Example| Description|
|-----------|---------|-------|
| " " | **["nikola tesla"](https://www.google.com/search?q=%22nikola+tesla%22&*)**  |Put any phrase in quotes to force Google to use exact-match. On single words, prevents synonyms. |
| OR | **[tesla OR edison](https://www.google.com/search?q=tesla+OR+edison)**  |Google search defaults to logical AND between terms. Specify "OR" for a logical OR (ALL-CAPS). |
| \| | **[tesla \| edison](https://www.google.com/search?q=tesla+%7C+edison)**  |The pipe (\|) operator is identical to "OR". Useful if your Caps-lock is broken :) |
| ( ) | **[(tesla OR edison) alternating current](https://www.google.com/search?q=(tesla+OR+edison)+alternating+current)**  |Use parentheses to group operators and control the order in which they execute. |
| - | **[tesla -motors](https://www.google.com/search?q=tesla+-motors)** |Put minus (-) in front of any term (including operators) to exclude that term from the results. |
| * | **[tesla "rock \* roll"](https://www.google.com/search?q=tesla+%22rock+*+roll%22)** | An asterisk (\*) acts as a wild-card and will match on any word. |
| #..# | **[tesla announcement 2015..2017](https://www.google.com/search?q=tesla+announcement+2015..2017)** | Use (..) with numbers on either side to match on any integer in that range of numbers. |
| $ | **[tesla deposit $1000](https://www.google.com/search?q=tesla+deposit+%241000)** | Search prices with the dollar sign ($). You can combine ($) and (.) for exact prices, like $19.99. |
| € | **[€9,99 lunch deals](https://www.google.com/search?q=%E2%82%AC9%2C99+lunch+deals)** | Search prices with the Euro sign (€). Most other currency signs don't seem to be honored by Google.  |
| in | **[250 kph in mph](https://www.google.com/search?q=250+kph+in+mph)** | Use "in" to convert between two equivalent units. This returns a special, Knowledge Card style result. |

Advanced search operators are special commands that modify searches and may require additional parameters (such as a domain name). Advanced operators are typically used to narrow searches and drill deeper into results.

### Advanced search operators

| Operator | Example| Description|
|-----------|---------|-------|
| intitle: | **[intitle:"tesla vs edison"](https://www.google.com/search?q=intitle:%22tesla+vs+edison%22)** | Search only in the page's title for a word or phrase. Use exact-match (quotes) for phrases. |
| allintitle: | **[allintitle: tesla vs edison](https://www.google.com/search?q=allintitle:+tesla+vs+edison)** | Search the page title for every individual term following "allintitle:". Same as multiple intitle:'s. |
| inurl: | **[tesla announcements inurl:2016](https://www.google.com/search?q=tesla+announcements+inurl:2016)** | Look for a word or phrase (in quotes) in the document URL. Can combine with other terms. |
| allinurl: | **[allinurl: amazon field-keywords nikon](https://www.google.com/search?q=allinurl:+amazon+field-keywords+nikon)** | Search the URL for every individual term following "allinurl:". Same as multiple inurl:'s. |
| intext: | **[intext:"orbi vs eero vs google wifi"](https://www.google.com/search?q=intext:%22orbi+vs+eero+vs+google+wifi%22)** | Search for a word or phrase (in quotes), but only in the body/document text. |
| allintext: | **[allintext: orbi eero google wifi](https://www.google.com/search?q=allintext:+orbi+eero+google+wifi)** | Search the body text for every individual term following "allintext:". Same as multiple intexts:'s. |
| filetype: | **["tesla announcements" filetype:pdf](https://www.google.com/search?q=%22tesla+announcements%22+filetype:pdf)** | Match only a specific file type. Some examples include PDF, DOC, XLS, PPT, and TXT. |
| related: | **[related:nytimes.com](https://www.google.com/search?q=related:nytimes.com)** | Return sites that are related to a target domain. Only works for larger domains. |
| AROUND(X) | **[tesla AROUND(3) edison](https://www.google.com/search?q=tesla+AROUND(3)+edison)** | Returns results where the two terms/phrases are within (X) words of each other. |

Unreliable operators have either been found to produce inconsistent results or have been deprecated altogether. The "link:" operator was officially deprecated in early 2017. It appears that "inanchor:" operators are still in use, but return very narrow and sometimes unreliable results. Use link-based operators only for initial research.

### Unreliable/deprecated operators
| Operator | Example| Description|
|-----------|---------|-------|
| ~ | **[~cars](https://www.google.com/search?q=~cars)**  |Include synonyms. Seems to be unreliable, and synonym inclusion is default now. |
| + | **[+cars](https://www.google.com/search?q=%2Bcars)** | Force exact-match on a single phrase. Deprecated with the launch of Google+. |
| daterange: | **[tesla announcements daterange:2457663-2457754](https://www.google.com/search?q=tesla+announcements+daterange:2457663-2457754)** | Return results in the specified range. Can be inconsistent. Requires [Julian dates](http://aa.usno.navy.mil/data/docs/JulianDate.php). |
| link: | **[link:nytimes.com](https://www.google.com/search?q=link:nytimes.com)** | Find pages that link to the target domain. This operator was deprecated in early 2017. |
| inanchor: | **[inanchor:"tesla announcements"](https://www.google.com/search?q=inanchor:)** | Find pages linked to with the specified anchor text/phrase. Data is heavily sampled. |
| allinanchor: | **[allinanchor: tesla announcements](https://www.google.com/search?q=allinanchor:+tesla+announcements)** | Find pages with all individual terms after "inanchor:" in the inbound anchor text. |

Note that, for all of the "allin...:" operators, Google will try to apply the operator to every term following it. Combining "allin...:" operators with any other operators will almost never produce the desired results.

___

## Search operator tips & tricks

Having all of the pieces is only the first step in building a puzzle. The real power of search operators comes from combining them.

### 1\. Chain together operator combos

You can chain together almost any combination of text searches, basic operators, and advanced operators:

```
"nikola tesla" intitle:"top 5..10 facts" -site:youtube.com inurl:2015
```

This search returns any pages that mention "Nikola Tesla" (exact-match), have the phrase "Top (X) facts" in the title, where X ranges from 5 to 10, are not on YouTube.com, and have "2015" somewhere in the URL.

### 2. Hunt down plagiarized content

Trying to find out if your content is unique or if someone is plagiarizing you? Use a unique phrase from your text, put it in quotes (exact-match) after an "intext:" operator, and exclude your own site with "-site:"...

```
intext:"they were frolicking in our entrails" -site:moz.com
```

Similarly, you can use "intitle:" with a long, exact-match phrase to find duplicate copies of your content.

### 3\. Audit your HTTP->HTTPS transition

Switching a site from HTTP to HTTPS can be challenging. Double-check your progress by seeing how many of each type of page Google has indexed. Use the "site:" operator on your root domain and then exclude HTTPS pages with "-inurl:"...

```
site:moz.com -inurl:https
```

This will help you track down any stragglers or find pages that might not have been re-crawled by Google.

These are just a few examples of a nearly infinite set of combinations. Looking for more examples? You're in luck! We've created [a mega-list of 67 examples](https://moz.com/blog/mastering-google-search-operators-in-67-steps) to catapult you toward site operator mastery.
