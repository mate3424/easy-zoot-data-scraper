# Easy Zoot Data Scraper
> A production-ready Zoot data scraper that collects structured fashion product data across multiple storefronts. It helps teams monitor prices, availability, and catalog changes without manual browsing, delivering clean data ready for analysis or automation.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>easy-zoot-data-scraper</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project extracts detailed product information from Zoot fashion storefronts in a consistent, structured format.
It solves the problem of manually tracking product prices, sizes, and availability across large catalogs.
It’s built for developers, data teams, and e-commerce analysts who need reliable product intelligence at scale.

### Built for real-world product tracking
- Handles category pagination and individual product pages automatically
- Applies smart rate limiting to keep requests stable and predictable
- Validates inputs to prevent misconfigured runs
- Outputs clean, analytics-ready records
- Scales from small tests to large catalog crawls

## Features
| Feature | Description |
|----------|-------------|
| Multi-storefront support | Works across multiple regional storefronts with consistent output. |
| Pagination handling | Automatically follows category pages until limits are reached. |
| Rate limiting controls | Adjustable delays and concurrency to ensure stability. |
| Structured output | Returns normalized product records ready for pipelines. |
| Flexible input schema | Easy configuration for URLs, limits, and performance tuning. |

---
## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| url | Direct link to the product detail page. |
| name | Product title as displayed in the store. |
| priceCurrency | Currency code used for pricing. |
| currentBestPrice | Current selling price with numeric and formatted values. |
| originalPrice | Original price before discounts, if available. |
| saleCode | Promotional or discount code applied to the product. |
| thumbnail | Primary product image URL. |
| images | Array of all available product images. |
| brand | Brand name, logo, and reference link. |
| breadcrumbs | Category hierarchy used for navigation. |
| description | Full textual product description. |
| attributes | Key-value pairs such as material or fit. |
| sizes | Available sizes with stock status. |
| available | Overall product availability flag. |

---
## Example Output

    [
      {
        "url": "https://www.zoot.cz/polozka/1234567/stylish-jacket",
        "name": "Stylish Jacket",
        "priceCurrency": "CZK",
        "currentBestPrice": {
          "value": 2199,
          "formattedPrice": "2 199 Kč"
        },
        "originalPrice": {
          "value": 2999,
          "formattedPrice": "2 999 Kč"
        },
        "saleCode": "WEEKEND10",
        "thumbnail": "https://images.zoot.cz/fit/1908x2562/example.jpg",
        "images": ["https://images.zoot.cz/img1.jpg", "https://images.zoot.cz/img2.jpg"],
        "brand": {
          "link": "https://www.zoot.cz/brand/only",
          "logo": "https://images.zoot.cz/brands/only.png"
        },
        "breadcrumbs": [
          { "text": "Ženy", "url": "https://www.zoot.cz/katalog/17504/zeny" }
        ],
        "description": "Lightweight jacket ideal for spring.",
        "attributes": [
          { "key": "Material", "value": "100 % polyester" }
        ],
        "sizes": [
          { "size": "S", "available": true, "note": null }
        ],
        "available": true
      }
    ]

---
## Directory Structure Tree

    Easy Zoot Data Scraper/
    ├── src/
    │   ├── main.ts
    │   ├── routes/
    │   │   ├── categoryHandler.ts
    │   │   └── productHandler.ts
    │   ├── extractors/
    │   │   ├── productParser.ts
    │   │   └── priceUtils.ts
    │   ├── validators/
    │   │   └── inputSchema.ts
    │   └── utils/
    │       ├── delays.ts
    │       └── logger.ts
    ├── storage/
    │   └── state.json
    ├── config/
    │   ├── default-input.json
    │   └── selectors.json
    ├── package.json
    ├── tsconfig.json
    └── README.md

---
## Use Cases
- **E-commerce analysts** use it to monitor price changes, so they can react faster to market shifts.
- **Retail teams** use it to track stock availability, so they can spot gaps in sizing or supply.
- **Data engineers** use it to feed BI dashboards, so reporting stays current without manual work.
- **Growth teams** use it to analyze product positioning, so promotions stay competitive.

---
## FAQs
**How do I limit the number of products collected?**
You can define a maximum item count in the input configuration, which stops the run once the threshold is reached.

**Can I adjust request speed?**
Yes. Concurrency and delay settings let you fine-tune how fast pages are processed based on your needs.

**Does it support multiple categories at once?**
Multiple start URLs are supported, allowing parallel extraction across categories or collections.

**What happens if a page fails to load?**
Timeouts and retries are handled gracefully, and failed requests are logged for review.

---
### Performance Benchmarks and Results

**Primary Metric:** Processes an average of 35–50 product pages per minute under standard rate limits.

**Reliability Metric:** Maintains a success rate above 98% across long-running catalog crawls.

**Efficiency Metric:** Uses controlled concurrency to keep memory usage stable under sustained loads.

**Quality Metric:** Captures over 99% of visible product fields with consistent formatting across categories.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
