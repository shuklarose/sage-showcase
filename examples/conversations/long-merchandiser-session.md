# Long: a merchandiser auditing two pages (9 turns)

> A Healf team member audits one product in depth, switches product mid-conversation, and asks for a cross-page comparison - testing focus switching and conversation memory.

Captured live on 2026-08-19T16:40:57.119Z against healf.com. Unedited.

---

**you:** Give me the full picture on this product. https://healf.com/en-uk/products/wellbel-women-90-capsules

**sage:** **Wellbel Women** is a daily physician-formulated supplement targeted at supporting hair, skin, and nail health from within.

### Overview & Pricing
- **Price:** **£67.99** for a bottle of **90 capsules**
- **Availability:** **in stock**
- **Subscription:** 10% saving available across flexible schedules (every 2 weeks, monthly, every 2 months, or every 3 months)
- **Serving size:** **3 capsules daily**, providing **30 servings** (a 1-month supply)

### What Is Inside
The formula includes a proprietary blend alongside key vitamins and minerals:
- **Proprietary Blend:** Methylsulfonylmethane (OptiMSM®), Horsetail Powder (Aerial Parts), Saw Palmetto Fruit Extract (45%), Stinging Nettle Leaf, PABA (Para-Aminobenzoic Acid), and Betaine HCl
- **Vitamins & Minerals:** Vitamin A (as Beta-Carotene), Folate (as Calcium L-5-Methyltetrahydrofolate, 667 µg DFE), Vitamin B12 (as Methylcobalamin), Vitamin D (as Cholecalciferol, Vitashine®, 1,000 IU), and Selenium (as Selenium Glycinate Complex, Albion®)
- **Other Ingredients:** Chicory Root Inulin, Capsule Shell (Hypromellose), Vegan L-Leucine, and Silicon Dioxide

### Appearance
It arrives in a cylindrical, matte light-beige jar containing 90 translucent capsules filled with a greenish-brown herbal powder.

### Customer Feedback
Customer sentiment is exceptionally positive, with an average score of **4.83/5** across **89 reviews**:
- **5 stars:** 81
- **4 stars:** 4
- **3 stars:** 2
- **2 stars:** 1
- **1 star:** 1

Reviewers frequently praise noticeable improvements in hair thickness, texture, and reduced shedding, with many mentioning visible results after 2 to 4 months of consistent daily use. Customers also highlight improvements in nail strength and general skin vitality.

Sourced from: commerce:variants, html-rsc:metafield.servings_per_container, html-rsc:metafield.suggested_use, html-rsc:metafield.ingredients, vision:product-photos, html-yotpo:bottomline.average_score, html-yotpo:bottomline.total_review, html-yotpo:bottomline.star_distribution, html-yotpo:reviews[]

<sub>22.3s | tools: navigate, ingest | data: tier 1 miss, tier 2 miss</sub>

---

**you:** what is weak on the page itself?

**sage:** An evaluation of the live listing identified five weaknesses:

### Findings & Areas for Improvement

- **High: Formulation contradiction regarding Biotin**
  - **Issue:** The main description claims the formula contains biotin (*"including biotin, selenium, vitamin A"*, *"Biotin: Contributes to the maintenance of normal hair and skin"*). Conversely, the *Why Brand* section states it is explicitly *"made without biotin, which can skew bloodwork results"*, and the published ingredient list contains no biotin.
  - **Action:** Remove all biotin references from the description and key benefit bullets to align with the ingredient panel.

- **Medium: Inconsistent product naming ("Glamlab" vs "Wellbel Women")**
  - **Issue:** While titled **Wellbel Women**, the live description, staged copy, and SEO meta description refer to the product as *"Glamlab"* or *"Glamlab by Wellbel"*.
  - **Action:** Standardise all body text, staged copy, and SEO metadata to use **Wellbel Women**.

- **Medium: Raw JSON exposed in image alt text**
  - **Issue:** The primary product image contains internal JSON string metadata in place of descriptive alt text (`{"category":"Front of Package","compliant":"UK-Compliant"...}`).
  - **Action:** Replace with clear, human-readable alt text for accessibility and SEO.

- **Low: Internal commercial data exposed in public tags**
  - **Issue:** Internal operational tags such as `Margin > 36.25`, `top-400-sold`, and `top_3500_net_sales` are visible in the storefront payload.
  - **Action:** Clean up public-facing tags to exclude commercial and margin metrics.

- **Low: Formatting error in the ingredients list**
  - **Issue:** A comma in the dosage splits Vitamin D into two separate items (*"Vitamin D (as Cholecalciferol) (Vitashine®) (1"* and *"000 IU)"*).
  - **Action:** Reformat the ingredient entry so that `1,000 IU` remains intact as a single item.

Sourced from: content.descriptionLive.value, content.descriptionStagedHidden.value, content.whyBrand.value, ingredients.value, product.title, seo.description.value, media.productImages, tags

<sub>26.9s | tools: evaluate | data: tier 0 hit</sub>

---

**you:** draft a better SEO meta description for it

**sage:** Here is an improved SEO meta description that removes the outdated "Glamlab" name, eliminates the unverified biotin claim, and highlights the verified formula within standard length limits:

> Support hair, skin, and nail health from within with Wellbel Women. Formulated with Saw Palmetto, OptiMSM®, Horsetail, and Selenium. Buy online at Healf.

*(154 characters)*

Sourced from: product.title, html-rsc:metafield.ingredients, html-rsc:metafield.benefits

<sub>3.4s | tools: none | data: none needed</sub>

---

**you:** does it contain vitamin d?

**sage:** Yes, it contains **Vitamin D (as Cholecalciferol, Vitashine®)** at a dosage of **1,000 IU** per 3-capsule serving.

Sourced from: html-rsc:metafield.ingredients

<sub>2.6s | tools: none | data: none needed</sub>

---

**you:** who is it for, going by what reviewers say?

**sage:** Going by customer reviews, **Wellbel Women** is primarily used by women targeting specific hair, nail, and skin concerns:

- **Thin, brittle, or shedding hair:** Reviewers frequently mention having naturally fine or brittle hair and turning to the supplement to increase thickness, improve texture, and reduce excess shedding (including shedding after coming off birth control).
- **People seeking stronger nails and skin support:** Customers note it covers multiple needs at once, reporting noticeably stronger nails and brighter skin alongside hair growth.
- **Those who have tried other hair supplements without success:** Several reviewers mention that other hair supplements failed to deliver results before finding success with Wellbel over consistent 2 to 4-month periods.

Sourced from: html-yotpo:reviews[]

<sub>5.0s | tools: ingest | data: tier 0 hit</sub>

---

**you:** now do the same health check on this one https://healf.com/en-uk/products/really-good-hair-oil

**sage:** An evaluation of the listing for **Really Good Hair Oil** identified six findings across compliance, merchandising, and metadata:

### Findings & Areas for Improvement

- **High: Unhedged physiological claims regarding hair growth and thinning**
  - **Issue:** The live copy claims the oil *"Stimulates hair follicle growth"*, *"promotes hair growth"*, and *"revives tired follicles, addressing concerns of hair thinning effectively"*. Under UK cosmetic advertising standards (ASA/CAP), topical cosmetic oils should avoid direct physiological regrowth or hair loss claims without robust clinical evidence.
  - **Action:** Soften the language to focus on cosmetic benefits, such as nourishing the scalp, conditioning strands, and supporting stronger-looking hair.

- **Medium: Incorrect pillar tag (`Eat` applied to a topical oil)**
  - **Issue:** The product carries the tag `Eat` despite being an external topical hair treatment with instructions for scalp application and washing.
  - **Action:** Remove the `Eat` tag to avoid miscategorisation in food and ingestible search filters.

- **Medium: Internal promotional and operational data in public tags**
  - **Issue:** Public storefront tags contain internal data such as `top_3500_net_sales`, `rc-member-healf-plus|price:member-discount|sub:15.0:percent|otp:15.0:percent`, `BF25_Overall_Collection_1`, and `June_Sale_2026`.
  - **Action:** Clean up public tags by moving internal logic and sale identifiers to private backend fields.

- **Medium: Missing alt text on gallery images**
  - **Issue:** Three out of four gallery images have no alt text (`null`), limiting screen-reader accessibility and image SEO.
  - **Action:** Add descriptive alt text across all gallery views describing the packaging, bottle, dropper, and texture.

- **Low: Marketing copy embedded in the ingredient list**
  - **Issue:** The first item in the structured ingredients field is a marketing sentence (*"Deep conditioning oils for damaged and dry hair. With Brahmi and Neem to renew scalp health..."*) rather than clean botanical/INCI ingredients.
  - **Action:** Remove promotional text from the ingredient list so it lists only the pure oils and extracts.

- **Low: Stale pre-order metafield on an active product**
  - **Issue:** The `preorder` metafield contains an old date (`2026-05-21`) even though the product is live and in stock.
  - **Action:** Clear the pre-order metafield to prevent conflicts with stock badges.

### Genuine Strengths
- **Complete content coverage:** Key Benefits, Suggested Use (covering both overnight and warm towel methods), FAQs, and Brand Story sections are fully populated.
- **Strong social proof:** Holds an average rating of **4.83/5** across **23 reviews**.

Sourced from: content.descriptionLive.value, product.productType, tags, content.suggestedUse.value, media.productImages, ingredients.value, extraPageFields.preorder.value, inventory.value, commerce.variants, html-yotpo:bottomline.average_score, html-yotpo:bottomline.total_review

<sub>24.4s | tools: navigate, evaluate | data: tier 1 miss, tier 2 miss</sub>

---

**you:** which of the two pages is in better shape?

**sage:** **Really Good Hair Oil** is currently in better shape. 

While both pages have tag clutter and image alt-text gaps, their primary compliance issues differ significantly in impact:

- **Wellbel Women has a direct internal contradiction:** The page actively confuses shoppers about its core formulation. The main copy explicitly highlights **biotin** as a key active ingredient, while the brand copy contradicts this by stating it is intentionally formulated without biotin, and the ingredient panel confirms no biotin is present. Additionally, it misnames the product as *"Glamlab"* across the body text and SEO metadata.
- **Really Good Hair Oil has coherent content:** The product name, benefits, full ingredient list, and detailed usage instructions (overnight and warm towel methods) are consistent and accurate to the physical product. Its main issue is aggressive cosmetic marketing claims (*"stimulates hair follicle growth"*), which requires tone softening rather than fixing broken product data.

Sourced from: content.descriptionLive.value, content.whyBrand.value, ingredients.value, product.title, seo.description.value, media.productImages, tags

<sub>4.7s | tools: none | data: none needed</sub>

---

**you:** what should the team fix first across both?

**sage:** Across both pages, the team should prioritise fixes in this order:

1. **Fix the contradictory biotin claim on Wellbel Women (Immediate)**
   - **Why first:** It is a direct factual contradiction on an active ingestible supplement. The live copy names biotin as a key active ingredient, while both the brand copy and the ingredient panel state it contains no biotin. This directly misleads shoppers with sensitivities or specific supplement requirements.

2. **Remove the legacy "Glamlab" branding on Wellbel Women**
   - **Why second:** The title, body copy, and SEO meta description still refer to the brand and product as *"Glamlab"*, damaging brand trust and confusing search engines.

3. **Soft-pedal the physiological hair growth claims on Really Good Hair Oil**
   - **Why third:** The copy claims the oil *"stimulates hair follicle growth"* and addresses hair thinning. Aligning these claims with UK cosmetic regulations (focusing on conditioning, scalp nourishment, and hair strength) protects against ASA compliance risk.

4. **Housekeeping across both listings (Metadata, Tags, and Alt Text)**
   - Remove the incorrect `Eat` tag on Really Good Hair Oil.
   - Clear internal operational tags (`top_3500_net_sales`, `June_Sale_2026`, etc.) and stale pre-order metafields from public storefront data.
   - Add descriptive alt text to all gallery images on both listings.

Sourced from: content.descriptionLive.value, content.whyBrand.value, ingredients.value, product.title, seo.description.value, tags, media.productImages, extraPageFields.preorder.value

<sub>4.3s | tools: none | data: none needed</sub>

---

**you:** nice - summarise this session in two lines for my notes

**sage:** We reviewed **Wellbel Women** (confirming its 1,000 IU Vitamin D content and customer feedback on thinning hair) and audited **Really Good Hair Oil**, finding that the oil page is in better overall shape. 

The top priorities across both are resolving the contradictory biotin and "Glamlab" copy on Wellbel Women, followed by softening the physiological hair growth claims and cleaning up internal tags on Really Good Hair Oil.

<sub>3.3s | tools: none | data: none needed</sub>

---
