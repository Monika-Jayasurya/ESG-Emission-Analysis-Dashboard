# 🌍 ESG & Emissions Analytics Dashboard  

### 📘 Project Overview  
The **ESG & Emissions Analytics System** is designed to help organizations accurately **measure, track, and visualize greenhouse gas (GHG) emissions** across all facilities and supply chain operations.  
It enables decision-makers to identify trends, monitor carbon offsets, and align sustainability goals with global ESG standards.  

---

### 🎯 Project Goals  
- Accurately capture GHG emissions data (Scopes 1, 2, and 3) across **8 cities** and **4 countries**.  
- Monitor **carbon offset** efforts and **net emissions** performance.  
- Enable decision-makers to take corrective actions and communicate ESG impact with stakeholders.  

---

### 🗂️ Dataset Description  
This dataset represents **monthly sustainability activity and emission data (2020–2025)** for a single company operating in **Cameroon, USA, India, and Germany**.  

| Column | Description |
|--------|--------------|
| Electricity_Consumption_kWh | Monthly electricity use in kWh → for Scope 2 |
| Gasoline_Used_L | Liters of fuel consumed → for Scope 1 |
| Materials_Sourced_Tons | Volume of raw materials procured |
| Transportation_Mode | Truck / Rail / Ship / Air |
| Transportation_Distance_km | Distance traveled for logistics |
| Carbon_Offsets_Purchased_tCO2e | Carbon offsets purchased |
| Scope 1, 2, 3 Emissions | Direct, indirect, and value-chain emissions |
| Total Emission (tCO₂e) | Combined Scopes 1 + 2 + 3 |
| Net Emission (tCO₂e) | Total Emission – Offsets |
| Sustainability Goal | “Carbon Neutral” or “Needs Improvement” |

---

### ⚙️ Excel Calculations  

#### **Scope 1 – Direct Emissions**  
Represents direct emissions from **fuel combustion** within company assets.  
Formula:  


⚙️ Calculations Used in Excel
1️⃣ Scope 1 – Direct Emissions

Formula:

Scope 1 (tCO₂e) = Gasoline_Used_L × 2.31 / 1000


Example:
= 366 × 2.31 ÷ 1000 = 0.85 tCO₂e

Emission Factor Source:
EPA | IEA | IPCC Guidelines

2️⃣ Scope 2 – Indirect Emissions (Electricity)

Formula:

Scope 2 (tCO₂e) = Electricity_Consumption_kWh × 0.45 / 1000


Example:
= 4155 × 0.45 ÷ 1000 = 1.87 tCO₂e

0.45 represents the average global grid emission factor (kg CO₂/kWh).

3️⃣ Scope 3 – Value Chain Emissions

Formula:

=IF(G2="Truck",0.15*F2*H2/1000,
IF(G2="Ship",0.02*F2*H2/1000,
IF(G2="Rail",0.03*F2*H2/1000,
IF(G2="Air",0.6*F2*H2/1000))))

Mode	Emission Factor (kg CO₂e/ton-km)
Truck	0.15
Ship	0.02
Rail	0.03
Air	0.60
4️⃣ Total and Net Emissions

Formulas:

Total Emission = Scope 1 + Scope 2 + Scope 3
Net Emission = Total Emission – Carbon Offsets Purchased

5️⃣ Sustainability Goal Logic
=IF(N2<=0,"Carbon Neutral (YES)","Work on broader carbon management strategy (NO)")


✅ If net emissions ≤ 0 → Carbon Neutral
❌ Else → Needs improvement

📊 Dashboard KPIs
KPI	Description / Insight
- Net Emission Rate	Cameroon recorded the highest (27.1 tCO₂e)
- Emissions by Transport Mode	Air > Truck > Rail > Ship
- Top Emitters by Mode	Air – Cameroon, Truck – India, Rail – Germany, Ship – USA
- Offset vs Emissions (2022–2023)	Carbon offsets exceeded emissions → Carbon-positive performance
- Yearly Trend	Sharp drop in 2022 (9 → -17 tCO₂e) likely due to COVID-related operational slowdown

🧮 Key Excel / BI Techniques Used
- Cleaning & Validation: Excel Power Query, conditional formulas
- Emission Calculations: IF statements, fixed factors, unit conversions
- Visualization: Power BI / Looker Studio dashboards
- Automation: Monthly form submission → Google Sheets sync → Live BI update

Dashboard

![Dashboard Screenshot](https://github.com/user-attachments/assets/6d3fc425-af49-4874-ba3c-f0a7f4526e70)


🧠 Key Insights

- Cameroon recorded the highest residual emissions, requiring targeted reduction strategies.
- Air transport contributed the most to total emissions — potential area for offset or route optimization.
- 2022–2023 show strong performance due to offset purchases exceeding emissions.
- Achieved average net zero across all facilities, but continuous monitoring needed for non-neutral locations.

🏁 Conclusion

This project demonstrates a complete ESG data lifecycle — from data collection and emission computation to dashboard visualization.
It showcases how analytics can help organizations:
- Identify carbon hotspots
-  Track sustainability progress
-  Communicate impact transparently

