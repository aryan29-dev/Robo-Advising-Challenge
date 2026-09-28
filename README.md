# CFM 101 Robo-Advising Challenge — Market Meet Strategy

**Team:** 09  
**Team Members:** Aryan Singh, Jack Smith, Samyak Jain  
**Strategy:** Market Meet

Portfolio optimization project developed for the CFM 101 Robo-Advising Challenge. The program screens a provided universe of U.S. and Canadian equities, applies liquidity and portfolio constraints, and constructs a $1,000,000 CAD portfolio designed to follow the Market Meet strategy.

## Methodology

- **Ticker screening:** Filters the provided ticker universe to eligible U.S. and Canadian equities based on the challenge requirements.

- **Liquidity and market-cap filtering:** Removes securities that do not satisfy the required trading-volume and market-cap constraints.

- **Volatility filtering:** Removes the 25% most volatile stocks within each sector.

- **Benchmark construction:** Creates an equally weighted benchmark from the daily returns of the S&P 500 (`^GSPC`) and TSX Composite (`^GSPTSE`).

- **Correlation analysis:** Ranks the remaining stocks by their correlation with the combined benchmark to identify securities that most closely reflect broader market movements.

- **Portfolio construction:** Allocates capital while enforcing sector and individual-stock limits, maintaining the required market-cap mix, and accounting for CAD/USD foreign exchange and transaction fees.

- **Share allocation:** Converts target portfolio weights into share quantities while deploying as much of the $1,000,000 CAD portfolio as possible.

## Portfolio Constraints

- Select 10–25 stocks.
- Maximum 15% allocation to any individual stock.
- Maximum 40% allocation to any single sector.
- Include at least one large-cap company above $10B CAD and one small-cap company below $2B CAD.
- Exclude stocks that do not satisfy the required liquidity threshold.
- Account for transaction fees and foreign exchange when constructing the final portfolio.

## Key Outputs

- Filtered equity universe
- Combined S&P 500 and TSX benchmark
- Sector-level volatility filtering
- Stock rankings based on benchmark correlation
- Final portfolio weights and share allocations
- Portfolio constraint validation
- Final submission file: `Stocks_Group_09.csv`

## Libraries

| Library | Use |
| --- | --- |
| `pandas` | Data cleaning, transformation, and portfolio calculations |
| `NumPy` | Numerical calculations |
| `numpy-financial` | Financial calculations |
| `yfinance` | Historical market and security data |
| `matplotlib` | Data visualization |
| `IPython.display` | Notebook output and DataFrame display |
| `datetime` | Date handling |
| `random` | Randomized operations where required |

## Benchmark

The portfolio uses an equally weighted combination of daily returns from:

- S&P 500 (`^GSPC`)
- TSX Composite (`^GSPTSE`)

The resulting benchmark is used to measure correlation and support stock selection under the Market Meet strategy.
