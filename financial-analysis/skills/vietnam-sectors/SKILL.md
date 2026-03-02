---
name: vietnam-sectors
description: Industry-specific analysis frameworks for key Vietnamese sectors with unique KPIs, peer lists, and regulatory considerations. Use when analyzing Vietnamese companies or sectors. Triggers on Vietnamese company tickers (HOSE/HNX/UPCOM), Vietnamese sector analysis, or explicit Vietnam market references.
---

# Vietnam Sector-Specific Analysis

Reference this skill when analyzing companies listed on HOSE, HNX, or UPCOM.

## How to Detect Vietnam Context

Apply this skill when:
- Company ticker is on HOSE/HNX/UPCOM (e.g., BMP, VCB, HPG, VHM)
- User mentions Vietnamese companies or Vietnamese market
- Currency is VND or "tỷ đồng"

When Vietnam context is detected, also reference:
- [Vietnam Data Sources](../references/vietnam-data-sources.md)
- [VAS Accounting](../references/vas-accounting.md)
- [Vietnam Tax & Legal](../references/vietnam-tax-legal.md)

---

## Sector Frameworks

### 1. Banking (Ngân hàng)

**Key KPIs:**
| Metric | Definition | Good Range |
|--------|-----------|-----------|
| NIM (Net Interest Margin) | Net interest income / Avg earning assets | >3.5% = strong |
| CIR (Cost-to-Income Ratio) | OpEx / Operating income | <40% = efficient |
| NPL Ratio | Non-performing loans / Total loans | <2% = healthy |
| Cost of Risk | Provision expense / Avg total loans | <1.0% = healthy, >2.0% = stressed |
| Provision Coverage | Loan loss reserves / NPL | >100% = comfortable buffer |
| LDR (Loan-to-Deposit Ratio) | Total loans / Total deposits | SBV cap ~85% |
| CAR (Capital Adequacy Ratio) | Tier 1 + Tier 2 / RWA | Basel II min 8% |
| CASA Ratio | Current + savings / Total deposits | >30% = good funding |
| ROE | Net income / Avg equity | >15% = strong |
| Credit Growth | YoY loan growth | SBV assigns quota per bank |

**Peer Groups:**
| Group | Companies | Characteristics |
|-------|----------|----------------|
| SOE Banks | VCB, BID, CTG, AGRB | Government >50%, implicit guarantee |
| Large Private | TCB, MBB, ACB, VPB, HDBank | Dynamic, higher NIM |
| Mid Private | TPB, MSB, LPB, OCB, SHB | Growing, varied quality |

**VN-Specific:**
- SBV assigns individual **credit growth quotas** — key driver of loan growth
- **Circular 02** provisions, restructuring allowances affect NPL reporting
- SOE banks have **implicit government guarantee** → lower cost of funding
- Cross-selling: bancassurance, securities partnerships

---

### 2. Real Estate (Bất động sản)

**Key KPIs:**
| Metric | Definition | Notes |
|--------|-----------|-------|
| Landbank (ha) | Total land area controlled | Primary value driver |
| Presale value (tỷ VNĐ) | Pre-sold but unrecognized revenue | Forward indicator |
| Backlog | Signed contracts not yet delivered | Revenue visibility |
| NAV / share | Net Asset Value per share | Primary valuation method |
| Inventory turnover | Revenue / Avg inventory | Low = project delays |
| Debt / Equity | Total debt / Equity | >1.5x = concerning |

**Peer Groups:**
| Segment | Companies | Focus |
|---------|----------|-------|
| Residential | VHM, NVL, KDH, DXG, PDR | Apartments, landed property |
| Industrial | KBC, SZC, IDC, PHR | Industrial parks, FDI tenants |
| Commercial | VIC, REE (through subs) | Office, retail |

**VN-Specific:**
- **QSDĐ (Land Use Rights):** No freehold — QSDĐ has fixed term (50-70 yrs)
- **Revenue recognition:** VAS = at handover (bàn giao), NOT % completion
  → Revenue is very lumpy; compare backlog and presale for forward view
- **Legal status** of projects is critical: many projects stalled due to permits
- **Valuation:** NAV method preferred over DCF for pure-play developers
- Bond defaults (2022-2023) still affecting some developers

---

### 3. Consumer / Retail (Tiêu dùng / Bán lẻ)

**Key KPIs:**
| Metric | Definition | Notes |
|--------|-----------|-------|
| Same-store growth | YoY revenue from existing stores | Organic growth indicator |
| Store count | Total stores / new openings | Network expansion |
| Revenue per store | Total revenue / number of stores | Efficiency |
| Gross margin | Gross profit / Revenue | Product mix indicator |
| Inventory days | Avg inventory / COGS × 365 | <60 days ideal for retail |

**Peer Groups:**
| Segment | Companies | Focus |
|---------|----------|-------|
| Electronics retail | MWG (TGDD, DMX, BHX) | Dominant multi-format |
| Pharma retail | FRT (Long Châu) | Fastest growing chain |
| Dairy/FMCG | VNM, MSN (WinCommerce) | Brand dominance |
| F&B | SAB (Sabeco), BHN (Habeco) | Duopoly beer market |

**VN-Specific:**
- Demographics: ~100M population, median age ~31, rising middle class
- MWG (Thế Giới Di Động) dominates — use as benchmark for retail metrics
- **Bách Hóa Xanh** (MWG subsidiary) expansion is major growth story
- Foreign brands entering: Circle K, 7-Eleven, Uniqlo → competitive pressure

---

### 4. Utilities & Infrastructure (Tiện ích & Hạ tầng)

**Key KPIs:**
| Metric | Definition | Notes |
|--------|-----------|-------|
| Capacity factor | Actual output / Max possible | For power plants |
| ASP (giá bán) | Average selling price per unit | Regulated for electricity |
| Volume | kWh, m³, tons sold | Core revenue driver |
| RAB (Regulated Asset Base) | For regulated utilities | Base for allowed returns |
| D&A / Revenue | Depreciation intensity | High for capital-heavy |

**Peer Groups:**
| Segment | Companies | Notes |
|---------|----------|-------|
| Gas & Power | GAS, POW, PPC, NT2, HND | EVN pricing regulated |
| Water & Pipes | BMP, NTP, DNP, TDM | Public investment driven |
| Construction infra | CTD, HBC, VCG | Government contracts |
| Renewables | BCG, GEG, REE | Solar/wind growth |

**VN-Specific:**
- **Electricity:** EVN is sole buyer (monopsony) — ASP regulated by MOIT
- **Power Development Plan VIII (QHĐ8):** Renewables policy framework
- Pipe industry: driven by real estate recovery + public investment
- **PVC price** (input cost) affects margins for pipe manufacturers

---

### 5. Steel & Materials (Thép & Vật liệu)

**Key KPIs:**
| Metric | Definition | Notes |
|--------|-----------|-------|
| Capacity utilization | Actual output / Installed capacity | >80% = healthy |
| ASP | Average selling price per ton | Volatile, track monthly |
| HRC-spread | Hot-rolled coil price − input cost | Profitability indicator |
| Export ratio | Export revenue / Total revenue | China competition risk |

**Peer Groups:**
| Companies | Market Position |
|----------|----------------|
| HPG | #1 steel, integrated, largest |
| HSG | #1 galvanized steel |
| NKG | HRC/CRC, export focused |
| TIS, POM | Smaller, niche players |

**VN-Specific:**
- **Anti-dumping duties** on Chinese/Korean steel imports — policy driven
- HPG (Hòa Phát) is quasi-monopoly in construction steel → sets market price
- Input costs: iron ore (global), coal, scrap — all USD-denominated
- Long steel vs flat steel dynamics differ significantly

---

### 6. Technology & Fintech (Công nghệ)

**Key KPIs:**
| Metric | Definition | Notes |
|--------|-----------|-------|
| Revenue growth | YoY growth | >20% expected for tech |
| Gross margin | >50% for software/services | Hardware lower |
| R&D / Revenue | Investment in innovation | VN average 3-5% |
| Employee count growth | Headcount as proxy | IT talent competition |

**Companies:** FPT (dominant), CMG, ELC, VNG (unlisted→listed 2025)

**VN-Specific:**
- FPT is the tech benchmark — IT services, telecom, education
- **Digital transformation** government mandate (QĐ 749/QĐ-TTg)
- IT outsourcing to Japan/US is major revenue stream for VN tech
- Fintech: MoMo, ZaloPay, VNPay (mostly unlisted) — limited public comps

---

## Valuation Benchmarks by Sector (2024-2025)

| Sector | P/E Range | P/B Range | EV/EBITDA | Dividend Yield |
|--------|----------|----------|-----------|---------------|
| Banking | 6-12x | 1.0-2.5x | N/A (banks use P/E & P/B; EBITDA not meaningful for financial institutions) | 1-3% |
| Real Estate | 8-20x | 0.8-3.0x | 10-18x | 0-2% |
| Consumer/Retail | 12-25x | 2-5x | 8-15x | 1-3% |
| Pipes/Manufacturing | 8-15x | 1.0-3.0x | 6-12x | 3-6% |
| Utilities | 8-12x | 1.0-2.0x | 5-8x | 3-8% |
| Technology | 15-30x | 2-6x | 12-20x | 1-2% |
| Steel/Materials | 6-12x | 0.8-2.0x | 5-10x | 2-5% |

---

> **Note:** Valuation ranges above are approximate guidelines based on historical trading ranges. Always verify against current market data via CafeF screener or Simplize. Ranges shift with interest rate cycles, macro conditions, and sector-specific catalysts.

---

## Company Structure Considerations

### State-Owned Enterprises (DNNN)
- Government >51%: VCB, BID, CTG, GAS, PLX, PVD, BVH
- **Governance discount:** 5-15% vs private peers
- **High dividends:** State budget needs → high payout ratios
- **Political influence** on business decisions
- **SCIC divestment:** Catalyst for governance improvement

### Foreign Strategic Investor (Nhà đầu tư chiến lược)
- SCG → BMP, ThaiBev → SAB, Jardine → (ex-VNM)
- Generally **governance premium** vs domestic-only
- FOL constraints may limit further foreign buying

### Family-Controlled Conglomerates
- HPG (Trần Đình Long), VIC/VHM (Phạm Nhật Vượng), MSN (Nguyễn Đăng Quang)
- **Related-party transactions** — check TMBS "Giao dịch bên liên quan"
- **Conglomerate discount:** 10-20% typical
- Key-man risk: founder = key decision maker

### Cross-Holdings & Pyramidal Structures
- Holding → Subsidiaries → Sub-subsidiaries common
- Example: DNP → Nhựa Đồng Nai + Nước sạch + Bao bì
- **Valuation approach:** SOTP (Sum of the Parts) or consolidated with segment notes
- **⚠️ Minority Interest:** When parent owns <100% of subsidiary, only count parent's ownership % in SOTP. Example: VIC owns 68% VHM → only 68% of VHM's equity value accrues to VIC shareholders. Always subtract minority interest from consolidated NAV.
