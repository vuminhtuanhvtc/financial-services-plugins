
# Vietnam Market Data Sources

Use this reference when analyzing Vietnamese companies listed on HOSE, HNX, or UPCOM.

## Data Source Priority (Vietnam)

### Tier 1 — Primary Sources (Free, Official)

1. **HOSE/HNX Official Filings**
   - HOSE: https://www.hsx.vn → Công bố thông tin → BCTC
   - HNX: https://www.hnx.vn → Tin công ty → BCTC
   - Content: BCTC quý/năm (kiểm toán + soát xét), nghị quyết ĐHĐCĐ, CBTT bất thường
   - Equivalent to: SEC 10-K/10-Q

2. **CafeF**
   - Financial data: https://s.cafef.vn/hose/{TICKER}.chn (hoặc /hnx/ cho HNX stocks)
   - BCTC chi tiết: https://s.cafef.vn/bao-cao-tai-chinh/{TICKER}/IncSta/
   - Content: Aggregated financials from official filings, stock data, news
   - Free, no API key required. Data sourced from HOSE/HNX filings.

3. **VietstockFinance**
   - URL: https://finance.vietstock.vn/{TICKER}/tai-chinh
   - Content: Standardized financial statements, ratios, charts
   - Free basic access.

4. **Simplize**
   - URL: https://simplize.vn/co-phieu/{TICKER}
   - Content: Analyst consensus, valuation, peer comparison, screener
   - Free. Good for consensus estimates (thay thế IBES).

### Tier 2 — Analyst Reports (Free/Partially Free)

5. **CTCK Research Reports** — Published by securities companies:
   - SSI Research: https://www.ssi.com.vn/khach-hang-ca-nhan/bao-cao-phan-tich
   - VNDirect: https://dstock.vndirect.com.vn/bao-cao-phan-tich
   - HSC: https://www.hsc.com.vn/vn/bao-cao-phan-tich
   - Vietcap (VCSC): https://www.vietcap.com.vn/research
   - ACBS, Shinhan, KBSV, MBS, BVSC — available on their websites
   - Content: Target price, DCF assumptions, consensus estimates, sector outlook

### Tier 3 — Supplementary (Free)

6. **Web Search** — For recent news, market commentary, corporate actions
7. **Company IR Websites** — {ticker}.com.vn or corporate websites
8. **TradingView / Investing.com** — Stock charts, technical data, beta
9. **Government data** — GSO (gso.gov.vn), SBV (sbv.gov.vn) for macro data

## What is NOT Available for Free in Vietnam

| Data Type | US Source | VN Status |
|-----------|----------|-----------|
| Real-time standardized API | Bloomberg, FactSet | FiinPro (paid 9M VNĐ/mo) — skip |
| Consensus estimates (structured) | IBES/FactSet | Simplize (free, limited) |
| Institutional ownership | SEC 13-F filings | Not publicly available in VN |
| Short interest data | Exchange data | Not available (no short selling infrastructure) |
| Options data | CBOE | No vanilla options. VN has **Covered Warrants** (chứng quyền có bảo đảm) since 2019 — limited data |

## Currency & Units

- **All values in VND** — standard unit: "tỷ đồng" (= 1 billion VND). Always use current USD/VND rate for conversion — do NOT use a fixed approximation
- **Number format:** `#,##0` with comma thousands separator
- **Per-share values:** đồng/cổ phiếu (VND/share)
- **Exchange rate:** Always note USD/VND rate and date when converting

## Fiscal Year Note

- Most VN companies use Dec 31 fiscal year end
- **Exceptions exist:** Some companies have FY ending Mar 31 or Jun 30
- **Always verify** the specific company's fiscal year before building models

## Filing Timeline

| Report | US Filing | VN Filing |
|--------|----------|----------|
| Quarterly (soát xét) | 10-Q within 40 days | Within 20 days after quarter end |
| Annual (kiểm toán) | 10-K within 60 days | Within 90 days after FY end |
| Earnings release | Same day (8-K) | Often delayed 20-30 days |
| Guidance | Common (forward) | Rare — use ĐHĐCĐ plan instead |
