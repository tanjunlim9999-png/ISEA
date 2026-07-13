# TCO (Total Cost of Ownership) Analysis  

## TCO Definition  

Total Cost of Ownership (TCO) is a financial metric used to calculate the complete cost of an asset over its entire life cycle. Instead of just looking at the initial purchase price, TCO factors in all hidden, indirect, and ongoing costs that occur after the purchase is made. TCO is typically broken down into two main categories:   
* Fixed Costs (Upfront CapEx): The initial, one-time expenses required to acquire the asset. Using a printer as an example, this includes the purchase price of the hardware and any necessary accessories or initial installation.   
* Variable Costs (Ongoing OpEx): The continuous expenses incurred through regular operation, maintenance, and consumption over time. For a printer, this includes ink/toner cartridges, reams of paper, electricity usage, and potential repair costs.   
In IT procurement, calculating TCO is essential because it prevents organizations from making the mistake of buying a "cheap" asset that ends up being incredibly expensive to operate in the long run.

## Lab Instructions

This Lab introduce the concept of TCO using printers as a scenario  

Choose two printer to compare  

## Printer A  
Printer A : HP DeskJet 2932 All-in-One Printer  
Price : $79 SGD  

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7e917e78-ca64-414b-a0b0-85d74bbcbcdf" />  

Ink catridge used : HP 68 Black Original Ink Catridge (7FP21TA) – price : 37.90 SGD  
Catridge yield – 160 pages  

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/aa603887-86d1-42d7-a36f-6e3bf849593f" />  

Power consumption : est 10 watts  


## Printer B  

Printer B : HP LaserJet Enterprise M507dn  
Price : $879 SGD  

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f5fd368a-91d6-438e-a97b-9a47e2a7ad81" />  

Ink catridge used : HP 89X High Yield Black Toner (CF289X) – price : $372.15 SGD  
Catridge yield – 10,000 pages  

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/9e339cf0-47c6-4c91-be49-d0e7bb52704c" />  

Power consumption: est 40 watts of continuous power  


## Potential Costs for both printers  

Assumptions  
Total printing volume : 750 pages/week x 260 weeks = 195000 pages  
Total run time : 40 hours / week x 260 weeks = 10,400 hours  
Paper cost : $4.60 per ream (500 pages) – Same for both printers  
<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7c46addc-1bdc-4495-b70e-046b6db52596" />  
Electricity Rate : $0.3478 per kWh (34.78 cents)  
<img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/40dc88ba-ed33-4ca6-a1a0-a12ea5475451" />  

For Printer A : HP DeskJet 2932 All-in-One Printer  

1.	Hardware price = $79.00  

2.	Paper cost:  
-	750 pages/week = 195,000 in total pages  
-	195,000 pages  / 500(per ream) = 390 ream  
-	390 ream x $4.60 SGD = $1,794.00SGD  

3.	Ink cost:  
-	195,000 pages / 160 pages per ink catridge = 1,218.75 catridges  
-	1,218.75 catridges x $37.90SGD = $46,190.63.00SGD  

4.	Power cost:  
-	10W x 10,400 hours = 104,000 Wh = 104 kWh.  
-	104 kWh x $0.3478 SGD = $36.17

  Grand Total :   

  <img width="1100" height="250" alt="image" src="https://github.com/user-attachments/assets/410b4aed-ae8c-4701-bef7-df361349d598" />  

  TCO, Cost per page = 48,100.80 / 195,000 = $0.247 per page  


  For Printer B : HP LaserJet Enterprise M507dn   

1.	Hardware price = $879.00
   
2.	Paper cost =   
-	750 pages/week = 195,000 in total pages  
-	195,000 pages  / 500(per ream) = 390 ream  
-	390 ream x $4.60 SGD = $1,794.00SGD
  
3.	Ink cost =  
-	195,000 pages / 10,000 pages per ink catridge = 19.5 catridges  
-	19.5 catridges x $372.15SGD = $7,256.93SGD
  
4.	Power cost =  
-	40W x 10,400 hours = 416,000 Wh = 416 kWh.  
-	416 kWh x $0.3478 SGD = $144.68 SGD

  Grand Total :  

  <img width="1100" height="250" alt="image" src="https://github.com/user-attachments/assets/0fd76389-f67c-46ad-b7a0-37517f534cd3" />  

  TCO, Cost per page = 10,074.61 / 195,000 = $0.052 per page  

  
## Spreadsheet Components  

Printer A = HP DeskJet 2932 All-in-One Printer   

<img width="1350" height="400" alt="image" src="https://github.com/user-attachments/assets/a7dea3dc-dbf4-42b4-8b23-84f123357d2d" />  

Printer B = HP LaserJet Enterprise M507dn   

<img width="1350" height="400" alt="image" src="https://github.com/user-attachments/assets/6748321d-945a-46fa-a259-d0add17bbae3" />  


## Relection Questions  

•	Based on the TCO, which printer is the most cost-effective over 5 years?  
Printer B (HP LaserJet Enterprise M507dn) has a drastically lower TCO ($10,074.61) compared to Printer A (HP DeskJet 2932) ($48,100.80) over the 5-year period.
While the Inkjet printer has a deceptively low upfront hardware cost ($79.00 vs. $879.00), its microscopic ink cartridge yield (160 pages) creates a massive financial burden at high volumes. Churning through 750 pages a week forces the purchase of over 1,200 ink cartridges, inflating variable costs to an unsustainable degree. Conversely, the Laser printer's high-yield toner (10,000 pages) minimizes long-term operational costs, demonstrating the classic "razor-and-blades" business model where high upfront capital expenditure (CapEx) yields massive operational savings (OpEx).  

•	Would the answer change for a home user who prints only 5 pages per week?  
Yes, the choice would completely reverse. If the volume drops to 5 pages per week, the total volume over 5 years becomes only 1,300 pages (5 pages × 260 weeks).
Inkjet TCO at low volume: ~$399.00 (requiring only ~8 ink cartridges over 5 years). Laser TCO at low volume: ~$940.00 (the printer itself costs $879.00 upfront).
At this minimal utilization level, the enterprise laser printer would never recoup its high initial purchase price, making the budget inkjet the mathematically superior choice for a light home user.  

•	What other non-financial factors could influence printer selection?  
-	Print Speed (Pages Per Minute): The enterprise laser prints at up to 45 pages per minute (ppm), whereas the entry-level inkjet operates at a sluggish fraction of that speed. In an office setting, slow print speeds cause employee bottlenecks and lost productivity.  
-	Reliability and Duty Cycle: Enterprise printers are engineered to handle tens of thousands of pages monthly without mechanical degradation. A consumer inkjet pushed to 750 pages a week would suffer premature hardware failure, leading to frequent downtime.  
-	Maintenance and Support: Enterprise hardware usually includes commercial warranties, on-site servicing options, and easily swappable parts (like pick rollers and fusers), whereas cheap consumer inkjets are essentially disposable if they break.  

•	What cost components are more significant for a large workgroup printer?  
-	Consumable Page Yield: Prioritizing ultra-high-capacity toner options (e.g., cartridges yielding 20,000+ pages) to drive the per-page cost as close to zero as possible.  
-	Maximum Monthly Duty Cycle: Ensuring the machine's robust build quality can easily sustain the team's workload without physical wear.  
-	Energy-Efficient Sleep States: Seeking low-wattage deep sleep configurations to mitigate electricity costs during idle nighttime and weekend hours.  


•	At what point (in years/pages) do the two printer options break even in cost?  
The break-even point occurs at approximately 4,018 pages printed. Mathematically, the extreme difference in cartridge running costs ($0.237 per page for the inkjet vs. $0.037 per page for the laser) allows the enterprise laser to offset its $800 price premium incredibly fast. At the lab's assumed workload of 750 pages per week, the break-even point is reached in 5.4 weeks (just a little over one month of active deployment). Past this point, every single page printed on the inkjet represents a direct financial loss compared to the laser workhorse.  














