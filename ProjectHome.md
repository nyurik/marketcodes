# Intro #

This project simplifies working with various constants used by financial firms. Each list is encoded as a .NET enum, with attributes used to provide additional information.

  * [ISO 3166](http://goo.gl/qhbE) - Country codes (US, GB, RU) _[Official Site](http://goo.gl/4N1zl)_
    * Name
    * Primary country currency

  * [ISO 4217](http://goo.gl/7LIxC) - Currency codes (USD, GBP, RUB) _[Official Site](http://goo.gl/WBSPI)_
    * Name
    * Number of significant decimals
    * Symbols
    * List of countries that use it

  * [ISO 10383](http://goo.gl/ChIP) - MIC (market/exchange) codes (XNYS, XLON, XMIC). _[Official Site](http://goo.gl/zLsI)_
    * Name
    * Country
    * Timezone string as used by `TimeZoneInfo` class
    * Url

# Examples #

```

public enum CountryCode
{
  /// <summary> United States </summary>
  [D("United States"), I(C.USD)] US = 840,
  ...
}

public enum CurrencyCode
{
  /// <summary> US Dollar </summary>
  [Currency("US Dollar", 2, "$", "Cent[D]")]
  [U(C.AS), U(C.EC), U(C.SV), U(C.GU), U(C.HT), U(C.MH), U(C.FM), U(C.MP), U(C.PW), U(C.PA), U(C.TC), U(C.US), U(C.VI)]
  USD = 154,
  ...
}

public enum MarketCode
{
  /// <summary> NEW YORK STOCK EXCHANGE, INC. [US] -- Active Before June 2005</summary>
  [D("NEW YORK STOCK EXCHANGE, INC. [US]")] 
  [I("NEW YORK STOCK EXCHANGE, INC.", "NYSE", C.US, "Eastern  Standard Time", "NEW YORK", "www.nyse.com")]
  XNYS = 0x584E5953,
  ...
}
```