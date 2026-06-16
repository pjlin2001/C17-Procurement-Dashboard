# C-17 Procurement Cost Dashboard

An interactive [Dash](https://dash.plotly.com/) dashboard for analyzing C-17
procurement costs. It loads purchase-order history and supplier pivot data,
then renders interactive visualizations of cost trends, distributions, and
supplier contributions.

## Features

- **Unit Cost Trends** — scatter plot of unit cost across PO entries
- **Histogram of Unit Costs** — distribution of unit costs
- **Boxplot of Unit Costs** — distribution with IQR-based outlier clipping
- **Part Number vs Unit Cost** — scatter plot with escalation factor on hover
- **Supplier Cost Contribution** — bar chart filterable by supplier(s)

## Data

The dashboard expects two Excel workbooks:

| File | Sheet used | Columns expected |
|------|-----------|------------------|
| PO History | `ROR PO History` | `Part Number`, `Unit Cost`, `Esc Value` |
| Supplier Pivot | `Supplier Pivot` | `Supplier Name`, `Sum of Total Cost` |

> **Note:** Data files are **not** included in this repository and are excluded
> via `.gitignore`. Update the file paths near the top of the notebook to point
> to your local copies before running.

## Setup

```bash
pip install -r requirements.txt
```

## Usage

Open the notebook and update these paths to your local files:

```python
po_history_path = "path/to/PO_History.xlsx"
supplier_pivot_path = "path/to/Supplier_Pivot.xlsx"
```

Run all cells. The Dash app starts a local server:

http://127.0.0.1:8050

## Built With

- pandas
- plotly
- dash
- scipy / numpy
