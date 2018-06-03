# Cause + Concern Triage

## Export issues to triage:

```ruby
export GITHUB_TOKEN='secret'
bin/export mysociety/alaveteli > ./out.csv
```

## Sync triaged issue labels back to GitHub

* **Warning:** This "updates" the issue even if the labels already exist, so be aware if you rely on the "Recently updated" or "Least recently updated" sort order.
* The issue to sync back to is parsed from the `url` column of the input CSV.

```ruby
export GITHUB_TOKEN='secret'
cat ./out.csv | bin/sync
```

## Analyse causes in each concern

* This fetches issues from GitHub, not a CSV export, so its easy to get regular updates. For example, you could run from cron once a quarter.

```ruby
export GITHUB_TOKEN='secret'
bin/analyse mysociety/alaveteli > ./analysis.csv
```
