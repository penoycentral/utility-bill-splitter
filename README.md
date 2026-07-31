# 🇸🇬 Singapore Co-Living Utility & PUB Bill Splitter

A styled, automated Excel spreadsheet template designed for flatmates, tenants, and co-living spaces in Singapore to distribute joint household bills (PUB, Internet, cleaner fees, aircon servicing) fairly, based on the exact number of days each person is present.

This workbook is **100% compatible with Google Sheets** and is pre-configured with a year's worth of monthly sheets containing built-in calculators, dropdown configurations, and daily trackers.

---

## 🚀 Key Features

*   **📅 Date-Driven Billing Cycles**: Fully dynamic headers using the **`DD-MM-YYYY`** date format (e.g., `01-07-2026` to `31-07-2026`). Enter any custom billing cycle start and end dates (e.g., matching your SP Services bill cycle). Non-active day columns automatically gray out and lock (e.g., February 29th–31st).
*   **💧 PUB Daily Cost-Share**: Rather than splitting bills flatly, PUB is divided by month days, then by occupants, and allocated based on daily presence. Absent days are omitted, ensuring you only pay for days you were in the house.
*   **🌐 Internet Splitting**: Hardcoded to allow cost-sharing specifically for a set number of occupants (e.g., split equally only among the first 3 tenants on the lease).
*   **🛠️ Custom Utility Slots**: Two extra columns (`Custom 1`, `Custom 2`) to allocate variable fees like cleaner visits, aircon gas refilling, or shared household supplies.
*   **📊 Integrated Daily Tracker**: Section 3 features an occupancy tracker where you simply enter **`1`** for each day an occupant is present (leave blank or enter `0` if absent). It automatically calculates days present and updates utility bill allocations in real time.
*   **📅 Full-Year Templates**: Includes 12 pre-configured sheets starting from `Jul-2026` to `Jun-2027`.

---

## 🎨 Visual Layout & Styles

The sheet follows a clean, professional **Steel Blue** theme, utilizing clear visual cues:
*   🟢 **Light Green Cells (`#E2EFDA`)**: Editable Inputs. You can safely type dates (`DD-MM-YYYY`), tenant names, bill totals, split methods, and daily attendance (`1` for present) here.
*   🔵 **Ice Blue Cells (`#DDEBF7`)**: Automated Formulas. These contain calculations and should not be edited.
*   ⚪ **Zebra Striping**: Alternating row colors to read roommate shares easily.
*   🔘 **Inactive Gray Columns (`#F2F2F2`)**: Days that fall outside the current billing start/end date range are automatically muted and visually disabled.

---

## ⚙️ Core Splitting Logic & Formulas

### 1. PUB Cost Share
By default, the PUB column uses the **`By Days Present`** split method. The share for occupant $i$ is calculated day-by-day:
$$\text{Daily Share}_d = \frac{\text{Total PUB Bill}}{\text{Billing Period Days} \times \text{Occupants Present on Day } d}$$
$$\text{Occupant Share} = \sum_{d=1}^{N} (\text{Presence}_d \times \text{Daily Share}_d)$$

> [!NOTE]
> If a tenant is away on holiday for 10 days, they do not pay for PUB on those 10 days. The vacancy cost for those empty-room days is not forced onto the remaining roommates. The **Reconciliation Status** in cell `C25` will display `❌ Unbalanced` to indicate the unallocated vacancy cost, which can be absorbed by the landlord or distributed manually.

### 2. Internet cost split
Defaulted to **`Split (Top 3)`**, which divides the internet bill by 3 and charges only the first 3 occupants listed in rows 13–15. Occupants from row 4 onwards pay `$0.00`.

### 3. General split methods (Custom 1 & 2)
Choose from three calculations in Row 9:
1.  **By Days Present**: Proportional daily allocation based on days in the house.
2.  **Split Equally**: Cost is divided evenly among all listed roommates.
3.  **Split (Top 3)**: Cost is divided by 3 and charged only to the first 3 roommates.

---

## 📝 Step-by-Step Guide

### 1. Open the File
You can use Microsoft Excel, Apple Numbers, or import it into **Google Sheets** (recommended for room rentals):
*   Upload [`utility_bill_calculator.xlsx`](./utility_bill_calculator.xlsx) to Google Drive.
*   Double-click to open in Sheets, and select **File** > **Save as Google Sheets**.
*   Share the link with your housemates.

### 2. Configure the Month
1.  Navigate to the sheet for the current month (e.g., `Jul-2026`).
2.  Enter your SP Services (PUB) billing start and end dates in cells `B4` and `D4` using the **`DD-MM-YYYY`** format (e.g., `01-07-2026` and `31-07-2026`). The daily tracker dates will adjust automatically.
3.  Type roommate names in the green column `A13:A22`. They will automatically mirror in the tracker below.
4.  Enter the monthly utility bills in the green cells `C8:F8`.
5.  Set your split methods in the dropdowns in row 9.

### 3. Log Roommate Attendance
*   Scroll down to **3. DAILY OCCUPANCY TRACKER**.
*   Simply enter **`1`** in the green day column for each day an occupant is present in the house. Leave blank or enter **`0`** if they were away (e.g., on home leave or staycation).
*   Total days present, daily PUB cost-share, and individual bill shares will update automatically in real time!


---

## 📁 Repository Files

*   [`utility_bill_calculator.xlsx`](./utility_bill_calculator.xlsx): The ready-to-use full-year Excel spreadsheet workbook.



---

## ⚠️ Disclaimer

This template and script are provided "as is" without warranty of any kind. **Use at your own risk.** Users are responsible for verifying calculations and utility figures prior to making financial payments or settlements.

