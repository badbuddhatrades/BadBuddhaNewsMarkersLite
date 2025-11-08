# BadBuddha NewsMarkers Lite

![Version](https://img.shields.io/badge/version-2.0.0-blue)
![Platform](https://img.shields.io/badge/platform-NinjaTrader%208-green)
![License](https://img.shields.io/badge/license-Free-brightgreen)

## Overview

BadBuddha NewsMarkers Lite is a free economic news event indicator for NinjaTrader 8 that displays today's high and medium impact news events directly on your intraday charts. See upcoming news releases with country flags, vertical guide lines, and clean time axis markers - all automatically synchronized from your CSV calendar file.

Perfect for day traders who need to avoid trading during high-impact news events or capitalize on volatility around economic releases.

## Features

- **Today's Events Only**: Displays high and medium impact economic news events for the current trading day
- **Visual Time Axis Markers**: Clean dots and labels on the chart's time axis showing exactly when news releases occur
- **Country Flags**: Instantly identify which country/currency is affected by each news event
- **Vertical Guide Lines**: Optional vertical lines at event times with configurable opacity and thickness
- **Auto-Reload CSV**: Automatically reloads your news calendar file every 5 minutes (configurable)
- **Simple & Clean**: No clutter - just the essential information you need
- **Automatic Updates**: Built-in update checking keeps you on the latest version
- **Intraday Charts Only**: Optimized for minute/tick/second charts where news timing matters most

## Installation

### Quick Install

1. Download the `BadBuddhaNewsMarkersLite.zip` file
2. Open NinjaTrader 8
3. From the Control Center, select **Tools > Import > NinjaScript Add-On**
4. Browse to the downloaded file and click **Import**
5. Restart NinjaTrader 8 (if prompted)

## Basics Setup

#### 1. CSV Calendar File

Your economic calendar CSV file will be located in:
```
Documents\NinjaTrader 8\BadBuddha_FFCalendar.csv
```

**CSV Format Requirements:**
- Headers: `DateTime` (or separate `Date` and `Time`), `Country`, `Currency`, `Impact`, `Event`/`Title`
- Times must be in UTC timezone
- Impact levels: `High`, `Medium`, `Low`, or `Holiday`

**Example CSV:**
```csv
DateTime,Country,Currency,Impact,Event
2025-09-06 08:30,United States,USD,High,Non-Farm Payrolls
2025-09-06 10:00,United States,USD,Medium,ISM Services PMI
2025-09-06 12:30,United States,USD,High,FOMC Minutes
```
**Do not manually edit the file**. NinjaTrader will update the file on a regular basis.

#### 2. Country Flags (Optional but Recommended)

1. Download flag PNG files  (https://github.com/badbuddhatrades/BadBuddhaNewsMarkersLite/raw/refs/heads/main/Flags_FX.zip)
2. Create folder: `Documents\NinjaTrader 8\Flags_FX\`
3. Place flag PNGs named by ISO2 code: `US.png`, `GB.png`, `EU.png`, `JP.png`, etc.

**Supported Currencies:**
USD, EUR, GBP, AUD, NZD, CAD, CHF, JPY, CNY

## Usage

### Adding to Chart

1. Open an **intraday chart** in NinjaTrader (5-minute, 1-minute, etc.)
2. Right-click the chart and select **Indicators**
3. Scroll to find `BadBuddha_NewsMarkers_Lite` or type in the search box
4. Click **Add** to apply with default settings
5. Configure parameters as needed (see Parameters section below)

### Basic Setup

**Recommended Settings:**
- **Timeframe**: 5-minute or 1-minute chart
- **CSV File Name**: `BadBuddha_FFCalendar.csv`
- **Auto-Reload**: 5 minutes
- **Show Vertical Lines**: Enabled
- **VLine Opacity**: 25% (subtle but visible)
- **VLine Thickness**: 3px

### Interpretation

- **Red Dots/Lines**: High impact events (major market movers)
- **Orange Dots/Lines**: Medium impact events (moderate volatility expected)
- **Vertical Lines**: Guide lines showing exact event time across the entire chart
- **Country Flags**: Quick visual identification of which economy is releasing data
- **Time Labels**: Shows event time in your local timezone + truncated event title

**Trading Tips:**
- Plan your trades around high-impact events (red markers)
- Consider exiting positions 15-30 minutes before major news
- Wait for volatility to settle after releases before re-entering
- Use medium impact events (orange) as potential opportunity zones

## Parameters

### Software Info (Read-Only)
| Parameter | Value | Description |
|-----------|-------|-------------|
| **Release Date** | September 2025 | Release month |
| **Indicator** | BadBuddha NewsMarkers Lite | Product name |
| **Version** | 2.0.0 | Current version |
| **Author** | BadBuddha Customs LLC | Developer |
| **License Tier** | LITE | Free version with upgrade path |

### Update Settings
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Enable Update Checks** | bool | true | Automatically check for new versions |
| **Update Cadence (Days)** | int | 1 | How often to check for updates |

### Lite Settings
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| **Auto-Reload (minutes)** | int | 5 | Reload CSV every X minutes (0 = disabled) |
| **Flag Folder** | string | Flags_FX | Folder name for flag PNG files |
| **Show Vertical Lines** | bool | true | Display vertical guide lines at event times |
| **VLine Opacity (%)** | int | 25 | Transparency of vertical lines (0-100) |
| **VLine Thickness (px)** | int | 3 | Width of vertical lines in pixels |

### Parameter Details

#### Show Vertical Lines
Enables/disables the vertical guide lines that span from top to bottom of the chart at each event time. Useful for seeing the exact timing across all price action.

#### VLine Opacity (%)
Controls the transparency of vertical guide lines. Lower values (10-30%) create subtle guides that don't obscure price action. Higher values (50-100%) make them more prominent. The line color matches the impact level (red for high, orange for medium).

## Examples

### Example 1: Pre-Market News Setup
**Scenario**: NFP (Non-Farm Payrolls) Friday at 8:30 AM ET

The indicator will show:
- Red dot and vertical line at 8:30 AM
- US flag icon
- Label: "08:30 Non-Farm Payrolls"

**Usage**: See the marker and plan to either close positions before 8:30 or wait until after the initial spike settles (typically 8:45-9:00).

### Example 2: Multiple Events Stacked
**Scenario**: FOMC day with multiple USD releases

The indicator automatically stacks multiple events at similar times:
- Each event gets its own row on the time axis
- Most important (highest impact) events shown with brightest vertical lines
- All events clearly labeled with country flags

## Tips & Best Practices

- **Check Before Market Open**: Verify today's events are loaded (check the chart time axis)
- **Combine With Price Action**: Use the news markers to understand sudden volatility spikes
- **Adjust VLine Opacity**: If lines are too distracting, reduce opacity to 10-15%
- **Multi-Monitor Setup**: Keep one chart with NewsMarkers visible while trading other instruments
- **Flag Folder Setup**: Invest 5 minutes to set up flags - the visual recognition is worth it

## Upgrade to Pro

**BadBuddha NewsMarkers PRO** includes advanced features for serious traders:

- ✅ **Past & Future Events**: See yesterday's and tomorrow's news (configurable date range)
- ✅ **Event Table**: Popout or overlay table with live countdowns to next event
- ✅ **Currency Filtering**: Auto-filter by instrument or custom currency list
- ✅ **Strategy Integration**: Expose news blackout periods to your NinjaScript strategies
- ✅ **Historical Backtesting**: Test strategies against past news events
- ✅ **User-Based Licensing**: Official NinjaTrader vendor support

[Learn More About Pro](https://badbuddhacustoms.com/newsmarkers-pro)

## Common Issues

### Issue: No events showing on chart
**Solution**:
1. Verify CSV file exists in `Documents\NinjaTrader 8\`
2. Check CSV file name matches the "CSV File Name" parameter
3. Ensure you're on an **intraday chart** (not daily/weekly)
4. Verify CSV contains events for today's date
5. Check NinjaTrader Output Window for error messages

### Issue: Events showing but no flags
**Solution**:
1. Create folder: `Documents\NinjaTrader 8\Flags_FX\`
2. Ensure flag PNGs are named correctly (US.png, GB.png, EU.png, etc.)
3. Use uppercase ISO2 codes for filenames
4. Check NinjaTrader Output Window for "Flag not found" messages

### Issue: Events showing at wrong time
**Solution**:
1. CSV times must be in **UTC timezone**
2. Indicator automatically converts UTC → your local timezone
3. Verify your CSV doesn't have timezone offset already applied
4. Check Windows timezone settings are correct

### Issue: Vertical lines not visible
**Solution**:
1. Ensure "Show Vertical Lines" is enabled
2. Increase "VLine Opacity (%)" to 50-100%
3. Increase "VLine Thickness (px)" to 5-10px
4. Check that events actually exist for today

## Version History

### v2.0.0 (September 2025)
- Initial release of BadBuddha NewsMarkers Lite
- Displays today's high and medium impact news events
- Country flags on time axis markers
- Vertical guide lines at event times
- Auto-reload CSV file functionality
- Configurable vertical line opacity and thickness
- Automatic update checking integrated

## Support

For questions, issues, or feature requests:
- **Website**: https://badbuddhacustoms.com
- **GitHub**: https://github.com/badbuddhatrades/BadBuddhaCustoms
- **Email**: support@badbuddhacustoms.com

### Frequently Asked Questions

**Q: Where can I get a news calendar CSV file?**
A: You can export calendars from sites like ForexFactory, Investing.com, or use the Pro version's built-in CSV downloader.

**Q: Can I use this on daily or weekly charts?**
A: No, this indicator is designed for intraday charts only where news timing is critical.

**Q: Does this work with futures, forex, and stocks?**
A: Yes! The indicator works with any NinjaTrader instrument. Use currency filtering in Pro for instrument-specific events.

**Q: How do I get past events or future events beyond today?**
A: Upgrade to BadBuddha NewsMarkers PRO for configurable date ranges.

## License

Copyright © 2025, BadBuddha Customs LLC
Free version - No license required

---

**Disclaimer**: This indicator is provided for educational and informational purposes. Trading involves risk. Past performance does not guarantee future results. Always verify news event times from official sources before making trading decisions.

**Made with ❤️ by BadBuddha Customs** | *Empowering NinjaTrader 8 Traders Since 2024*
