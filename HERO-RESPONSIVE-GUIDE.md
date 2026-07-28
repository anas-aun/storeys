# Hero Section Responsive Implementation Guide

## Overview
This guide explains the responsive design implementation for the hero section of the Storeys website.

## Files Modified/Created

### New Files:
1. **css/hero-responsive.css** - Full responsive styles with comments
2. **css/hero-responsive.min.css** - Minified production version
3. **HERO-RESPONSIVE-GUIDE.md** - This documentation file

### Modified Files:
1. **index.html** - Added responsive CSS link and inline media queries

## Breakpoint Strategy

### Mobile First Approach
The responsive design follows a mobile-first methodology with the following breakpoints:

| Breakpoint | Device Type | Screen Width |
|------------|-------------|--------------|
| Base | Small Mobile | 320px - 480px |
| Small | Mobile | 481px - 767px |
| Medium | Tablet Portrait | 768px - 991px |
| Large | Tablet Landscape | 992px - 1199px |
| XL | Desktop | 1200px - 1599px |
| XXL | Large Desktop | 1600px - 1919px |
| XXXL | Extra Large Desktop | 1920px+ |

## Responsive Features

### 1. **Hero Container**
- Uses `100dvh` (dynamic viewport height) for modern mobile browsers
- Fallback to `100vh` for older browsers
- Minimum height ensures content visibility

### 2. **Video Background**
- Full-width coverage on all devices
- Optimized for mobile performance with GPU acceleration
- High DPI screen optimization for retina displays

### 3. **Data Tags & Contact**
- **Mobile (< 768px)**: Stacked vertically in single column
- **Tablet (768px+)**: Two columns side by side
- **Desktop (1200px+)**: Optimized spacing with original design

### 4. **Typography (Excellence Text)**
- **Mobile**: `clamp(2.5rem, 10vw, 5rem)` - scales with viewport
- **Tablet**: `clamp(6rem, 12vw, 12rem)` - larger, maintains proportion
- **Desktop**: `clamp(10rem, 16vw, 20rem)` - original large display
- **Large Desktop**: `clamp(16rem, 18vw, 32rem)` - maximum impact

### 5. **Spacing & Padding**
- **Mobile**: Reduced padding (1.5rem - 2rem)
- **Tablet**: Medium padding (3rem - 4rem)
- **Desktop**: Original design padding (6rem - 10rem)

## Special Optimizations

### Touch Devices
```css
@media (hover: none) and (pointer: coarse)
```
- Minimum touch target size of 44px for accessibility
- Enhanced clickable areas for tags and links

### Landscape Mobile
```css
@media (max-height: 500px) and (orientation: landscape)
```
- Adjusted heights to prevent content overflow
- Optimized typography for horizontal viewing

### High DPI Screens
```css
@media (-webkit-min-device-pixel-ratio: 2)
```
- Crisp image rendering for retina displays
- Optimized video quality

### Accessibility
```css
@media (prefers-reduced-motion: reduce)
```
- Disables animations for users with motion sensitivity
- Improves experience for users with vestibular disorders

## Implementation Instructions

### For Development:
Use the full version with comments:
```html
<link rel="stylesheet" type="text/css" href="css/hero-responsive.css">
```

### For Production:
Switch to the minified version:
```html
<link rel="stylesheet" type="text/css" href="css/hero-responsive.min.css">
```

## Testing Checklist

- [ ] iPhone SE (375x667) - Smallest modern mobile
- [ ] iPhone 12/13 (390x844) - Standard mobile
- [ ] iPhone 14 Pro Max (430x932) - Large mobile
- [ ] iPad Mini (768x1024) - Small tablet
- [ ] iPad Pro (1024x1366) - Large tablet
- [ ] Desktop 1366x768 - Common laptop
- [ ] Desktop 1920x1080 - Standard desktop
- [ ] Desktop 2560x1440 - Large desktop
- [ ] Landscape orientation on all mobile devices
- [ ] Touch interactions on mobile/tablet
- [ ] Reduced motion preference

## Browser Compatibility

### Supported Browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+
- Samsung Internet 14+

### Features Used:
- CSS Grid
- Flexbox
- CSS Custom Properties (Variables)
- Clamp() function
- Modern viewport units (dvh)
- Media queries Level 4

## Performance Tips

1. **Video Optimization**:
   - Use compressed MP4 files
   - Consider WebM for modern browsers
   - Add poster image for quick display

2. **Loading Strategy**:
   - Video loads with `preload="auto"` and `playsinline`
   - Poster image displays during load

3. **GPU Acceleration**:
   - `transform: translateZ(0)` forces GPU rendering
   - `will-change` hints for better performance

## Future Enhancements

1. **Container Queries**: When widely supported, replace some media queries
2. **Aspect Ratio**: Use native aspect-ratio property when supported by all browsers
3. **Dynamic Island Support**: Add safe-area-inset for iPhone 14 Pro+
4. **Picture Element**: Responsive images for different screen densities

## Troubleshooting

### Issue: Text too small on mobile
**Solution**: Check if the clamp() function is supported. Fallback to static sizes if needed.

### Issue: Video not playing on iOS
**Solution**: Ensure `playsinline` attribute is present and video is muted.

### Issue: Layout breaks on very small screens
**Solution**: Test on devices < 320px width. May need additional breakpoint.

### Issue: Touch targets too small
**Solution**: Verify min-height of 44px is applied to all interactive elements.

## Contact & Support

For questions or issues with the responsive implementation:
- Check browser console for errors
- Validate CSS using W3C CSS Validator
- Test on real devices, not just browser simulators

---

**Last Updated**: July 28, 2026
**Version**: 1.0.0
**Author**: Kiro AI
