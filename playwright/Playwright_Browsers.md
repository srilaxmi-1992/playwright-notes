# Playwright – Browser Support Notes

## Browser Engines (Binaries Used by Playwright)

Playwright runs tests using bundled browser engines:

* **Chromium** → Base for Chrome, Edge
* **Firefox (Nightly Build)** → Custom patched version used by Playwright
* **WebKit** → Engine behind Safari

---

## Real Browser Execution Support

Playwright can also run tests on some real installed browsers:

* Supported:

  * Chrome
  * Edge
  * Opera
  * Brave

* Not fully supported as real browsers:

  * Firefox (uses Playwright’s patched version instead)
  * Safari (uses WebKit engine, not actual Safari browser)

---

## Key Takeaway

Playwright primarily uses **browser engines (binaries)** for consistency and reliability, while offering limited support for **real browser execution** where applicable.
