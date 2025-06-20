# 📊 Bank Marketing Campaign – Data Cleaning Project

This project involves cleaning and restructuring raw marketing campaign data from a bank, originally provided in `bank_marketing.csv`. The cleaned and transformed output is separated into three final CSV files prepared for PostgreSQL database integration: `client.csv`, `campaign.csv`, and `economics.csv`.

---

## 🣼 Objective

* Transform raw marketing data into structured, normalized tables.
* Ensure data types and formats are consistent for seamless PostgreSQL insertion.
* Facilitate future campaign data integration.

---

## 📁 Input File

* `bank_marketing.csv`

---

## 📄 Output Files & Structure

### `client.csv`

| Column           | Type    | Description       | Cleaning                                        |
| ---------------- | ------- | ----------------- | ----------------------------------------------- |
| `client_id`      | integer | Client ID         | N/A                                             |
| `age`            | integer | Age               | N/A                                             |
| `job`            | object  | Job type          | Replace `.` with `_`                            |
| `marital`        | object  | Marital status    | N/A                                             |
| `education`      | object  | Education level   | Replace `.` with `_`, change `unknown` to `NaN` |
| `credit_default` | bool    | Credit in default | `1` if "yes", else `0`                          |
| `mortgage`       | bool    | Has mortgage      | `1` if "yes", else `0`                          |

---

### `campaign.csv`

| Column                       | Type     | Description                     | Cleaning                                                  |
| ---------------------------- | -------- | ------------------------------- | --------------------------------------------------------- |
| `client_id`                  | integer  | Client ID                       | N/A                                                       |
| `number_contacts`            | integer  | Campaign contact count          | N/A                                                       |
| `contact_duration`           | integer  | Last contact duration (seconds) | N/A                                                       |
| `previous_campaign_contacts` | integer  | Prior campaign contacts         | N/A                                                       |
| `previous_outcome`           | bool     | Outcome of previous campaign    | `1` if "success", else `0`                                |
| `campaign_outcome`           | bool     | Current campaign outcome        | `1` if "yes", else `0`                                    |
| `last_contact_date`          | datetime | Date of last contact            | Combine `day`, `month`, and `year = 2022` as `YYYY-MM-DD` |

---

### `economics.csv`

| Column                 | Type    | Description          | Cleaning |
| ---------------------- | ------- | -------------------- | -------- |
| `client_id`            | integer | Client ID            | N/A      |
| `cons_price_idx`       | float   | Consumer Price Index | N/A      |
| `euribor_three_months` | float   | 3-month Euribor rate | N/A      |

---

## 🚀 How to Use

1. Run the provided cleaning script in Python (Jupyter Notebook or standalone script).
2. Verify outputs:

   * `client.csv`
   * `campaign.csv`
   * `economics.csv`
3. Import into PostgreSQL with your ETL pipeline.

---

## 📦 Requirements

* Python 3.x
* pandas
* numpy

```bash
pip install pandas numpy
```

---

## 🔗 Resources

* [Project Documentation](https://documenter.getpostman.com/view/27221035/2sB2x2LEfa)

---

## 🏁 Status

👌 Completed and validated. Ready for database import.
