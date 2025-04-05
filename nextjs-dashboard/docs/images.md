# Image Optimization in Next.js

Next.js provides a powerful image optimization system through the `next/image` component. This guide explains how to optimize images in your Next.js application for better performance and user experience.

## Overview

Images are a crucial part of web applications but can significantly impact performance if not optimized. Next.js's image optimization system helps you:

- Prevent layout shift during image loading
- Automatically resize images for different devices
- Lazy load images outside the viewport
- Serve images in modern formats (WebP, AVIF) when supported by the browser

## The Image Component

The `<Image>` component is an extension of the HTML `<img>` tag with built-in optimization features:

```jsx
import Image from "next/image";

// Basic usage
<Image src="/hero.png" alt="Description" width={500} height={300} />;
```

## Using the Image Component

### Local Images

For images stored in your project's `/public` directory:

```jsx
import Image from "next/image";

export default function Page() {
  return (
    <Image
      src="/hero-desktop.png"
      width={1000}
      height={760}
      alt="Screenshots of the dashboard project showing desktop version"
    />
  );
}
```

### Remote Images

For images from external sources, you need to configure domains in `next.config.js`:

```js
// next.config.js
module.exports = {
  images: {
    domains: ["example.com"],
  },
};
```

Then use the component:

```jsx
<Image
  src="https://example.com/image.jpg"
  width={500}
  height={300}
  alt="Remote image"
/>
```

## Responsive Images

Next.js makes it easy to create responsive images that adapt to different screen sizes:

```jsx
<div className="flex items-center justify-center p-6 md:w-3/5 md:px-28 md:py-12">
  {/* Desktop image */}
  <Image
    src="/hero-desktop.png"
    width={1000}
    height={760}
    className="hidden md:block"
    alt="Desktop version"
  />

  {/* Mobile image */}
  <Image
    src="/hero-mobile.png"
    width={560}
    height={620}
    className="block md:hidden"
    alt="Mobile version"
  />
</div>
```

## Image Optimization Features

### Automatic Optimization

- **Format Optimization**: Automatically serves images in WebP or AVIF formats when supported by the browser
- **Size Optimization**: Resizes images to avoid shipping large images to devices with smaller viewports
- **Lazy Loading**: Images load only as they enter the viewport, improving initial page load time

### Layout Shift Prevention

- The `width` and `height` props are used to calculate the aspect ratio
- This prevents Cumulative Layout Shift (CLS) during image loading
- The actual rendered size can be controlled with CSS

### Priority Loading

For important images above the fold, use the `priority` prop:

```jsx
<Image src="/hero.png" alt="Hero image" width={500} height={300} priority />
```

## Best Practices

1. **Always specify dimensions**

   - Provide `width` and `height` props that match the source image's aspect ratio
   - This prevents layout shift and improves Core Web Vitals

2. **Use appropriate image formats**

   - Next.js automatically serves modern formats (WebP, AVIF) when supported
   - For best results, provide high-quality source images

3. **Implement responsive images**

   - Use different images for different screen sizes when appropriate
   - Leverage CSS to control how images are displayed

4. **Optimize for performance**

   - Use the `priority` prop for above-the-fold images
   - Let Next.js handle lazy loading for images below the fold

5. **Provide meaningful alt text**
   - Always include descriptive alt text for accessibility


## Additional Resources

- [Next.js Image Component Documentation](https://nextjs.org/docs/api-reference/next/image)
- [Image Optimization in Next.js](https://nextjs.org/docs/basic-features/image-optimization)
- [Improving Web Performance with Images (MDN)](https://developer.mozilla.org/en-US/docs/Learn/Performance/Multimedia)
- [How Core Web Vitals Affect SEO](https://web.dev/vitals/)
