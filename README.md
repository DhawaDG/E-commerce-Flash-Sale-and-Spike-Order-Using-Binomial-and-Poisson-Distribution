# E-commerce Flash Sale and Spike Order Analysis Using Binomial and Poisson Distribution

## Introduction

This project analyzes e-commerce flash sales and order spikes using statistical distributions. It demonstrates how to detect flash sales and order spikes using binomial and Poisson models.

### Flash Sale and Order Spike Definition

- **Flash Sale:** A short-term promotion offering significant discounts, leading to a sudden surge in visitors and orders.
- **Order Spike:** A rapid, temporary increase in order volume, often during flash sales or special events.

---

## Content

### 1. Data Generation

- Two synthetic datasets are generated:
    - **flash_sale_daily_data.csv**  
        Columns: `date`, `day_of_week`, `is_weekend`, `is_flash_sale`, `visitors`, `customers`, `conversion_rate`, `orders`, `orders_per_customer`, `aov`, `revenue`
    - **flash_sale_hourly_data.csv**  
        Columns: `date`, `hour`, `is_flash_sale_hour`, `visitors`, `customers`, `conversion_rate`, `orders`, `orders_per_customer`

---

### 2. Data Cleaning and EDA

- Checked column names, shape, and size.
- Performed descriptive statistics.
- Checked for missing values and duplicates.
- Plotted data distributions.
- Saved cleaned datasets.

---

### 3. Finding Flash Sale Using Binomial Distribution

- Identified columns for:
    - `k`: desired events (orders)
    - `n`: number of trials (visitors)
    - `p`: probability of success (conversion rate)
- Calculated global conversion rate.
- Detected flash sales using:
    - Binomial PMF
    - Binomial CDF (`p_right_tail`)
    - Z-score method (mean and variance)
- **Conclusion:** Binomial CDF is the most statistically valid method for determining flash sales.

> **Export PDF:** [PREVIEW PDF](PDF/Flashsale.pdf)

---

### 4. Finding Order Spike Using Poisson Distributions

- Identified lambda (average order rate).
- Checked for overdispersion and mixture models.
- Used:
    - Poisson PMF
    - Poisson CDF
    - Z-score method
    - Poisson GLM model and ABS threshold method
    - Negative Binomial Distribution (GLM Negative Binomial and ZINB)
- **Conclusion:** Deploy ZINB as the standard approach for count data analysis in production, especially with overdispersion and structural zeros.

> **Export PDF:** See [PREVIEW PDF](PDF/orderspike.pdf)
