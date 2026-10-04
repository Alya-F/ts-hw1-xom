# Данные к ДЗ 1 по временным рядам: ExxonMobil и нефть Brent

Данные к домашнему заданию 1 курса «Анализ и прогнозирование временных рядов». Ноутбук с решением читает их отсюда по прямым ссылкам, поэтому запускается сразу, без ручного скачивания файлов.

## Файлы

| Файл | Что внутри | Источник |
|---|---|---|
| `XOM_nasdaq_5Y.csv` | Дневные цены акций ExxonMobil (тикер XOM), 1255 торговых дней с 04.10.2021 по 02.10.2026. Колонки `Date`, `Close/Last`, `Volume`, `Open`, `High`, `Low`; даты в формате месяц/день/год, цены со знаком `$`, новые даты сверху. | [Nasdaq: XOM, Historical Data](https://www.nasdaq.com/market-activity/stocks/xom/historical), период 5Y, кнопка Download historical data |
| `DCOILBRENTEU.csv` | Цена нефти Brent, долларов за баррель, по рабочим дням с 20.05.1987 по 29.09.2026. Колонки `observation_date`, `DCOILBRENTEU`; в дни без котировок значение пустое. | [FRED: DCOILBRENTEU](https://fred.stlouisfed.org/series/DCOILBRENTEU), исходные данные EIA |

Оба файла скачаны 04.10.2026 и больше не меняются. Источники со временем дописывают новые дни, а все числа в ноутбуке посчитаны на этом снимке, поэтому данные хранятся здесь.

## Как загрузить

```python
import pandas as pd

DATA_URL = 'https://raw.githubusercontent.com/Alya-F/ts-hw1-xom/main/'

stocks_raw = pd.read_csv(DATA_URL + 'XOM_nasdaq_5Y.csv')
brent_raw = pd.read_csv(DATA_URL + 'DCOILBRENTEU.csv', parse_dates=['observation_date'])
```
