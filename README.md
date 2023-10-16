***

# Sliding GapMinder

### Instructions

In this version of the bubble chart from [Hans Rosling's GapMinder storytelling video](https://www.ted.com/talks/hans_rosling_at_state), the bubble chart shows 142 countries. The chart shows the life expectancy compared to the GDP per capita for each country. An interactive version of the tool can be found on the [GapMinder website](http://www.gapminder.org/tools/#_chart-type=bubbles).

This chart is interactive:

![Lab Result](img/p3_gapminder.gif)

Using dataset at `./data/gapminder.csv` to re-create the GapMinder bubble chart. Here is a snippet of the dataset:

| `country`      |`year`|`population`|`continent` |`lifeExp`|`gdpPercap`  |
|----------------|------|------------|------------|---------|-------------|
| Afghanistan    | 2002 | 25268405   | Asia       | 42.129  | 726.7340548 |
| Afghanistan    | 2007 | 31889923   | Asia       | 43.828  | 974.5803384 |
| United Kingdom | 1977 | 56179000   | Europe     | 72.76   | 17428.74846 |
| United Kingdom | 1982 | 56339704   | Europe     | 74.04   | 18232.42452 |
| Madagascar     | 2002 | 16473477   | Africa     | 57.286  | 894.6370822 |
| Madagascar     | 2007 | 19167654   | Africa     | 59.443  | 894.6370822 |

* `country` (`string`) - the name of the country
* `year` (`number`) - the year for that recording, spans from 1952 to 2007 in **5-year intervals**
* `population` (`number`) - the total population for that year
* `lifeExp` (`number`) - the mean life expectancy for that year
* `gdpPercap` (`number`) - the income per person, or GDP per capita in USD adjusted for inflation for that year

![Lab Result](img/p3_gapminder_image.jpeg)

The data-bindings on the bubbles are:
* x-positon - `gdpPercap` in a `scaleLog`
* y-positon - `lifeExp` in a `scaleLinear`
* radius - `population` in a `scaleSqrt`
* fill color - `continent` (we have provided the color map as `contintentColors`)

First, you will need to group or nest the dataset by the `year` data attribute. This data re-configuration is slightly different - you want to access all 142 countries for each year so making a key-value array with `d3.nest().entries()` might not be the best method.

This interactive chart uses D3's Enter, Update, Exit pattern.

