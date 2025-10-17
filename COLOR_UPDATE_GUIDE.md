# V2V Color Scheme Update Guide
## Futuristic Blue + Teal Theme

## Color Changes Summary

### Replace OLD colors with NEW colors:

#### Primary Brand Colors
- **OLD**: `#6366f1` (Indigo) and `#8b5cf6` (Purple)
- **NEW**: `#06b6d4` (Cyan) and `#14b8a6` (Teal)

#### Background Colors
- **OLD**: `#0a0e27`, `#1a1f3a`, `#0f1229`, `#13172e`
- **NEW**: `#0a1628`, `#0d1b2a`, `#0f1f2e`

#### Card Backgrounds
- **OLD**: `rgba(30, 35, 60, 0.8)`, `rgba(20, 25, 45, 0.8)`
- **NEW**: `rgba(15, 31, 46, 0.8)`, `rgba(10, 22, 40, 0.8)`

#### Border Colors
- **OLD**: `rgba(99, 102, 241, 0.X)`
- **NEW**: `rgba(20, 184, 166, 0.X)` (keep same opacity)

### Typography Changes
- **OLD Font**: `'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`
- **NEW Font**: `'Segoe UI', 'Roboto', -apple-system, BlinkMacSystemFont, sans-serif`

- **Font Weight Adjustments**:
  - Reduce 800 → 700
  - Reduce 700 → 600 (for most headings)

### Border Radius - Simpler Style
- Large cards: 20px → 16px or 12px
- Buttons: 12px → 10px
- Small elements: Keep at 8-10px

---

## Files to Update

1. ✅ **01_Dashboard_Landing.html** - UPDATED
2. **02_Target_Identification.html** - Needs update
3. **03_Business_Analysis_Results.html** - Needs update + TREND CHART
4. **04_Investment_Opportunity_Summary.html** - Needs update
5. **05_Competitor_Comparison.html** - Needs update

---

## Trend Chart Addition for Business Analysis Results

### Location
Add after the "Score Overview" section (after line ~216 in the original file)

### HTML Structure
```html
<!-- Performance Trend Chart -->
<div class="trend-section">
    <div class="trend-header">
        <div class="trend-title">Performance Trend</div>
        <div class="time-range-tabs">
            <div class="time-tab">7D</div>
            <div class="time-tab">1M</div>
            <div class="time-tab active">3M</div>
            <div class="time-tab">6M</div>
            <div class="time-tab">1Y</div>
            <div class="time-tab">All</div>
        </div>
    </div>
    
    <div class="chart-container">
        <!-- Chart grid lines -->
        <div class="chart-grid">
            <div class="grid-line"><span class="grid-label">10.0</span></div>
            <div class="grid-line"><span class="grid-label">8.0</span></div>
            <div class="grid-line"><span class="grid-label">6.0</span></div>
            <div class="grid-line"><span class="grid-label">4.0</span></div>
            <div class="grid-line"><span class="grid-label">2.0</span></div>
        </div>
        
        <!-- SVG Line Chart -->
        <div class="chart-line">
            <svg class="chart-svg" viewBox="0 0 1000 240" preserveAspectRatio="none">
                <defs>
                    <linearGradient id="lineGradient" x1="0%" y1="0%" x2="100%" y2="0%">
                        <stop offset="0%" style="stop-color:#06b6d4;stop-opacity:1" />
                        <stop offset="100%" style="stop-color:#14b8a6;stop-opacity:1" />
                    </linearGradient>
                    <linearGradient id="areaGradient" x1="0%" y1="0%" x2="0%" y2="100%">
                        <stop offset="0%" style="stop-color:#06b6d4;stop-opacity:0.3" />
                        <stop offset="100%" style="stop-color:#06b6d4;stop-opacity:0" />
                    </linearGradient>
                </defs>
                
                <!-- Area fill under line -->
                <path d="M 0 80 L 100 90 L 200 75 L 300 70 L 400 65 L 500 55 L 600 50 L 700 45 L 800 40 L 900 35 L 1000 30 L 1000 240 L 0 240 Z" 
                      fill="url(#areaGradient)" />
                
                <!-- Trend line -->
                <path d="M 0 80 L 100 90 L 200 75 L 300 70 L 400 65 L 500 55 L 600 50 L 700 45 L 800 40 L 900 35 L 1000 30" 
                      stroke="url(#lineGradient)" 
                      stroke-width="3" 
                      fill="none" />
                
                <!-- Data points -->
                <circle cx="0" cy="80" r="5" fill="#06b6d4" />
                <circle cx="100" cy="90" r="5" fill="#06b6d4" />
                <circle cx="200" cy="75" r="5" fill="#06b6d4" />
                <circle cx="300" cy="70" r="5" fill="#06b6d4" />
                <circle cx="400" cy="65" r="5" fill="#06b6d4" />
                <circle cx="500" cy="55" r="5" fill="#06b6d4" />
                <circle cx="600" cy="50" r="5" fill="#06b6d4" />
                <circle cx="700" cy="45" r="5" fill="#06b6d4" />
                <circle cx="800" cy="40" r="5" fill="#06b6d4" />
                <circle cx="900" cy="35" r="5" fill="#06b6d4" />
                <circle cx="1000" cy="30" r="5" fill="#14b8a6" />
            </svg>
        </div>
        
        <!-- X-axis labels -->
        <div class="x-axis">
            <span class="x-label">Jul</span>
            <span class="x-label">Aug</span>
            <span class="x-label">Sep</span>
            <span class="x-label">Oct</span>
        </div>
    </div>
    
    <!-- Trend statistics -->
    <div class="trend-stats">
        <div class="trend-stat">
            <div class="trend-stat-label">3-Month Change</div>
            <div class="trend-stat-value positive">+12.5%</div>
        </div>
        <div class="trend-stat">
            <div class="trend-stat-label">Average Score</div>
            <div class="trend-stat-value">8.4</div>
        </div>
        <div class="trend-stat">
            <div class="trend-stat-label">Peak Score</div>
            <div class="trend-stat-value">8.9</div>
        </div>
        <div class="trend-stat">
            <div class="trend-stat-label">Trend Direction</div>
            <div class="trend-stat-value positive">↗ Improving</div>
        </div>
    </div>
</div>
```

### CSS Styles to Add
```css
/* Trend Chart Section */
.trend-section {
    background: linear-gradient(135deg, rgba(15, 31, 46, 0.8) 0%, rgba(10, 22, 40, 0.8) 100%);
    border: 1px solid rgba(20, 184, 166, 0.15);
    border-radius: 12px;
    padding: 28px;
    margin-bottom: 32px;
}

.trend-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 24px;
}

.trend-title {
    font-size: 18px;
    font-weight: 600;
}

.time-range-tabs {
    display: flex;
    gap: 8px;
    background: rgba(6, 182, 212, 0.05);
    padding: 4px;
    border-radius: 8px;
}

.time-tab {
    padding: 8px 16px;
    border-radius: 6px;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
    color: #9ca3af;
}

.time-tab:hover {
    background: rgba(20, 184, 166, 0.1);
    color: #ffffff;
}

.time-tab.active {
    background: linear-gradient(135deg, #06b6d4 0%, #14b8a6 100%);
    color: #ffffff;
}

.chart-container {
    position: relative;
    height: 280px;
    margin-top: 20px;
}

.chart-grid {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 40px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.grid-line {
    height: 1px;
    background: rgba(20, 184, 166, 0.1);
    position: relative;
}

.grid-label {
    position: absolute;
    left: -40px;
    top: -8px;
    font-size: 11px;
    color: #6b7280;
}

.chart-line {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 40px;
}

.chart-svg {
    width: 100%;
    height: 100%;
}

.x-axis {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
}

.x-label {
    font-size: 11px;
    color: #6b7280;
}

.trend-stats {
    display: flex;
    gap: 32px;
    margin-top: 24px;
    padding-top: 24px;
    border-top: 1px solid rgba(20, 184, 166, 0.1);
}

.trend-stat {
    flex: 1;
}

.trend-stat-label {
    font-size: 12px;
    color: #6b7280;
    margin-bottom: 6px;
}

.trend-stat-value {
    font-size: 20px;
    font-weight: 600;
}

.trend-stat-value.positive {
    color: #10b981;
}

.trend-stat-value.negative {
    color: #ef4444;
}
```

---

## Quick Find & Replace Guide

### For ALL HTML files:

1. **Find**: `#6366f1` → **Replace**: `#06b6d4`
2. **Find**: `#8b5cf6` → **Replace**: `#14b8a6`
3. **Find**: `#0a0e27` → **Replace**: `#0a1628`
4. **Find**: `#1a1f3a` → **Replace**: `#0d1b2a`
5. **Find**: `#0f1229` → **Replace**: `#0d1b2a`
6. **Find**: `#13172e` → **Replace**: `#0a1628`
7. **Find**: `#1a1f3a` → **Replace**: `#0f1f2e`
8. **Find**: `rgba(99, 102, 241,` → **Replace**: `rgba(20, 184, 166,`
9. **Find**: `rgba(139, 92, 246,` → **Replace**: `rgba(20, 184, 166,`
10. **Find**: `rgba(30, 35, 60,` → **Replace**: `rgba(15, 31, 46,`
11. **Find**: `rgba(20, 25, 45,` → **Replace**: `rgba(10, 22, 40,`
12. **Find**: `'Inter',` → **Replace**: `'Segoe UI', 'Roboto',`
13. **Find**: `font-weight: 800` → **Replace**: `font-weight: 700`
14. **Find**: `font-weight: 700` → **Replace**: `font-weight: 600` (for headings, not numbers)

---

## Visual Changes Summary

### Before (Purple/Indigo)
- Primary: Indigo (#6366f1) + Purple (#8b5cf6)
- Dark blue-purple backgrounds
- Heavy font weights (800)
- Larger border radius (20px)

### After (Cyan/Teal)
- Primary: Cyan (#06b6d4) + Teal (#14b8a6)
- Darker blue-gray backgrounds
- Cleaner font weights (600-700)
- Tighter border radius (10-12px)
- More professional, modern, tech-forward aesthetic

---

## Status

- ✅ Dashboard Landing - UPDATED
- ⏳ Target Identification - Pending
- ⏳ Business Analysis Results - Pending + needs trend chart
- ⏳ Investment Opportunity Summary - Pending
- ⏳ Competitor Comparison - Pending
