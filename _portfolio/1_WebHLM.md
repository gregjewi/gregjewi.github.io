---
title: "WebHLM"
excerpt: "Client-side computing for hydrologic simulations<br/><img src='/images/WebHLM-edu-results.png'>"
collection: portfolio
---

Client-side computing for hydrologic modeling
=======================
<i>WebHLM joins the growing and interconnected ecosystem of web-ready hydrologic tools.</i>

![](/images/WebHLM-edu-results.png)

WebHLM is a hydrologic simulation engine completely developed using web standards.
Capable of running full-scale hydrologic models in the browser, WebHLM is a new alternative for web-based simulation in hydrology.

Specs
--------
- **Language**	: JavaScript
- **Solver**	: 4th-Order Runge-Kutta with dynamic stepper and dense output interpolation
- **Model** 	: Hillslope Link Model construction. Constant Runoff and Variable Runoff models currently available

Results; Time Performance
--------
Current testing shows WebHLM is capable of simulating 1000 link-days per second.
In other words, in one second WebHLM can simulate one day of an area broken down into 1,000 hillslopes, Or simulate a single hillslope for 1,000 days.
The table below gives approximate simulation times for river networks of varying area.

| Basin Area [km^2] | Sim. Length [days] | Time to Complete |
|-------------------|--------------------|------------------|
| 10                | 1                  | 0.085 sec.       |
| 104               | 1.5                | 1.32 sec.        |
| 640               | 4                  | 17.5 sec.        |
| 1700              | 8                  | 1 min., 25 sec.  |
| 12600             | 20                 | 20 min.          |