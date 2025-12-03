# Adrift - Premium Graphic Street Wear Landing Page

## Project Description
Adrift is a landing page for a fictional streetwear brand that combines cosmic themes with psychology-inspired designs. The site features a bold, modern aesthetic with a focus on unique acid-washed apparel for "cosmic wanderers." The page includes a hero section, embedded video, product showcase, size chart, and contact form - all built with responsive design principles.

## CSS Transform Implementation
I implemented a 'transform on hover' for the call-to-action button:
```css
.cta-button:hover {
    transform: translateX(-50%) translateY(-4px);
}
```
This creates a subtle lift effect when users hover over the "Explore The Collection" button.

## CSS Animation Implementation
I implemented a 'scroll-triggered fade-in animation' for the product cards:
```css
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
```
The product cards fade in and slide up as they enter the viewport, using the modern `animation-timeline: view()` property with a fallback for older browsers.

## Table Content Type
I chose a product specifications table (size chart) that displays t-shirt measurements across different sizes (S, M, L, XL, 2XL) with columns for length, shoulder width, chest width, and sleeve length measurements. This provides essential sizing information for potential customers.

## Challenges Encountered and Solutions

### Challenge 1: Video Container Sizing
Problem: The video container was displaying with extra space around the video, making it look awkward.

Solution: Removed the forced 16:9 aspect ratio and allowed the video to display at its natural aspect ratio by using `width: 100%; height: auto;` which made the container fit the video perfectly.

### Challenge 2: Mobile Trust Banner Overflow
Problem: The trust banner text was extending beyond the viewport on mobile devices.

Solution: Added mobile-specific CSS to reduce padding, decrease font size, and adjust icon sizing: `padding: 0 20px; font-size: 12px;` in the media query.

### Challenge 3: File Naming with Spaces
Problem: Received validation errors for image paths containing spaces (e.g., "adrift wordmark.png").

Solution: Renamed all files to use hyphens instead of spaces (e.g., "adrift-wordmark.png") for proper URL compatibility.

## Key Learnings

1. Fixed positioning requires offset compensation - When using `position: fixed` on navigation, you must add padding to the body to prevent content from being hidden behind the nav.

2. Mobile-first thinking is essential - Many desktop styles need to be adjusted or overridden for mobile. Testing at multiple breakpoints (375px, 768px, 1440px) throughout development prevents issues.

3. Modern CSS features need fallbacks - Using newer features like `animation-timeline: view()` requires `@supports` queries and fallback styles for older browsers.

4. File naming conventions matter - Avoiding spaces in filenames prevents URL encoding issues and validation errors. 

5. Semantic HTML improves structure - Using proper elements like `<article>`, `<section>`, and `<nav>` with appropriate IDs and classes makes the code more maintainable and accessible.

6. Form validation enhances UX - Implementing visual feedback with CSS (`:valid`, `:invalid`, `:focus` states) helps users understand form requirements without JavaScript.

7. Responsive images and media - Using `max-width` and proper sizing prevents content overflow while maintaining aspect ratios across devices.