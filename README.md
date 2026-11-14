# What Do They Really Think?

An interactive guessing game about political perception gaps. Students guess what Democrats and Republicans believe and who belongs to each party, then compare their guesses with real survey data and with what each party guessed about the other. By Gwen Sharp.

**Live site:** https://gsharpokie.github.io/politicalbeliefs/

## What it does

- **Round 1: Beliefs (10 questions).** Students guess what share of Republicans or Democrats agreed or disagreed with a statement. After each guess, a chart shows the actual answer, the other party’s average guess, and the student’s guess.
- **Round 2: Who’s in the party? (8 questions).** Students guess what share of each party belongs to groups people associate with it (for example, Republicans earning over $250,000 a year). The chart also shows how each party guessed about itself.
- **Results.** Students see their average miss next to the other party’s average miss, a summary chart of every question, a short “Why it matters” section, and discussion questions.
- Students guess about both parties, so no one has to say which party they belong to. The page deliberately avoids red and blue.

## For instructors

- To show every answer without playing (for example, on a projector), add `#answers` to the end of the link: https://gsharpokie.github.io/politicalbeliefs/#answers
- The page stores nothing and sends nothing anywhere. Nothing a student enters leaves their browser.

## Data

- **Round 1:** Yudkin, Daniel, Stephen Hawkins, and Tim Dixon. 2019. *The Perception Gap: How False Impressions Are Pulling Americans Apart.* More in Common. Tables 1 and 2. Online survey with YouGov, November 7–10, 2018; 2,100 U.S. adults (936 Democrats, 755 Republicans, 409 independents). https://perceptiongap.us/
- **Round 2:** Ahler, Douglas J. and Gaurav Sood. 2018. “The Parties in Our Heads: Misperceptions about Party Composition and Their Consequences.” *Journal of Politics* 80(3): 964–981. Table 1. Guesses from a YouGov survey of 1,000 Americans, March 2015; actual shares mostly from the 2012 American National Election Study. https://doi.org/10.1086/697253

Both parties have changed since these surveys; the page says so.

## Editing the questions

All of the questions and numbers are in one list near the top of the `<script>` section of `index.html`, starting with `const Q = [`. To change one, open `index.html` on GitHub, select the pencil icon, edit the line, and select **Commit changes**. The live site updates within a few minutes.

Each Round 1 question looks like this:

```js
{ r:1, p:"R", verb:"agreed with", s:"Racism still exists in America.", short:"Racism still exists", actual:79, other:51 },
```

- `r` is the round (1 or 2). `p` is the party the question is about: `"R"` or `"D"`.
- `verb` is `"agreed with"` or `"disagreed with"`. `s` is the survey statement. `short` is the label in the results chart.
- `actual` is the party’s own answer. `other` is the other party’s average guess.
- Round 2 questions use `q` (the full question) in place of `verb` and `s`, and add `own` (the party’s guess about itself).
- Use curly quotes and apostrophes in the text. Keep the comma at the end of each line except the last.

## Turning on the site (one time)

Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, and select **Save**. The site goes live a minute or two later.

The page’s “Suggest a correction” link opens a new issue in this repository, so keep Issues turned on (Settings → General → Features).

## Author

Created by Gwen Sharp ([@gsharpokie](https://x.com/gsharpokie)).

## License

© 2026 Gwen Sharp. Licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/): you may share and adapt it for noncommercial purposes with credit. See [LICENSE](LICENSE). The survey figures belong to the studies cited above; this license covers the page’s design, text, and code.
