# Module 11 data — support tickets

`support_tickets.csv` is a **synthetic** corpus of 3,000 customer-support tickets for an outdoor-gear retailer (the fictional Northwind Outfitters). No ticket describes a real customer. Released **CC0** (public domain).

| Column | Contents |
|---|---|
| `ticket_id` | `T-10001` and up |
| `channel` | `email`, `webform` or `chat` |
| `subject` | the ticket's subject line (sometimes generic, sometimes empty) |
| `body` | the ticket text |
| `queue` | the label: the queue the ticket belongs in |

## The queues

| Queue | Share of tickets |
|---|---:|
| shipping | 29.0% |
| returns-warranty | 21.5% |
| billing | 21.3% |
| product-question | 17.2% |
| account-access | 11.0% |

## What makes it hard on purpose

- Neighbouring queues share vocabulary (a *refund* lives in billing and in returns; a *package* in shipping and in returns).
- About **16%** of tickets carry a second intent; the label follows the first, dominant clause.
- About **15%** have one to three typos.
- About **2%** are junk ("see attached", a bare order number) that say almost nothing.
- About **4%** are re-submissions of an earlier ticket, so **deduplicate before you split**.

Generated once, with a fixed random seed, from the course's ticket generator; the file never changes during the term.
