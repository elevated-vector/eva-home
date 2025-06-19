# Team Section Image Update - ElevatedVector Website

## Overview
Updating the "Meet Our Team" section of the ElevatedVector website to replace initial circles with actual team member photos.

## Current Structure
The team section currently uses `.team-avatar` divs with initials:
- Hans Havlik: "HH"
- Bala Bosch: "BB" 
- Jordan Kearfott: "JK"

## Available Images
Located in `/Users/jordankearfott/ElevatedVector/eva-home-new/assets/images/`:
- `Hans_Havlik.png` (1.9MB)
- `Bala_Bosch.png` (320KB)
- `Jordan_Kearfott.jpg` (268KB)

## Implementation Plan
1. Replace `.team-avatar` content with `<img>` elements
2. Maintain existing styling for consistent circle appearance
3. Add `object-fit: cover` for proper image scaling
4. Ensure accessibility with proper alt attributes
5. Maintain hover effects and transitions

## CSS Changes Needed
- Update `.team-avatar` to handle image children
- Add image-specific styling for proper fit
- Ensure responsive behavior

## File: index.html
Section: Team Section (lines ~1200-1300 approximately)
