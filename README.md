# RateRight PGH: Parking Demand Forecasting

Forecasts 7-day daily paid parking transactions for 9 Pittsburgh parking zones
to help parking managers decide which zones to review first.

## Results
- Selected a model per zone (ETS, SARIMAX, Ridge) using 4 rolling 7-day backtests
- Reserved holdout week: 7.1% WAPE vs. 9.5% for seasonal naive (25.6% relative improvement)
- Output: a ranked zone watchlist flagging above- and below-normal demand

## Data
- [Pittsburgh Parking Transactions (WPRDC)](https://data.wprdc.org/dataset/parking-transactions)
- [Parking Meters and Payment Points (WPRDC)](https://data.wprdc.org/dataset/pittsburgh-parking-meters-and-payment-points)
- Weather: Open-Meteo historical archive (downloaded in the notebook)

Download the two WPRDC files, save them as `transaction_info.csv` and
`parking_info.csv`, and place them in the same folder as the notebook.

## Limitations
- Forecasts paid transactions, not physical occupancy
- Weather tests used observed weather, so they show an upper bound, not deployable accuracy
- Sundays are not forecast because most Sunday records are missing
