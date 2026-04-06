#DAY 1

# Instagram Thrift Store DB


![alt text](<er-diagram.png>)

Database design for an Instagram store selling **thrift** and **handmade** items.
Supports product management, inventory tracking, orders, payments, and shipping.

## Tables

* User (id, name, email, phoneNumber)
* Product (id, name, type, price, size, color)
* Inventory (id, product_id, quantity)
* Order (id, customer_id, amount)
* OrderItem (id, order_id, product_id, quantity, price)
* Payment (id, order_id, payment_status, payment_method)
* Shipping (id, order_id, address, status, tracking_id)

## Relationships

* User → many Orders
* Order → many OrderItems
* Product → many OrderItems
* Product → one Inventory
* Order → one Payment
* Order → one Shipping

Thrift items have quantity **1**, handmade items can have **multiple**.


