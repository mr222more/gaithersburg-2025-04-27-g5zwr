# CustomEuroGlass Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the CustomEuroGlass landing page. Whether you're new to web development or need a quick reference, follow these step-by-step instructions.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the company name and navigation menu:

```html
<header class="fixed w-full bg-gray-900/95 backdrop-blur-sm z-50 border-b border-gray-800">
    <nav class="container mx-auto px-4 sm:px-6 lg:px-8 py-4">
        <div class="flex items-center justify-between">
            <a href="/" class="text-2xl font-bold text-white tracking-tight">CustomEuroGlass</a>
```

To update:
1. Change company name: Replace "CustomEuroGlass" with your desired text
2. Modify header background: Update `bg-gray-900/95` to change color/opacity
   - Example darker background: `bg-gray-950/95`
   - Example lighter background: `bg-gray-800/95`

### Hero Section
The main landing section contains your primary heading and call-to-action buttons:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight text-white mb-6">
    Gaithersburg's Premier <span class="text-blue-400">Shower Glass</span> Installation
</h1>
```

To update:
1. Change heading text: Replace the existing text while maintaining the `<span>` element for highlighted words
2. Adjust text size:
   - Mobile: Change `text-4xl`
   - Tablet: Change `md:text-5xl`
   - Desktop: Change `lg:text-6xl`

### Responsive Design Tips
- Classes starting with `sm:` apply to screens 640px and up
- Classes starting with `md:` apply to screens 768px and up
- Classes starting with `lg:` apply to screens 1024px and up

## Fixing Broken Links

### Current Link Inventory
1. Navigation Menu Links:
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-300 hover:text-white transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-300 hover:text-white transition-colors duration-300">Benefits</a>
    <a href="#contact" class="text-gray-300 hover:text-white transition-colors duration-300">Contact</a>
</div>
```

2. Call-to-Action Links:
```html
<a href="http://www.customeuroglass.com" class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-2 rounded-full">
    Get Started
</a>
```

To update links:
1. Internal links (starting with #): Ensure the href matches the corresponding section's id attribute
2. External links: Replace `http://www.customeuroglass.com` with your actual website URL
3. Email links: Update `mailto:lt@customeuroglass.com` with your contact email

## Adding Privacy and Terms Pages

### Footer Modification
Add privacy and terms links to the footer's Quick Links section:

```html
<div>
    <h3 class="text-xl font-bold mb-4">Quick Links</h3>
    <ul class="space-y-2">
        <li><a href="#features" class="text-gray-400 hover:text-white transition-colors duration-300">Features</a></li>
        <li><a href="#benefits" class="text-gray-400 hover:text-white transition-colors duration-300">Benefits</a></li>
        <li><a href="#contact" class="text-gray-400 hover:text-white transition-colors duration-300">Contact</a></li>
        <!-- Add these new lines -->
        <li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

### Creating Policy Pages
1. Create new files named `privacy.html` and `terms.html` in the same directory as `index.html`
2. Copy the header and footer from `index.html` to maintain consistent styling
3. Add your policy content between the header and footer

## Troubleshooting

### Common Issues and Solutions

1. Broken Internal Links
- **Problem**: Clicking navigation links doesn't scroll to sections
- **Solution**: Ensure section `id` attributes match the link `href` values exactly
```html
<!-- Link -->
<a href="#features">Features</a>
<!-- Matching section -->
<section id="features">
```

2. Responsive Design Issues
- **Problem**: Layout breaks on mobile devices
- **Solution**: Check for proper responsive classes
```html
<!-- Example of proper responsive classes -->
<div class="text-sm md:text-base lg:text-lg">
```

3. Style Inconsistencies
- **Problem**: New elements don't match existing design
- **Solution**: Copy Tailwind classes from similar existing elements
```html
<!-- Copy these classes for new links -->
class="text-gray-400 hover:text-white transition-colors duration-300"
```

### Need Help?
If you encounter issues not covered in this guide:
1. Check the [Tailwind CSS documentation](https://tailwindcss.com/docs)
2. Verify all HTML tags are properly closed
3. Use browser developer tools (F12) to inspect elements
4. Ensure all files are in the correct directory structure

Remember to test all changes across different devices and browsers before deploying to production.