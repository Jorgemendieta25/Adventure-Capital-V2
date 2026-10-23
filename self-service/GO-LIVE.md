# FloVibez Self-Service Rentals · Go-live checklist

## Smartwaiver automatic return
Open Smartwaiver → Create/Edit Waivers → edit the official FloVibez waiver → Settings → Redirect URL → Enable.

**Redirect URL (copy exactly):**
`https://jorgemendieta25.github.io/Adventure-Capital-V2/self-service/?waiver_return=1`

Choose whether the redirect should fire after submission or after email verification. **Publish the waiver** and test on a phone. The landing page recognizes `waiver_return=1` and shows a welcome-back message so guests know where to continue.

Important: Redirecting back to the page or clicking “I completed the waiver” **is not proof of signature**. Verify all participants' signed waivers through Smartwaiver before granting access.

## Actual brand logo
The site currently has a custom FloVibez-inspired vector brand mark with the FloVibez wordmark. To use the **exact company logo**, upload your authorized transparent PNG or SVG to `self-service/assets/flovibez-logo.png`, then replace the header vector with an `<img>` element referencing that file.

## Verify operational integration
- Link in use: official FloVibez Smartwaiver `https://waiver.smartwaiver.com/w/603675178139f/web/`.
- Link in use: published Peek booking gateway `https://book.peek.com/s/d200b1bc-05b1-4fb8-a435-74d300269d2c/WRkAK`.
- Payment is completed through Peek; the static page **does not** verify payment via API.
- There is **no remote lock integration** and no automated unlock code. Only authorized release after waiver and booking verification.
- Diagram on the safety page is conceptual, not a chart for navigation.
- Verify published availability, park closing times and operating conditions before unattended use.

## Publishing
Repo `Jorgemendieta25/Adventure-Capital-V2` → Settings → Pages → Source: GitHub Actions.
The workflow at `.github/workflows/flovibez-pages.yml` will deploy content on pushes.
Expected URL: `https://jorgemendieta25.github.io/Adventure-Capital-V2/self-service/`.
