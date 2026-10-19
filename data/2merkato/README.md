# 2merkato business emails

Email addresses published by businesses in the 2merkato business directory
(<https://www.2merkato.com>), with the business name each address belongs to.

| | |
|---|---|
| Rows | 858 |
| Unique email addresses | 848 |
| Distinct businesses | 631 |
| Businesses publishing two addresses | 151 |
| Collected | 2026-10-19 |

## Files

- `2merkato_business_emails.csv` — the dataset
- `2merkato_business_emails.jsonl` — same rows, one JSON object per line

## Columns

| column | meaning |
|---|---|
| `email` | the address, as published |
| `business_name` | the business the address belongs to |
| `detail_url` | the listing the address was taken from |
| `category` | business category, where one was published |
| `sources` | `rss` (category feed), `page` (listing page), or `page+rss` (seen in both) |

## Method

The directory publishes contact details in a "Contact Us" block at the end of
a listing description, and only for listings whose owner entered them. The
addresses were collected from two sources:

- **Category RSS feeds.** Each category exposes a feed at
  `index.php?option=com_mtree&task=rss&type=new&cat_id=<id>` that embeds the
  full listing description, including the contact block. All 1,062 category
  nodes in the tree were walked and 773 feeds were fetched, covering 14,225
  distinct listings.
- **Listing pages.** The first page of every category holds the promoted
  listings, which publish contact details far more often (45–60% versus
  2–4%). 1,113 listing pages were fetched directly.

Every address was re-verified against the page it came from.

## Caveats

- Roughly 4% of listings publish an email. Listings without one publish a
  phone number and address instead; re-checking never changes this, so it
  reflects the source, not the collection.
- The email yield varies sharply by category. Ethiopian Manufacturers and
  Agriculture are around 83%; Micro and Small Enterprises and Foreign
  Suppliers are 0%.
- The ~10,000 older listings that appear in no category feed and on no
  category's first page were not covered.
- One address is `nafletcocschool@gmal.com` — a typo in the source listing.
