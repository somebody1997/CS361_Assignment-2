# Microservice for Stock Strategy Recommendations

This microservice provides stock buying and selling recommendations based on selected strategies. It allows users to query for the best times to buy or sell a specific stock symbol within a given date range.

## How to Request Data

To request data from the microservice, make a GET request to the appropriate endpoint. The request URL follows this format:


```
GET /api/Best_Strategies/:strategy/:symbol/:action/:startDate/:endDate
```
### Parameters:

- `:strategy` - The trading strategy to use (e.g., `low-risk`, `Equity`, `Global Macro`, `Jump Trading`, `Two Sigma`).
- `:symbol` - The stock symbol to query (e.g., `AAPL`).
- `:action` - The action, either `BUY` or `SELL`.
- `:startDate` - The start date of the period to analyze (YYYY-MM-DD).
- `:endDate` - The end date of the period to analyze (YYYY-MM-DD).

### Example call to request when to buy AAPL stock using a conservative strategy:


## How to Receive Data

The microservice responds with a JSON object containing the recommendation. For a buy request, the response will look like this:

```json
{
  "symbol": "AAPL",
  "strategy": "low-risk",
  "startDate": "2024-01-01",
  "endDate": "2024-01-31",
  "bestBuyPrice": 150.00,
  "bestBuyDate": "2024-01-15"
}
```
For a sell request, the structure would be similar, indicating the best sell price and date.
