
# Lab 2a: Total Cost of Ownership (TCO)

## 2. Lab Objectives

The objectives of this lab were to:

- Understand the concept of Total Cost of Ownership (TCO).
- Compare the purchase and operating costs of two printers.
- Calculate printing requirements over five years.
- Research toner costs, electricity consumption, and maintenance requirements.
- Use Microsoft Excel formulas to calculate TCO.
- Identify the most economical printer based on long-term costs.
- Understand the break-even point between two printers.


## 3. Printers Selected

For this comparison, I selected two monochrome laser printers designed for office environments.

### Printer A: Brother HL-L5210DN

- Monochrome laser printer.
- Automatic double-sided printing.
- High-capacity toner cartridge options.
- Network printing capabilities.

### Printer B: HP LaserJet Pro 4003dn

- Monochrome laser printer.
- Automatic double-sided printing.
- High-yield toner cartridge options.
- Network printing capabilities.

Both printers were selected because they support office printing and can be compared using similar operating requirements.


## 4. Lab Assumptions

The following assumptions were provided for the TCO analysis:

| Description | Value |
|---|---|
| Printing volume per week | 750 pages |
| Powered-on hours per week | 40 hours |
| Weeks per year | 52 |
| Analysis period | 5 years |
| Printing type | Monochrome |

### 4.1 Annual Printing Volume

Annual printing volume was calculated by multiplying weekly printing requirements by the number of weeks in a year.

**Formula:**

750 × 52 = **39,000 pages per year**

### 4.2 Five-Year Printing Volume

39,000 × 5 = **195,000 pages**

Therefore, each printer must support approximately 195,000 printed pages over five years.

### 4.3 Annual Powered-On Hours

40 × 52 = **2,080 hours per year**

### 4.4 Five-Year Powered-On Hours

2,080 × 5 = **10,400 hours**

These calculations provide the foundation for estimating toner consumption, electricity costs, and other operating expenses.

---

## 5. Total Cost of Ownership Calculation

The TCO calculation considers the following expenses:

1. Initial printer purchase price.
2. Toner cartridge replacement costs.
3. Electricity consumption.
4. Maintenance and replacement parts.

**General Formula:**

TCO = Purchase Cost + Consumables Cost + Electricity Cost + Maintenance Cost

### 5.1 Toner Cost Calculation

Toner cost is determined by the cartridge price, page yield, and total printing requirements.

**Formula:**

Cartridges Required = Total Pages / Toner Page Yield

The result must be rounded up because toner cartridges are purchased as complete units.

**Cost Per Page Formula:**

Cost Per Page = Toner Cartridge Price / Toner Page Yield

The calculation should also consider any toner supplied with the printer and additional replacement consumables.

### 5.2 Electricity Cost Calculation

Electricity consumption is calculated using the printer's power consumption and operating hours.

**Formula:**

Energy Consumption (kWh) = Power (Watts) / 1000 × Operating Hours

Electricity Cost = Energy Consumption (kWh) × Electricity Tariff

Where printing and ready-mode power consumption differ, these operating states should be considered separately to improve accuracy.

### 5.3 Maintenance Cost Calculation

Maintenance expenses may include replacement drums, servicing, and other consumable components.

These expenses should be estimated based on the manufacturer's specifications and expected usage.

---

## 6. Microsoft Excel Implementation

Microsoft Excel is used to organise the printer specifications and calculate the five-year TCO.

The spreadsheet includes the following information:

- Printer purchase price.
- Toner cartridge price.
- Toner page yield.
- Annual and five-year printing volume.
- Electricity consumption and tariff.
- Maintenance expenses.
- Total cost over five years.

### Excel Formulas

| Calculation | Excel Formula |
|---|---|
| Annual pages | `=750*52` |
| Five-year pages | `=750*52*5` |
| Annual powered-on hours | `=40*52` |
| Five-year powered-on hours | `=40*52*5` |
| Toner cartridges required | `=ROUNDUP(195000/18000,0)` |
| Toner cost per page | `=324/18000` |

The toner formulas above use example inputs for the Brother printer. The completed spreadsheet will use cell references so the calculations update automatically when input values change.

---

## 7. Five-Year TCO Comparison

The final comparison will be completed after verifying the purchase prices, toner costs, electricity consumption, and maintenance requirements.

| Cost Component | Brother HL-L5210DN | HP LaserJet Pro 4003dn |
|---|---|---|
| Purchase Price | Pending | Pending |
| Five-Year Toner Cost | Pending | Pending |
| Five-Year Electricity Cost | Pending | Pending |
| Five-Year Maintenance Cost | Pending | Pending |
| **Total Five-Year TCO** | **Pending** | **Pending** |

The printer with the lower total cost will be considered the more economical option under the stated assumptions.

---

## 8. Reflection Questions

### Question 1: Based on the TCO, which printer is the best?

The printer with the lowest five-year Total Cost of Ownership would be the better financial choice for an organisation printing 750 pages per week.
Although the initial purchase price is important, ongoing expenses such as toner, electricity, and maintenance significantly affect long-term costs.
The final selection between the Brother HL-L5210DN and HP LaserJet Pro 4003dn will be determined after completing the TCO calculations.

### Question 2: Would your answer be the same for a home user who prints five pages per week?

The answer may differ for a home user printing only five pages per week.
Over five years, the home user would print approximately **1,300 pages**, compared with **195,000 pages** for the organisation.
Since the printing volume is significantly lower, toner consumption would have less impact on the overall TCO.
Therefore, a printer with a lower initial purchase price may be more economical for home use, even if its cost per page is higher.

### Question 3: What other factors could or should we have considered apart from TCO?

Apart from TCO, other important factors include:

- Printing speed.
- Reliability.
- Print quality.
- Security features.
- Network connectivity. (TCP/IP)
- Environmental impact.
- Availability of technical support.

For an organisation, printer downtime could reduce employee productivity.
Therefore, selecting a printer should involve evaluating both financial costs and operational requirements to ensure it meets the organisation's needs.

### Question 4: Knowing something about the cost structure of printers, what would you look for in a large workgroup printer?

For a large workgroup printer, I would prioritise a low cost per page, high-capacity toner cartridges, reliability, and fast printing speeds.
Since the printer would be used frequently by multiple employees, operating expenses could become more significant than the initial purchase price.
I would also consider the recommended monthly print volume, automatic duplex printing, network security, and maintenance requirements to minimise downtime and improve efficiency.

### Question 5: What is the time period where both printers will cost the same?

The break-even point is the time when both printers have the same accumulated total cost.
It can be calculated by comparing their initial purchase prices and annual operating expenses.

**Break-even Formula:**

Break-even Period = (Purchase Price A - Purchase Price B) / (Annual Operating Cost B - Annual Operating Cost A)
This formula assumes constant annual operating expenses and a nonzero difference in annual operating costs.
A printer with a higher purchase price but lower operating costs may become more economical after a certain period.
The exact break-even period will be calculated using the completed Excel spreadsheet.



## 9. Challenges and Learning Experience

One of the challenges in this lab was understanding how different cost components contribute to the overall cost of owning a printer.
Initially, I understood printer costs mainly in terms of the purchase price. However, this exercise introduced me to the importance of considering recurring expenses such as toner replacements, electricity consumption, and maintenance.Another learning challenge was understanding how to convert weekly printing requirements into annual and five-year figures.
I also explored the use of Excel formulas to automate calculations and learned why rounding up toner cartridge quantities is necessary.
The break-even concept was particularly useful because it demonstrated how a printer with a higher purchase price could potentially become cheaper over time due to lower operating expenses.



## 10. Conclusion

This lab helped me understand the importance of evaluating the Total Cost of Ownership rather than relying solely on the initial purchase price of equipment.
By comparing two printers over five years, I learned how printing volume, toner efficiency, electricity consumption, and maintenance expenses influence long-term costs.
I also understood that the most economical printer may vary depending on the user's printing requirements. A printer suitable for a large organisation may not necessarily be the best choice for a home user.
The exercise demonstrated how TCO analysis can support informed purchasing decisions and improve the management of IT resources.
The final printer recommendation and break-even period will be added after completing the Excel calculations.



## 11. Screenshots and Supporting Evidence

The following screenshots will be included as evidence of the lab.


---

## 12. References

- [Brother Singapore](https://www.brother.com.sg/)
- [HP Singapore](https://www.hp.com/sg-en/)
- [SP Group](https://www.spgroup.com.sg/)

Specific product pages, retailer prices, and electricity tariff references will be added when the research is finalised.
