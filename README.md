# Font metric overrides for Google Fonts
`font-metric-overrides.csv` is a CSV that contains font metric overrides for all [fonts](https://github.com/google/fonts) available from Google Fonts.
```csv
font,ascent-override,descent-override,line-gap-override
"/ofl/poppins/Poppins-Regular.ttf",1.05,0.35,0.1
"/apache/opensanscondensed/OpenSansCondensed-LightItalic.ttf",1.068847656,0.29296875,0
"/apache/chewy/Chewy-Regular.ttf",varies by OS,varies by OS,varies by OS
...
```

## Usage
Include font metric overrides to your stylesheets:
```css
h1 {
    font-family: "Poppins", "fallback for Poppins";
}
@font-face {
    font-family: "fallback for Poppins";
    src: local("Arial");
    ascent-override: 105%;
    descent-override: 35%;
    line-gap-override: 10%;
}
```

For more information on using font metric overrides see [Improved font fallbacks](https://developers.chrome.com/blog/font-fallbacks/).

## Additional Resources
`font-metadata.csv` contains various font metadata (for example, ascent/descent/line-gap, glyphs widths, and UPM) that is relevant to generating font fallbacks.

## Are there tools that can do this?
Yes!
Check out these tools:

**Non-framework tools:**
*   [Fontaine](https://github.com/unjs/fontaine): Fontaine is a library that automatically generates and inserts font fallbacks that use font metric overrides.
*   [Capsize](https://github.com/seek-oss/capsize) is a font sizing and layout library. Capsize provides an API for getting information about various font metrics.

**Framework tools:**
*   [@next/font](https://nextjs.org/docs/basic-features/font-optimization): Starting in Next 13, `next/font` automatically uses font metric overrides and `size-adjust` to provide matching font fallbacks.
*   [@nuxtjs/fontaine](https://github.com/nuxt-modules/fontaine): Starting in Nuxt 3, you can use `nuxt/fontaine` to automatically generate and insert matching font fallbacks into the stylesheets used by your Nuxt app.
