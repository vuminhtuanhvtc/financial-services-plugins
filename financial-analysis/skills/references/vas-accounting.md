
# VAS (Vietnamese Accounting Standards) Reference

Use this reference when analyzing Vietnamese companies reporting under VAS.

## VAS vs US GAAP — Key Differences

| Item | US GAAP | VAS | Impact on Analysis |
|------|---------|-----|-------------------|
| Revenue recognition | ASC 606 (5-step model) | IAS 18-based, simpler | Real estate: VAS recognizes at handover, not % completion → revenue lumpy |
| Lease accounting | ASC 842 (on-balance sheet) | Off-balance sheet (old IAS 17) | VN: operating leases not on BS → debt metrics appear lower |
| Goodwill | Impairment testing only | Amortized over ≤10 years | VN: M&A target NI lower due to goodwill amortization charge |
| Fair value measurement | Widely used (ASC 820) | Cost model predominant | VN: asset values may be understated vs fair value |
| Stock-based compensation | ASC 718 (P&L expense) | Very rare, no specific standard | VN: ESOP exists but accounting treatment varies |
| R&D costs | Mostly expensed | Can be capitalized (development phase) | VN: EBITDA may appear higher if R&D capitalized |
| Financial instruments | ASC 815/320 (complex) | Simpler classification | VN: fewer derivative disclosures |
| Segment reporting | ASC 280 (mandatory) | Limited | VN: segment data often unavailable → harder to do SOTP |

## Financial Statement Structure (VAS)

| VAS Name | English | Standard Tab Name |
|----------|---------|-------------------|
| Báo cáo kết quả kinh doanh (KQKD) | Income Statement | IS (keep as IS) |
| Bảng cân đối kế toán (CDKT) | Balance Sheet | BS (keep as BS) |
| Báo cáo lưu chuyển tiền tệ (LCTT) | Cash Flow Statement | CF (keep as CF) |
| Thuyết minh BCTC (TMBS) | Notes to Financial Statements | Notes |

> Tab naming: Keep standard IS/BS/CF names — the meaning is identical.

## VAS Income Statement Line Items

| VAS Line | English | Notes |
|----------|---------|-------|
| Doanh thu bán hàng và CCDV | Revenue from sales & services | = Revenue |
| Giảm trừ doanh thu | Revenue deductions | Trade discounts, returns |
| Doanh thu thuần | Net revenue | = Net Revenue |
| Giá vốn hàng bán | Cost of goods sold | = COGS |
| Lợi nhuận gộp | Gross profit | = Gross Profit |
| Doanh thu hoạt động tài chính | Financial income | Interest income, FX gains, dividends received. Often large for cash-rich VN companies |
| Chi phí tài chính | Financial expenses | Includes interest expense + FX losses |
| Trong đó: Chi phí lãi vay | Of which: Interest expense | Extract for EBITDA/EBIT calc |
| Chi phí bán hàng | Selling expenses | = S&M / SGA |
| Chi phí QLDN | General & admin expenses | = G&A |
| LN thuần từ HĐKD | Net operating profit | ⚠️ ≠ US GAAP EBIT! VAS already deducts financial expenses. To calculate EBIT: LN thuần từ HĐKD + Chi phí lãi vay − Doanh thu tài chính |
| Thu nhập khác / Chi phí khác | Other income / expenses | Non-recurring items |
| Lợi nhuận trước thuế (LNTT) | Profit before tax | = PBT / EBT |
| Chi phí thuế TNDN | Corporate income tax | = Tax expense |
| Lợi nhuận sau thuế (LNST) | Net income | = Net Income |

## NOL (Net Operating Loss) Carry

- **VN rule:** NOL carry forward **5 years only** (vs unlimited in US post-2017)
- Impact: Loss-making companies face expiring NOLs → tax planning important
- Model accordingly in 3-statement projections

## Audit Standards

- Vietnamese companies use **Vietnam Standards on Auditing (VSA)**
- Listed companies must be audited by firms approved by SSC (Ủy ban Chứng khoán)
- Quarterly reports: soát xét (review), not full audit
- Annual reports: full audit required within 90 days of FY end
