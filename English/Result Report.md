📑 [Analysis Result Report]

1. Title

The Impact of Foreign Trading Trends and the Dollar Index on the Dollar Exchange Rate

2. Summary

Purpose: To analyze the impact of foreigners' domestic stock trading trends and the dollar index on the dollar exchange rate, and to determine if there are actual exchange rate movements that do not align with the recent dollar index.

Method: Analyze 10 years of data starting from 2015 using Python, and separately analyze 1 year of data for mutual comparison.

Conclusion: The dollar exchange rate generally has a clear positive correlation with the dollar index, but a conditional correlation exists with foreign trading trends.

3-1. Data Preparation

(1) Foreign Trading Trend Data (foreign invest)

Period: 2015.11.26. ~ 2025. 11. 25.

Source: KRX Information Data System (https://data.krx.co.kr/contents/MDC/MDI/mdiLoader/index.cmd?menuId=MDC0201020301)

Preprocessing: Merged 5 files of 2-year data using queries and kept only the foreign net buying amount information, scaled by 1 billion units.

(2) Dollar Index Data (dollar index)

Period: 2015.11.26. ~ 2025. 11. 25.

Source: Investing.com Dollar Index (DXY) (https://kr.investing.com/indices/usdollar-historical-data?cid=1224074)

Preprocessing: Kept only the daily dollar index data and removed the rest.

(3) Dollar Exchange Rate Data (dollar rate)

Period: 2015.11.26. ~ 2025. 11. 25.

Source: Woori Bank Forex Center (https://spot.wooribank.com/pot/Dream?withyou=FXXRT0014)

Preprocessing: Crawled only the date and the basic exchange rate. Converted the date from string to date format, and the basic exchange rate to a float type by removing the ',' separator for thousands.

(4) Total Integrated Data

Preprocessing: Determined the analysis target based on dates overlapping in all three datasets and merged them by deleting the remaining data.

4-1. Analysis Process

<img src="./img/visual1-1.png">
<center>10-Year Data</center>

<img src="./img/visual1-2.png">
<center>1-Year Data</center>

The volatility of the foreign trading trend data was too severe, so the data was refined by dividing by 100 and then adding 100. Since the direction was still difficult to determine due to volatility, a 30-day trend line was added for the 10-year data, and a 10-day trend line for the 1-year data. The faintest graph on each plot is the refined foreign trading trend data, and the line with the index 'Foreign Invest' is the trend line.

5-1. Key Findings

Relationship between Dollar Exchange Rate and Dollar Index
The basic direction is almost identical. However, a decoupling phenomenon where the gap widens has been observed since 2022. Therefore, while basic exchange rate fluctuations can be explained by the dollar index, it can be judged that the recent sharp rise in exchange rates and high volatility are influenced by complex factors such as government policies, foreign exchange defense by financial authorities, international situations, and the widening interest rate gap between Korea and the US.

Relationship between Dollar Exchange Rate and Foreign Trading Trends
They do not basically match. In other words, it is difficult to see a distinct correlation. In the 1-year data, they seem to match to some extent when volatility is low, but this is not the case when viewed with 10-year data. Therefore, it cannot be explained uniformly.

For a more detailed analysis of the causes of recent exchange rate fluctuations, it is judged that analyzing the movements during the 2008 financial crisis would be helpful. During the martial law declaration on December 3, 2024, financial authorities lowered the exchange rate, which had soared to over 1480 won, to 1360 won through direct intervention, and are still working on stabilizing the exchange rate in cooperation with the National Pension Service. During the Lehman Brothers crisis, the sharp rise in the exchange rate was also a major issue, and the government at the time worked to stabilize the exchange rate by signing an unlimited currency swap with the US. Of course, the Lehman Brothers crisis is a case of a financial crisis, so it is difficult to explain the current state, which is a mix of the beginning of a global recession and financial instability due to bad debts, but it is considered to be a useful reference to some extent.

3-2. Data Preparation

(1) Dollar Index Variation Data (dollar index)

Preprocessing: Kept only the daily dollar index variation % data from the same source and removed the rest. Scaled the variation % data by multiplying by 1,000.

(2) Dollar Exchange Rate Variation Data (dollar rate)

Preprocessing: Crawled only the date and the KRW/USD exchange rate variation from the same site. Converted the date from string to date format, and set the variation to 0 for days with no change to construct the data.

(3) Total Integrated Data

Preprocessing: Determined the analysis target based on dates overlapping in all three datasets and merged them by deleting the remaining data.

4-2. Analysis Process

<img src="./img/visual2-1.png">
<center>10-Year Data</center>

<img src="./img/visual2-2.png">
<center>1-Year Data</center>

All 10-year graphs were made with 120-day moving averages, and the 1-year graphs below were made with 30-day moving averages.

5-2. Key Findings

This is the conclusion on the correlation between Dollar Index, Foreign Net Buying, and KRW/USD Exchange Rate.

In the second analysis conducted with the variations of each data rather than the simple trend analysis in the first visualization, the impact of foreign trading trends on the KRW/USD exchange rate can be confirmed more clearly. Although not perfect, it can be judged that foreign trading trends have a negative influence on the KRW/USD exchange rate, so it can be said to be a significant variable determining the direction of the dollar exchange rate.

Applying the conclusion of the first visualization, beyond the basic positive correlation where the KRW/USD exchange rate is subordinate to the dollar index, and based on the assumption that the KRW/USD exchange rate and foreign net buying would show a negative correlation, focus was placed on the abnormal phenomenon where the KRW/USD exchange rate ignored the direction of the dollar index and showed a positive correlation with foreign net buying. This occurred in mid-2017 and mid-2019, respectively.

This phenomenon is not common, and there are two main causes.
First, apart from the strength of the dollar itself, the weakness of the won occurred due to internal problems in Korea. Second, the outflow of domestic investment capital overseas was greater than the net buying of domestic stocks by foreigners.

As a result of the investigation, in 2017, a semiconductor super cycle occurred led by Samsung Electronics, leading to strong foreign buying, but the won weakened due to security issues called North Korea's provocation. In 2019, as the US-China trade conflict intensified, there were concerns about an economic recession in Korea, which has a large export volume to China, and Japan's export restriction policy against Korea caused problems in the supply of semiconductor materials, fueling these concerns and triggering a strong weakness of the won.

These causes cannot be seen as related to foreign net buying, and are merely temporary coincidences caused by the won's own problems. Such exceptional phenomena cannot negate the hypothesis that foreign net buying has a negative correlation with the KRW/USD exchange rate.

However, to say that foreign net buying has a negative correlation with the KRW/USD exchange rate, foreign net buying and the dollar index must be in an inverse relationship. Since the KRW/USD exchange rate basically follows the dollar index, it should be noted that if the dollar index moves in the same direction as foreign net buying (when the dollar is strong and foreigners also buy stocks), the influence of foreign supply and demand on the exchange rate may be offset or diluted.

Additionally, in the process of analyzing the impact of foreign net buying on the dollar exchange rate, a question arose as to whether there is a time lag correlation, so I intend to generate additional graphs below for analysis.

4-3. Analysis Process

<img src="./img/visual2-3.png">
<center>10-Year Data</center>

<img src="./img/visual2-4.png">
<center>1-Year Data</center>

The 10-year foreign net buying graph was shifted 80 days to the right to match other graphs to some extent.
The 1-year foreign net buying graph was shifted 20 days to the right.

5-3. Key Findings

Analyzed the impact of foreign net buying on the KRW/USD exchange rate with a time lag.

This is because I thought that foreign selling and buying of Korean stocks does not necessarily lead to immediate exchange from Won to Dollar, so foreign trading trends cannot be said to necessarily affect the KRW/USD exchange rate.

The graphs with time lags also basically show a negative correlation with the KRW/USD exchange rate well, but it is difficult to identify a differentiation from the graphs without time lags.

Therefore, rather than viewing foreign net buying as affecting the KRW/USD exchange rate with a time lag, considering that judgment is similarly possible with 80-day and 20-day lags respectively compared to graphs without lags, it is considered correct to judge that the impact of foreign net buying on the KRW/USD exchange rate has a tendency.

6. Limitations and Areas for Improvement

Although dollar exchange rate data was crawled for crawling practice, it seems that using FinanceDataReader (https://wikidocs.net/172650) would largely prevent data-related problems in financial data analysis.

In this analysis, only the total foreign investment trend data was used, but it is expected to be meaningful to separately analyze the trend of the semiconductor sector, which has a high proportion in the domestic stock market, in the future.

7. Final Conclusion

If the dollar index determines the 'direction' of the exchange rate, the money bags of foreign big hands change the 'destiny' of the exchange rate.