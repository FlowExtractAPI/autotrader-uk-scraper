**[AutoTrader UK Scraper](https://apify.com/dz_omar/autotrader-uk-scraper?fpr=smcx63)** extracts **AutoTrader UK listings** from any search link you copy from autotrader.co.uk: **cars, vans, motorbikes, motorhomes, caravans, trucks, farm machinery, plant and electric bikes**. Paste the link, choose how many listings you want, and get clean data with **price, mileage, specs, registration, seller phone and address, vehicle checks and high-resolution photos**.

Perfect for **car dealers**, **vehicle traders and auction buyers**, **market analysts** and **lead-generation teams** who need up-to-date UK vehicle stock without copying listings by hand.

## What does AutoTrader UK Scraper do?

- **Any AutoTrader search link** — set your filters on the website (make, model, price, year, mileage, fuel, gearbox, berths, distance…) and paste the address. The same filters apply to the data.
- **Every vehicle type** — cars, vans, bikes, motorhomes, caravans, trucks, farm, plant and electric-bike searches, plus single listing links.
- **Large searches collected in full** — when AutoTrader shows thousands of matches, the scraper still reaches them, not just the first pages.
- **Full listing details** — registration, seller phone and website, description, equipment, history check, price rating against the market, running costs and every photo.
- **Working high-resolution photos** — 1280×960 image links that open directly.
- **Duplicates removed** — a listing found by several of your links is delivered and charged once.

### What data can you extract from AutoTrader UK?

| Category | Fields |
|---|---|
| Listing | listing ID, URL, title, headline, description, condition, photos (count, main photo, all photos) |
| Vehicle | make, model, variant, trim, generation, year, first registration, plate, registration number, mileage, body type, fuel, gearbox, engine size and power, drivetrain, doors, seats, colour |
| Price | price, price as shown, price excluding fees, price on application, price rating, market value, mileage vs average |
| History & running costs | owners, service history, write-off category, vehicle check (stolen, scrapped, write-off, imported, exported), CO2, fuel economy, road tax, insurance group, expert rating |
| Type-specific | berths, bed and end layout, dimensions, gross weight, style (e.g. telehandlers, attachments, mountain bikes) |
| Seller | name, trade or private, dealer ID, rating and review count, phone, website, address, town, county, postcode, region, latitude/longitude, distance, FCA number, logo, dealer page |

### Why use AutoTrader UK Scraper on Apify?

Running it on Apify gives you **API access**, **scheduling**, **monitoring**, **integrations** (Make, Zapier, n8n, Google Sheets, webhooks) and **proxy rotation** without managing any infrastructure. A 100-listing run with full details costs about **$0.08**.

## How to scrape AutoTrader UK

1. Open [AutoTrader UK Scraper](https://apify.com/dz_omar/autotrader-uk-scraper?fpr=smcx63) in Apify Console.
2. On autotrader.co.uk, run your search with the filters you want and copy the page address.
3. Paste one or more links into **AutoTrader UK search or listing URLs**.
4. Set **Maximum listings per URL** (start small: `20`).
5. Click **Start**, then download the results as JSON, CSV or Excel, or fetch them over the API.

## How much does it cost to scrape AutoTrader UK?

Pay only for what you get. Prices per event by Apify plan:

| Event | FREE | BRONZE | SILVER | GOLD+ |
|---|---|---|---|---|
| Listing (search-results data) | $0.0005 | $0.00049 | $0.00048 | $0.00047 |
| Listing details add-on | $0.00025 | $0.00024 | $0.00024 | $0.00023 |
| Search link (once per link) | $0.001 | $0.0009 | $0.0008 | $0.0007 |
| Run start (per GB of memory) | $0.003 | $0.0025 | $0.002 | $0.002 |

- **1,000 listings with full details** cost about **$0.75** on the free plan and **$0.70** on GOLD (+ the start and search-link fees).
- **1,000 listings without details** cost about **$0.50** (GOLD: $0.47).
- The details add-on is never charged when details are turned off, unavailable for that vehicle type, or could not be read.

## Input and output examples

### Input

```json
{
    "startUrls": [
        "https://www.autotrader.co.uk/car-search?postcode=SW1A1AA&make=Volkswagen&model=Golf",
        "https://www.autotrader.co.uk/motorhome-search?berth=2&make=Benimar&postcode=SW1A1AA&transmission=Automatic",
        "https://www.autotrader.co.uk/car-details/202610217203885"
    ],
    "maxResults": 100,
    "includeDetails": true
}
```

| Input value | What it extracts |
|---|---|
| Search link (`…/car-search?…`, `…/van-search?…`, `…/motorhome-search?…`, …) | Up to **Maximum listings per URL** listings matching the link's filters |
| Listing link (`…/car-details/<number>`) | That one listing with full details |
| Link without a postcode | A UK-wide search |

The run collects up to **Maximum listings per URL × number of URLs**: 10 links with 100 gives up to 1,000 listings.

### Output

### Listing record

A real record from a test run (seller phone and registration partly masked here; the dataset has them in full).

```json
[
    {
        "advert_id": "202610217203885",
        "url": "https://www.autotrader.co.uk/car-details/202610217203885",
        "category": "Car",
        "title": "Ford C-Max 1.6 16v Zetec 5dr",
        "make": "Ford",
        "model": "C-Max",
        "trim": "Zetec",
        "year": 2010,
        "registration": "FP10•••",
        "mileage": 133000,
        "price": 449,
        "price_formatted": "£449",
        "fuel_type": "Petrol",
        "transmission": "Manual",
        "engine_size_litres": 1.6,
        "engine_power_bhp": 99,
        "co2_g_km": 164,
        "annual_tax_gbp": 275,
        "insurance_group": "13E",
        "price_rating": null,
        "image_count": 13,
        "main_image": "https://m.atcdn.co.uk/a/media/w1280h960/c4c977fa2f834eb3b1e080d8698f69f3.jpg",
        "seller": {
            "name": "MCV",
            "type": "Trade",
            "phone": "(07811) ••••••",
            "town": "Manchester",
            "postcode": null,
            "rating": null,
            "review_count": null
        },
        "detail_status": "ok"
    }
]
```

## Other Actors you might need

| Actor | What it adds |
|---|---|
| **[Salvagebid Scraper](https://apify.com/dz_omar/salvagebid-scraper?fpr=smcx63)** | Salvage and damaged-vehicle auction listings — useful alongside AutoTrader prices for trade buyers and repairers. |

## Frequently asked questions

### Is it legal to scrape AutoTrader UK?

The scraper collects publicly available listing data. You are responsible for using it in line with AutoTrader's terms and with UK GDPR, especially for seller contact details. This is not legal advice.

### Do I need an AutoTrader account?

No. Paste public search or listing links — no login, cookies or API key.

### Which AutoTrader links are accepted?

Search links for cars, vans, bikes, motorhomes, caravans, trucks, farm, plant and electric bikes, and single listing links for every type except electric bikes. Links copied without `https://` work too. Other websites and other AutoTrader pages are rejected before the run starts, so nothing is charged.

### Why are some fields empty?

Sellers fill in different details, and some fields only come with full details (registration, phone, description, equipment, vehicle check). Electric-bike results carry search-results data only (`detail_status: "not_available"`).

### Why did my run return fewer listings than I asked for?

The search had fewer matches, a listing was already delivered by another of your links, or your max cost per run was reached. The run's status line and log say which. If more than 1,000 listings share one exact price, the extra ones can't be reached — narrow the search to get them.

### In what order do the listings come back?

In the link's sort order, as long as you ask for up to 1,000 listings per link. Above 1,000, a large search is collected in price bands from cheapest to most expensive, so that every listing can be reached.

### What happens if a link has a filter the scraper can't apply?

The run log names it and the rest of the search runs as normal, so you never get a silently wider search.

### Can I use AutoTrader UK Scraper in Make, Zapier, n8n or my own code?

Yes — through Apify's integrations, the Apify API and the client libraries for JavaScript and Python.

### What happens if a run is interrupted?

It saves progress and resumes where it left off, without delivering or charging the same listing twice.

## Support

- 🌐 **Website:** [flowextractapi.com](https://flowextractapi.com)
- 📧 **Email:** [flowextractapi@outlook.com](mailto:flowextractapi@outlook.com)
- 💬 **GitHub:** [FlowExtractAPI](https://github.com/FlowExtractAPI)
- 💼 **LinkedIn:** [flowextract-api](https://www.linkedin.com/in/flowextract-api/)
- 🐦 **X (Twitter):** [@FlowExtractAPI](https://x.com/FlowExtractAPI)
- 📱 **Facebook:** [flowextractapi](https://www.facebook.com/flowextractapi)
- 🎵 **TikTok:** [@flowextractapi](https://www.tiktok.com/@flowextractapi)

## Legal & compliance

- **Public data only** — processes publicly available data.
- **Rate limiting** — respects source-service limits and terms of use.
- **Data protection** — no storage of personal information or unauthorized data collection.
- **Commercial use** — suitable for business intelligence and research.
- No affiliation with or endorsement by AutoTrader is implied.

---

*AutoTrader UK Scraper — by FlowExtract API. Turn any website into structured data.*
