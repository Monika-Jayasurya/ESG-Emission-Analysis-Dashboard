🌍 ESG & Emissions Analytics Dashboard
📘 Project Overview

This project simulates a real-world ESG (Environmental, Social, and Governance) data reporting system designed to track and communicate greenhouse gas (GHG) emissions across multiple facilities and supply chain operations.

It enables organizations to:
✅ Measure Scope 1, 2, and 3 emissions accurately.
✅ Monitor carbon offset efforts and net emissions.
✅ Visualize ESG performance across countries and transportation modes.

🎯 Project Goals

Capture GHG emissions across 8 cities and 4 countries (Cameroon, USA, India, Germany).

Monitor offset purchases and net emission trends.

Enable data-driven sustainability reporting via dashboards.

Support decision-making for mission reduction strategies.

🧩 Data Description
Column Name	Description
Electricity_Consumption_kWh	Monthly electricity use (kWh) → used to calculate Scope 2 emissions
Gasoline_Used_L	Liters of fuel consumed → used for Scope 1 emissions
Materials_Sourced_Tons	Total materials sourced (in tons)
Transportation_Mode	Mode of transport (Truck / Rail / Ship / Air)
Transportation_Distance_km	Distance covered for material transport
Carbon_Offsets_Purchased_tCO2e	Total offsets purchased (in tonnes of CO₂e)
Scope 1 Emission (tCO₂e)	Direct emissions from company operations
Scope 2 Emission (tCO₂e)	Indirect emissions from electricity
Scope 3 Emission (tCO₂e)	Supply chain emissions (based on transport)
Total Emission (tCO₂e)	Sum of Scope 1 + Scope 2 + Scope 3
Net Emission (tCO₂e)	Total Emission – Offsets
Sustainability Goal	"Carbon Neutral (YES)" or "Work on broader carbon management strategy (NO)"
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
Net Emission Rate	Cameroon recorded the highest (27.1 tCO₂e)
Emissions by Transport Mode	Air > Truck > Rail > Ship
Top Emitters by Mode	Air – Cameroon, Truck – India, Rail – Germany, Ship – USA
Offset vs Emissions (2022–2023)	Carbon offsets exceeded emissions → Carbon-positive performance
Yearly Trend	Sharp drop in 2022 (9 → -17 tCO₂e) likely due to COVID-related operational slowdown

🧮 Key Excel / BI Techniques Used
Data Cleaning & Validation: Excel Power Query, conditional formulas
Emission Calculations: IF statements, fixed factors, unit conversions
Visualization: Power BI / Looker Studio dashboards
Automation: Monthly form submission → Google Sheets sync → Live BI update

Dashboard

![Dashboard Screenshot](https://github.com/user-attachments/assets/6d3fc425-af49-4874-ba3c-f0a7f4526e70)


🧠 Key Insights

Cameroon recorded the highest residual emissions, requiring targeted reduction strategies.
Air transport contributed the most to total emissions — potential area for offset or route optimization.
2022–2023 show strong performance due to offset purchases exceeding emissions.
Achieved average net zero across all facilities, but continuous monitoring needed for non-neutral locations.

🏁 Conclusion

This project demonstrates a complete ESG data lifecycle — from data collection and emission computation to dashboard visualization.
It showcases how analytics can help organizations:
✅ Identify carbon hotspots
✅ Track sustainability progress
✅ Communicate impact transparently

