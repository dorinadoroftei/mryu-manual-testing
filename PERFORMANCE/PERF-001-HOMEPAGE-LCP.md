# PERF-001 – Homepage LCP Image Loaded With Low Priority

## Summary

A PageSpeed Insights review found that the homepage Largest Contentful Paint (LCP) image was loaded with `loading="lazy"` and did not use `fetchpriority="high"`.

Because the main above-the-fold image is requested with low priority, it may appear later than necessary and increase perceived homepage loading time.

## Module

Homepage / Performance / Media loading

## Environment

- **Website:** MR YU
- **URL:** https://mryu.ro
- **Platform:** WordPress
- **Page builder:** Elementor
- **Environment:** Production
- **Evidence date:** 2026-07-06
- **Tool:** Google PageSpeed Insights

## Observed result

The LCP diagnostic reported:

- the LCP resource used lazy loading;
- high fetch priority was not applied;
- the image request could be discovered in the initial document;
- a critical request-chain latency of approximately 1.449 seconds was reported in the saved evidence.

## Expected result

The primary above-the-fold image should be discoverable immediately and should not be deferred as a below-the-fold asset.

Where supported by the page implementation:

- remove lazy loading from the specific LCP image;
- apply `fetchpriority="high"`;
- preserve explicit width and height;
- keep the optimized WebP asset;
- avoid applying high priority to multiple non-critical images.

## Business impact

A slower first meaningful visual can:

- reduce perceived site quality;
- make the homepage feel unresponsive on mobile connections;
- increase the risk of abandonment before customers reach the menu;
- negatively affect Core Web Vitals.

## Severity

**Medium**

The website remains usable, but the issue affects performance and the first impression of a customer-facing production page.

## Priority

**Medium**

The repair should be implemented through a controlled method that does not require an unsafe Elementor/Elementor Pro update.

## Root cause

**Partially confirmed**

Confirmed technical observations:

- the LCP image used lazy loading;
- the image did not receive high fetch priority.

The exact WordPress, Elementor, optimization-plugin or theme mechanism that added the loading behavior was not confirmed.

## Recommended validation

1. Identify the current LCP element in a fresh PageSpeed run.
2. Confirm that it is still the homepage hero image.
3. Change only the target image loading behavior.
4. Purge relevant caches.
5. Inspect the rendered HTML.
6. Verify that `loading="lazy"` is absent from the LCP image.
7. Verify that `fetchpriority="high"` is present once.
8. Repeat PageSpeed on mobile and desktop.
9. Check homepage visuals and responsive layout.
10. Run menu, navigation and cart smoke tests.

## Change constraints

- Do not update Elementor or Elementor Pro only to address this finding.
- Preserve the current validated image asset unless a replacement is explicitly approved.
- Back up before changing theme, template or code-snippet behavior.
- Avoid global rules that disable lazy loading for every image.

## Status

**Open – requires current-state verification and controlled retest**

## Evidence available

A saved PageSpeed Insights PDF from 2026-07-06 documents the diagnostic. The repository does not include the raw file because supporting evidence must be reviewed and sanitized before public upload.
