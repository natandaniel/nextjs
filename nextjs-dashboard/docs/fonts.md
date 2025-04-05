# Fonts in Next.js

Next.js provides a built-in font system that optimizes font loading and usage in your application. This guide explains how to use fonts effectively in your Next.js project.

## Setting Up Fonts

1. Create a fonts module (e.g., `app/ui/fonts.ts`):

```typescript
import { Inter, Lusitana } from "next/font/google";

export const inter = Inter({ subsets: ["latin"] });
export const lusitana = Lusitana({
  weight: ["400", "700"],
  subsets: ["latin"],
});
```

## Using Fonts in Components

1. Import the font from your fonts module:

```typescript
import { lusitana } from "@/app/ui/fonts";
```

2. Apply the font using the `className` property:

```typescript
<p className={`${lusitana.className} text-xl`}>This text uses Lusitana font</p>
```

## Optimization Features

### Preloading

- Fonts are preloaded automatically
- No additional configuration needed
- Improves First Contentful Paint (FCP)

### Caching

- Fonts are self-hosted with your application
- Browser caching is optimized
- Reduces network requests

### Layout Shift Prevention

- Font metrics are calculated at build time
- CSS size-adjust properties are automatically applied
- Prevents Cumulative Layout Shift (CLS)

## Additional Resources

- [Next.js Font Documentation](https://nextjs.org/docs/basic-features/font-optimization) - Official Next.js documentation on font optimization
- [Google Fonts](https://fonts.google.com/) - Browse and select fonts for your project
- [Font Loading Best Practices](https://web.dev/font-best-practices/) - Web.dev guide on font loading best practices
- [Variable Fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts/Variable_Fonts_Guide) - MDN guide on variable fonts
- [Font Display Property](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display) - MDN documentation on font-display CSS property
- [Font Subsetting](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range) - MDN guide on font subsetting with unicode-range
- [Font Loading API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API) - MDN documentation on the Font Loading API
- [Font Performance](https://web.dev/optimize-webfont-loading/) - Web.dev guide on optimizing web font loading
