# English below

# Analiza sprzedaży w pizzerii
**Projekt portfolio | SQL i Power BI**

## 1. Cel projektu

Celem analizy było poznanie wzorców sprzedaży w pizzerii: określenie, w jakich godzinach składanych jest najwięcej zamówień, ile pizz obejmuje typowe zamówienie oraz które produkty, kategorie i rozmiary generują najwyższy przychód.

Analizę przeprowadziłam w SQL, a wyniki przedstawiłam w raporcie Power BI.

## 2. Dane i narzędzia

Analiza została wykonana na tabeli `pizza_sales`, zawierającej 12 kolumn dotyczących zamówień i produktów, m.in. `order_id`, `quantity`, `order_date`, `order_time`, `unit_price`, `total_price`, `pizza_size`, `pizza_category` i `pizza_name`.

Menu obejmuje 32 rodzaje pizzy.

**Narzędzia:** SQL, Power BI.

## 3. Pytania analityczne

- W jakich godzinach składanych jest najwięcej zamówień?
- Ile pizz najczęściej obejmuje jedno zamówienie?
- Które pizze generują najwyższy i najniższy przychód?
- Która kategoria generuje największy przychód?
- Które rozmiary pizz generują największy przychód?
- Jakie są podstawowe statystyki cen jednostkowych?

## 4. Wyniki analizy

### 4.1. Ceny jednostkowe

| Miara | Wynik |
|---|---:|
| Minimalna cena jednostkowa | 9,75 |
| Maksymalna cena jednostkowa | 35,95 |
| Średnia cena jednostkowa | 16,50 |

Średnia cena jednostkowa wyniosła około 16,50.

### 4.2. Godziny z największą liczbą zamówień

Liczbę zamówień obliczono jako liczbę unikalnych identyfikatorów `order_id` w poszczególnych godzinach.

| Godzina | Liczba zamówień |
|---|---:|
| 12:00 | 2 106 |
| 13:00 | 2 062 |
| 18:00 | 2 026 |
| 17:00 | 1 988 |
| 19:00 | 1 677 |
| 16:00 | 1 621 |
| 20:00 | 1 369 |
| 14:00 | 1 277 |
| 15:00 | 1 240 |
| 11:00 | 1 034 |
| 21:00 | 1 033 |
| 22:00 | 555 |
| 23:00 | 24 |
| 10:00 | 8 |

Najwięcej zamówień złożono o 12:00 (2 106), a następnie o 13:00 (2 062). Wysoka liczba zamówień występowała również we wczesnych godzinach wieczornych, szczególnie o 17:00 i 18:00.

Wyniki wskazują na dwa okresy wzmożonego ruchu: porę lunchu oraz wczesny wieczór.

### 4.3. Liczba pizz w zamówieniu

Liczbę pizz w każdym zamówieniu obliczono przez zsumowanie wartości `quantity` dla poszczególnych `order_id`.

| Miara | Wynik |
|---|---:|
| Liczba unikalnych zamówień | 18 020 |
| Minimalna liczba pizz w zamówieniu | 1 |
| Maksymalna liczba pizz w zamówieniu | 25 |
| Średnia liczba pizz w zamówieniu | 2,31 |

Najczęściej zamówienie obejmowało jedną pizzę (6 858 zamówień). Na drugim miejscu znalazły się zamówienia na dwie pizze (5 221). Średnia wyniosła 2,31 pizzy na zamówienie.

W danych występują również większe zamówienia, w tym jedno obejmujące 25 pizz.

### 4.4. Przychód według pizzy

Przychód dla poszczególnych pizz obliczono jako sumę `unit_price * quantity`.

**Pizze o najwyższym przychodzie:**

| Pizza | Przychód |
|---|---:|
| The Barbecue Chicken Pizza | 36 150,75 |
| The Thai Chicken Pizza | 36 145,25 |
| The California Chicken Pizza | 34 375,25 |
| The Classic Deluxe Pizza | 32 043,00 |
| The Spicy Italian Pizza | 29 396,75 |

Najwyższy przychód osiągnęła The Barbecue Chicken Pizza (36 150,75), a wynik dla The Thai Chicken Pizza był bardzo zbliżony (36 145,25).

**Pizze o najniższym przychodzie w zestawieniu:**

| Pizza | Przychód |
|---|---:|
| The Brie Carre Pizza | 9 814,75 |
| The Green Garden Pizza | 12 261,25 |
| The Mediterranean Pizza | 12 653,25 |
| The Spinach Pesto Pizza | 13 062,00 |
| The Spinach Supreme Pizza | 13 088,25 |

Najniższy przychód w tym zestawieniu osiągnęła The Brie Carre Pizza (9 814,75).

### 4.5. Przychód według kategorii

| Kategoria | Przychód |
|---|---:|
| Classic | 185 538,30 |
| Supreme | 175 354,00 |
| Chicken | 164 161,75 |
| Veggie | 163 212,85 |

Najwyższy przychód wygenerowała kategoria Classic (185 538,30), a najniższy — Veggie (163 212,85).

### 4.6. Przychód według rozmiaru pizzy

| Rozmiar | Przychód |
|---|---:|
| L | 315 729,10 |
| M | 210 180,25 |
| S | 149 433,25 |
| XL | 12 061,50 |
| XXL | 862,80 |

Najwyższy przychód wygenerował rozmiar L (315 729,10), a najniższy — XXL (862,80).

Zestawienie dotyczy przychodu, a nie liczby zamówień ani liczby sprzedanych sztuk.

## 5. Najważniejsze wnioski

- **Godziny szczytu:** najwięcej zamówień składano w porze lunchu, szczególnie o 12:00 i 13:00. Wysoka liczba zamówień występowała również między 17:00 a 19:00.
- **Wielkość zamówień:** najczęściej zamawiano jedną pizzę. Średnia liczba pizz na zamówienie wyniosła 2,31.
- **Najwyższy przychód według produktu:** The Barbecue Chicken Pizza i The Thai Chicken Pizza osiągnęły bardzo zbliżone wyniki.
- **Najniższy przychód według produktu:** The Brie Carre Pizza miała najniższy przychód spośród przedstawionych pizz. Wynik ten może być punktem wyjścia do dalszej analizy, ale sam w sobie nie uzasadnia usunięcia produktu z menu.
- **Kategorie:** najwyższy przychód osiągnęła kategoria Classic.
- **Rozmiary:** najwyższy przychód wygenerował rozmiar L. Sam przychód nie pozwala jednak stwierdzić, że był to najczęściej zamawiany rozmiar.

## 6. Rekomendacje do dalszej analizy

- Porównać liczbę sprzedanych sztuk, przychód i — jeśli dostępne będą dane o kosztach — marżę poszczególnych pizz.
- Sprawdzić liczbę sprzedanych sztuk i zamówień dla każdego rozmiaru przed podjęciem decyzji dotyczących oferty.
- Wykorzystać wzorce godzinowe jako punkt wyjścia do analizy obsady pracowników lub promocji, a następnie ocenić ich wpływ na wyniki.

## 7. Raport Power BI

Wyniki analizy przedstawiłam również w raporcie Power BI. Wykres punktowy porównujący przychód i liczbę zamówień dla poszczególnych pizz pozwala sprawdzić, czy produkty z większą liczbą zamówień osiągają również wyższy przychód.

## 8. Ograniczenia analizy

- Dane nie zawierają informacji o kosztach składników ani marży, dlatego analiza dotyczy przychodu, a nie zysku.
- Przychód według rozmiaru nie jest tym samym co liczba zamówień lub liczba sprzedanych sztuk.
- Wyniki opisują dostępny zbiór danych i same w sobie nie wyjaśniają przyczyn różnic w sprzedaży.

## Podsumowanie

Analiza wykazała, że najwięcej zamówień składano w porze lunchu i we wczesnych godzinach wieczornych. Najczęściej zamówienie obejmowało jedną pizzę, a najwyższy przychód spośród analizowanych produktów osiągnęły The Barbecue Chicken Pizza i The Thai Chicken Pizza. Kategoria Classic oraz rozmiar L miały najwyższy przychód w swoich zestawieniach.

Projekt pozwolił przećwiczyć analizę danych sprzedażowych w SQL, formułowanie wniosków biznesowych oraz prezentowanie wyników w Power BI.

---

# Pizza Sales Analysis
**Portfolio Project | SQL and Power BI**

## 1. Project Objective

The goal of this project was to explore sales patterns in a pizzeria by identifying peak ordering hours, understanding how many pizzas are typically included in an order, and determining which products, categories, and pizza sizes generate the highest revenue.

I performed the analysis using SQL and presented the results in a Power BI report.

## 2. Dataset and Tools

The analysis was based on the `pizza_sales` table, which contains 12 columns related to orders and products, including `order_id`, `quantity`, `order_date`, `order_time`, `unit_price`, `total_price`, `pizza_size`, `pizza_category`, and `pizza_name`.

The menu contains 32 pizza varieties.

**Tools:** SQL, Power BI.

## 3. Business Questions

- During which hours are the most orders placed?
- How many pizzas are most commonly included in an order?
- Which pizzas generate the highest and lowest revenue?
- Which pizza category generates the highest revenue?
- Which pizza sizes generate the highest revenue?
- What are the basic statistics for unit prices?

## 4. Analysis Results

### 4.1. Unit Prices

| Metric | Result |
|---|---:|
| Minimum unit price | 9.75 |
| Maximum unit price | 35.95 |
| Average unit price | 16.50 |

The average unit price was approximately 16.50.

### 4.2. Hours with the Highest Number of Orders

The number of orders was calculated by counting distinct `order_id` values for each hour.

| Hour | Number of Orders |
|---|---:|
| 12:00 PM | 2,106 |
| 1:00 PM | 2,062 |
| 6:00 PM | 2,026 |
| 5:00 PM | 1,988 |
| 7:00 PM | 1,677 |
| 4:00 PM | 1,621 |
| 8:00 PM | 1,369 |
| 2:00 PM | 1,277 |
| 3:00 PM | 1,240 |
| 11:00 AM | 1,034 |
| 9:00 PM | 1,033 |
| 10:00 PM | 555 |
| 11:00 PM | 24 |
| 10:00 AM | 8 |

The highest number of orders was recorded at 12:00 PM (2,106), followed by 1:00 PM (2,062). Order volume was also high in the early evening, particularly at 5:00 PM and 6:00 PM.

The results indicate two periods of increased activity: lunchtime and the early evening.

### 4.3. Number of Pizzas per Order

The number of pizzas in each order was calculated by summing `quantity` for each `order_id`.

| Metric | Result |
|---|---:|
| Number of unique orders | 18,020 |
| Minimum number of pizzas per order | 1 |
| Maximum number of pizzas per order | 25 |
| Average number of pizzas per order | 2.31 |

Orders containing one pizza were the most common (6,858 orders), followed by orders containing two pizzas (5,221). The average was 2.31 pizzas per order.

The dataset also includes larger orders, including one order containing 25 pizzas.

### 4.4. Revenue by Pizza

Revenue for each pizza was calculated as the sum of `unit_price * quantity`.

**Pizzas with the highest revenue:**

| Pizza | Revenue |
|---|---:|
| The Barbecue Chicken Pizza | 36,150.75 |
| The Thai Chicken Pizza | 36,145.25 |
| The California Chicken Pizza | 34,375.25 |
| The Classic Deluxe Pizza | 32,043.00 |
| The Spicy Italian Pizza | 29,396.75 |

The Barbecue Chicken Pizza generated the highest revenue (36,150.75), closely followed by The Thai Chicken Pizza (36,145.25).

**Pizzas with the lowest revenue in the selected ranking:**

| Pizza | Revenue |
|---|---:|
| The Brie Carre Pizza | 9,814.75 |
| The Green Garden Pizza | 12,261.25 |
| The Mediterranean Pizza | 12,653.25 |
| The Spinach Pesto Pizza | 13,062.00 |
| The Spinach Supreme Pizza | 13,088.25 |

The Brie Carre Pizza generated the lowest revenue among the pizzas shown (9,814.75).

### 4.5. Revenue by Category

| Category | Revenue |
|---|---:|
| Classic | 185,538.30 |
| Supreme | 175,354.00 |
| Chicken | 164,161.75 |
| Veggie | 163,212.85 |

The Classic category generated the highest revenue (185,538.30), while the Veggie category generated the lowest (163,212.85).

### 4.6. Revenue by Pizza Size

| Size | Revenue |
|---|---:|
| L | 315,729.10 |
| M | 210,180.25 |
| S | 149,433.25 |
| XL | 12,061.50 |
| XXL | 862.80 |

Size L generated the highest revenue (315,729.10), while size XXL generated the lowest (862.80).

This comparison measures revenue, not the number of orders or the number of pizzas sold.

## 5. Key Findings

- **Peak hours:** The highest number of orders occurred around lunchtime, particularly at 12:00 PM and 1:00 PM. Order volume was also high between 5:00 PM and 7:00 PM.
- **Order size:** Orders containing one pizza were the most common. The average number of pizzas per order was 2.31.
- **Highest revenue by product:** The Barbecue Chicken Pizza and The Thai Chicken Pizza generated very similar revenue.
- **Lowest revenue by product:** The Brie Carre Pizza had the lowest revenue among the pizzas shown. This finding may warrant further investigation but does not, on its own, justify removing the product from the menu.
- **Categories:** The Classic category generated the highest revenue.
- **Pizza sizes:** Size L generated the highest revenue. However, revenue alone does not establish that it was the most frequently ordered size.

## 6. Recommendations for Further Analysis

- Compare the number of units sold and revenue for each pizza, and include profit margins if cost data becomes available.
- Examine the number of units sold and orders for each pizza size before making decisions about the menu.
- Use hourly ordering patterns as a starting point for further analysis of staffing levels or promotions, then evaluate their impact on business results.

## 7. Power BI Report

I also presented the analysis results in a Power BI report. A scatter plot comparing revenue and the number of orders for each pizza helps explore whether products with more orders also generate higher revenue.

## 8. Limitations

- The dataset does not include ingredient costs or profit margins, so the analysis focuses on revenue rather than profit.
- Revenue by pizza size is not equivalent to the number of orders or the number of units sold.
- The results describe the available dataset and do not, by themselves, explain the reasons behind differences in sales.

## Summary

The analysis showed that the highest number of orders occurred around lunchtime and in the early evening. Orders containing one pizza were the most common, while The Barbecue Chicken Pizza and The Thai Chicken Pizza generated the highest revenue among the products analyzed. The Classic category and size L generated the highest revenue within their respective comparisons.

This project provided practical experience in analyzing sales data with SQL, developing business insights, and presenting results using Power BI.

