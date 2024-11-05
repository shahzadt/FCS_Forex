# FCS Forex API Wrapper - Python

**Last Updated**: 2024-11-04 (Version 3)

The **FCS Forex API Wrapper** is a Python library for fetching forex quotes and economic data, providing responses in JSON format. This library allows you to retrieve live currency exchange rates, historical data, economic calendar events, and technical indicators.

## Features

- Supports over 2000 currency exchange rates.
- Updates prices every 10 seconds.
- Access to 25 years of historical data.
- Includes moving averages (MA) and indicators signals.
- Economic calendar with global events data.

## Requirements

- Python >= Python 3.13.0
- An FCS API key, available [here](https://fcsapi.com/dashboard).

## Installation

Clone the repository and install any dependencies listed in `requirements.txt`:

```bash
git clone <repository_url>
cd fcs_forex
pip install -r requirements.txt
```

## Getting Started

### Setting up the API Key
1. Get your API key from the [FCS API Dashboard](https://fcsapi.com/dashboard).
2. Update the `api_key` parameter when initializing the `FCSForex` class in `main.py`, or pass it directly to the class instance.

```python
from fcs_forex import FCSForex

# Initialize with your API key
forex_api = FCSForex(api_key='YOUR_API_KEY')
```
## API Response Format
The default response format is JSON.

## Available Methods

1. **Fetch Symbols List**  
   Get a list of available forex or crypto symbols.
   ```python
   symbols_list = forex_api.get_symbols_list()

2. **Get Latest Price**
   Retrieve the latest price for specific currency pairs.

   ```python
   response = forex_api.get_latest_price(['EUR/USD', 'USD/JPY', 'GBP/CHF'])
   ```

3. **Currency Conversion**

    Convert one currency into another. For example, converting 200 EUR to USD.

    ```python
    conversion_result = forex_api.get_converter(200, 'EUR', 'USD')
    ```

4. **Retrieve Currency Profile**

    Get details for specified currencies by symbol.

    ```python
    profile = forex_api.get_profile('EUR,USD,JPY')
    ```

5. **Fetch Base Prices**

    Get all quote prices for a specified base currency.

    ```python
    base_prices = forex_api.get_base_prices('EUR')
    ```

6. **Retrieve Historical Candle Data**

    Get historical OHLC (Open, High, Low, Close) data for specified currency pairs.

    ```python
    candle_data = forex_api.get_last_candle('EUR/USD', '1d')
    ```

7. **Access Historical Data**

    Retrieve historical forex data for a specific time period.

    ```python
    history_data = forex_api.get_history({
        'symbol': 'EUR/USD',
        'period': '1d',
        'from': '2024-10-01',
        'to': '2024-10-31'
    })
    ```

8. **Technical Indicators**

    Fetch moving averages, pivot points, and other top indicators.

    ```python
    moving_averages = forex_api.get_moving_averages('EUR/USD', '1d')
    pivot_points = forex_api.get_pivot_points('EUR/USD', '1d')
    indicators = forex_api.get_technical_indicator('EUR/USD', '1d')
    ```

9. **Economic Calendar**

    Get economic events within a specified date range for a currency or country.

    ```python
    calendar_data = forex_api.get_economy_calendar(symbol='USD', from_date='2024-11-01', to_date='2024-11-05')
    ```

10. **Search for Forex Symbols**

    Search for forex symbols by keyword or criteria.

    ```python
    search_results = forex_api.get_search_query('BTC')

    ```


## Other Resources

- **WebSocket API for Real-Time Prices:** [View Documentation](#)
- **PHP Library:** [Available on GitHub](https://github.com)

## Support

For support, please contact us at [support@fcsapi.com](mailto:support@fcsapi.com) or use the live chat.

## License

This project is provided under the MIT License. See the LICENSE file for more details.
