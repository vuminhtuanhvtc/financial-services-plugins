# Portfolio Rebalance

description: Analyze portfolio allocation drift and generate rebalancing trade recommendations across accounts. Considers tax implications, transaction costs, and wash sale rules. Triggers on "rebalance", "portfolio drift", "allocation check", "rebalancing trades", or "my portfolio is out of balance".

## Workflow

### Step 1: Current State

For each account, capture:
- Account type (taxable, IRA, Roth, 401k)
- Holdings with current market value
- Cost basis (for taxable accounts)
- Unrealized gains/losses per position

### Step 2: Drift Analysis

Compare current allocation to IPS targets:

| Asset Class | Target % | Current % | Drift | $ Over/Under |
|------------|----------|-----------|-------|-------------|
| US Large Cap Equity | | | | |
| US Small/Mid Cap | | | | |
| International Developed | | | | |
| Emerging Markets | | | | |
| Investment Grade Bonds | | | | |
| High Yield / Credit | | | | |
| TIPS / Inflation Protected | | | | |
| Alternatives | | | | |
| Cash | | | | |

Flag positions exceeding the rebalancing band (typically ±3-5%).

### Step 3: Trade Recommendations

Generate trades to bring allocation back to target:

**Tax-Aware Rebalancing Rules:**
- Prefer rebalancing in tax-advantaged accounts (IRA, Roth) first — no tax consequences
- In taxable accounts, avoid selling positions with large short-term gains
- Harvest losses where possible while rebalancing
- Watch for wash sale rules (30-day window) across all accounts
- Consider directing new contributions to underweight asset classes instead of trading

**Trade List:**

| Account | Action | Security | Shares/$ | Reason | Tax Impact |
|---------|--------|----------|----------|--------|-----------|
| | Buy/Sell | | | Rebalance / TLH | ST gain / LT gain / Loss |

### Step 4: Asset Location Review

Optimize which assets are held in which account types:
- **Tax-deferred (IRA/401k)**: Bonds, REITs, high-turnover funds (highest tax drag)
- **Roth**: Highest expected growth assets (tax-free growth)
- **Taxable**: Tax-efficient equity (index funds, ETFs, munis), tax-loss harvesting candidates

### Step 5: Implementation

- Total trades by account
- Estimated transaction costs
- Estimated tax impact (realized gains/losses)
- Net effect on allocation drift

### Step 6: Output

- Drift analysis table
- Recommended trade list (Excel)
- Tax impact summary
- Before/after allocation comparison

## Important Notes

- Don't rebalance for rebalancing's sake — small drift within bands is fine
- Tax costs can outweigh rebalancing benefits in taxable accounts — calculate the breakeven
- Consider pending cash flows (contributions, withdrawals, RMDs) before trading
- Check for any client-specific restrictions (ESG, concentrated stock, lockups)
- Document rationale for every trade for compliance records
- Wash sale rules apply across accounts — coordinate trades across the household

---

## 🇻🇳 Vietnam Market Adjustments

### Asset Classes (replaces US SPY/AGG/EFA)
| VN Asset Class | Instruments | Typical Allocation |
|---------------|------------|-------------------|
| Cổ phiếu (Equities) | HOSE/HNX/UPCOM stocks, ETFs (VN30, VNFIN LEAD) | 30-60% |
| Trái phiếu (Bonds) | Government bonds (TPCP), corporate bonds (caution) | 10-20% |
| Tiền gửi (Deposits) | Bank term deposits (4-6% p.a.) | 10-30% |
| Vàng (Gold) | SJC gold bars, gold-linked savings | 5-15% |
| Bất động sản (Real Estate) | Direct property, REITs (limited) | 10-30% |

### Benchmark
- **VN-Index** (HOSE) replaces S&P 500 as primary equity benchmark.
- **VNALL-Index** for broader market including HNX and UPCOM.

### Rebalancing Considerations
- **No wash sale rule:** Simplifies rebalancing — no 30-day waiting period after selling at a loss.
- **Transaction costs:** Brokerage 0.15-0.35% + CGT 0.1% = meaningful for frequent rebalancing. Rebalance quarterly or when drift exceeds 5%.
- **T+2 settlement:** Stock transactions settle T+2 in Vietnam.
- **Gold allocation:** Culturally significant in VN. SJC gold bars are the standard. Track VN gold premium vs global price.
- **Bank deposits:** Often used as "safe" allocation — compare rates across banks (Vietcombank, Techcombank, MB, etc.).

