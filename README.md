# VAG Number Decoder

A single page desk reference for decoding Volkswagen, Audi, Skoda, SEAT and CUPRA part numbers and VINs. Built to be opened on a phone at a parts counter, not read like a manual.

**Live:** https://t11mrp.github.io/vag-number-decoder/

## What it does

Type anything into the filter box at the top and every table on the page filters at once. `615` gives you brakes. `black` gives you every black finish code. `Caddy` gives you the type codes. Press `/` from anywhere to jump into the box, `Esc` to clear it.

The part number breakdown at the top is clickable. Tap any block and it takes you to the table that explains it.

## What is in it

- Anatomy of a part number, block by block
- Main groups, characters 1 to 0
- Subgroups, the 60 or so you actually meet
- Body shape digit, including the LHD and RHD split
- Type codes for VW, Audi, Skoda and SEAT
- Index letters, exchange parts, and the N, WHT, G, B, D and ZAW prefixes
- Interior and exterior finish codes
- VIN structure, maker prefixes, and the model year letter table
- The four mistakes that cost money
- House listing format for Shopify and eBay

## Running it

No build step, no dependencies, no framework. It is one HTML file.

```
git clone https://github.com/T11MRP/vag-number-decoder.git
cd vag-number-decoder
open index.html
```

Or just double click `index.html`.

The only external requests are the Google Fonts stylesheet and font files. Everything else is inline. It works offline apart from the fonts, which fall back to the system stack.

## Adding to it

Every filterable row is a `<tr>` with a `data-s` attribute holding lowercase search terms. The filter searches that attribute plus the row's visible text, so add synonyms and trade slang to `data-s` and they become searchable without cluttering the page.

```html
<tr data-s="615 brake discs calipers rotors">
  <td class="code">615</td>
  <td>Brake discs and calipers</td>
</tr>
```

To add a whole new section, copy an existing `<section>`, give it an `id`, and it joins the filter automatically. Sections with no matching rows hide themselves.

Colours are CSS custom properties on `:root`, redefined for dark mode in two places so that both the system setting and an explicit theme choice work. Change them in one place and the whole page follows.

## Accuracy

The subgroup and type code tables are a working reference compiled from public sources, not an extract of the official catalogue. They are right often enough to be useful at speed and wrong often enough that you should not quote a customer from them. When it matters, put the VIN into ETKA.

Corrections welcome, especially from anyone who spends their day in the real catalogue.

## Licence

MIT. See `LICENSE`.

Volkswagen, Audi, Skoda, SEAT and CUPRA are trademarks of their respective owners. This is an independent reference tool and is not affiliated with or endorsed by any of them.
