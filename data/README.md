# QuickCart orders: data dictionary

`quickcart_orders.csv`: **3,000 past orders, 16 columns**, no missing values. 24.8% of orders were late.

> **Synthetic data.** QuickCart is a fictional company. The data was generated for this course to behave like real delivery data (lateness depends on distance, store load, weather, traffic, courier experience and vehicle, partly in combination). Don't draw conclusions about real delivery services from it.

| Column | Type | Meaning |
|---|---|---|
| `order_id` | id | Order number |
| `order_hour` | number | Hour the order was placed (8–22) |
| `weekday` | category | Mon … Sun |
| `distance_km` | number | Distance from store to customer, km |
| `items_count` | number | Number of items in the order |
| `basket_value_eur` | number | Order value in euros |
| `weather` | category | `clear`, `rain`, `snow` |
| `traffic_level` | number | Traffic index, 1 (empty roads) to 10 (jam) |
| `store_queue` | number | Orders waiting to be packed at the store when this order came in |
| `courier_experience_months` | number | How long the assigned courier has worked for QuickCart |
| `vehicle` | category | `bike`, `scooter`, `car` |
| `is_premium_customer` | 0/1 | Customer has a premium membership |
| `promo_used` | 0/1 | A promo code was used |
| `customer_previous_orders` | number | Orders this customer placed before |
| `customer_rating` | 1–5 | Stars the customer gave this order |
| **`late`** | 0/1 | **Target.** 1 = delivered more than 10 minutes after the promised time |
