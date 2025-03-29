DefaultIndustriesPlus ~ by embrrFlare
(View source code at https://github.com/embrrFlare/default-industries-plus)

(Many mechanic ideas inspired by Borg's Stockpiling Industries [BSPI])

This newGRF is an industry set that reimplements the default industries by adding new and modular mechanics designed to work in harmony.
DefaultIndustriesPlus currently only replaces the temperate industries, and will be broken on sub-arctic and sub-tropic climate types.

In its base form, this GRF adds:
- Secondary industry stockpiling
- New cargoes and cargo chains
- "Bonus" cargoes that increase production efficency

However, this GRF also contains many optional mechanics:
- Industry boosting mechanics (via bank, power plant, or town population)
- Custom industry closing rules
- Custom industry production change rules
- Primary industry reserves (limited supply of cargo)
- Base secondary conversion rate (responds to station rating and behaves like primary production rate)
- Secondaries require power to operate.

The default parameters offer a good starting point to get right into the industry set, without being too difficult.
All the mechanics are designed to be used in conjunction with each other in any combination you'd like. Play the way you like the most!

More in-depth mechanic primer:

Secondary Stockpiling:
- Like many other industry sets, secondaries have a limit to how much cargo they can stockpile at once.
- How full the stockpile is influences their conversion speed. If it's too full, the secondary will stop accepting cargo completely.
- Secondaries will store up to 10 month's worth of theoretical maximum production (assuming all bonuses are maxed) before stopping to accept cargo.
- However, to max out the stockpile modifier, you only need 1 month's worth.
- In general it is a good idea to keep less than 5k units of input cargo waiting as any more is unnecessary, although the exact amount will depend on your settings.

New Chains:
- Sawmill now produces lumber instead of goods
- Oil refinery produces goods at a lower rate and produces two additional cargoes: Lubricants and Petrol
- Lumber -> Factory
- Lubricants -> Factory (Increases Conversion Efficency)
- Petrol -> Power Plant (Increases Conversion Efficency)

Production Increasing Cargoes (Conversion Efficiency):
- Certain cargoes are not converted directly into output cargo, but increase the conversion efficiency of other cargoes.
- These cargoes (Lubricants and Petrol) give an efficiency bonus based on their current stockpile, and will be converted at a similar (but lesser) rate as the other cargoes.
- This efficiency bonus directly increases their output: The factory will produce more goods from the same amount of cargo, and coal will be consumed at a lesser rate while still generating the same amount of power.

Bonus mechanics:
- Delivering enough cargo to the power plant / bank will give a bonus to industries within the town.
- This bonus is limited either by the waiting cargo stockpile (simple mechanics) or by the number of waiting "units" (advanced mechanics)
- Cargo is converted into "units" over time (Advanced mechanics). Industries that are affected by the bonus will consume units every production tick.
- Simple mechanics have a single pre-set goal of cargo per month, while advanced mechanics need some form of logistics to scale cargo delivery with town industry production.
- The town bonus is simply affected by the town's population, adding a small incentive to grow the town.
- Bonuses can either be additive or multiplicative with each other based on preferenc.

Industry Closure / Freezing Rules:
- Industries are considered "serviced" if at least one of their output cargoes are being serviced (primary industries) or if they are able to produce cargo (secondaries).
- An industry being serviced or unserviced only has an effect on its closure or freezing rules.
- If closure is turned off, the industry can lower to its minimum production but will not close.
- If freezing is turned on, the industry will either have slowed production changes or completely stopped changes. This prevents unserviced industries with closures disabled to lose all their initial production and require a lengthy amount of time to recover.

Production Changes:
- If "Smooth Primary Industry Growth" is on, production changes have a much smaller impact and are much smoother over time.
- Each production change tick is completely deterministic and determined by your growth difficulty settings.
- The station rating of each cargo is used. For industries with two or more output cargoes (farms), an average of each cargo is used.
- Station rating calculations remain unchanged. To keep station ratings high, use fast, new vehicles that pick up at the station often and keep waiting cargo low, alongside building a town statue.
- From minimum production (4), industries need 124 positive ticks to reach max production (128). It is recommended to have a moderate growth rate setting to account for the slower rate of growth compared to vanilla.
- These production rules are identical for secondaries, assuming "Advanced Secondary Mechanics" is enabled.

Primary Reserves:
- When enabled, industries will spawn with a limited number of reserves. This number decreases whenever they produce cargo and are currently being serviced (Non-connected industries do not use up their reserves)
- Whenever reserves run out, the industry will close next month.

Advanced Secondary Mechanics:
- If enabled, secondary industries will additionally have a base production, similar to primary industries.
- Growth mechanics are unchanged, just ensure to keep good service by delivering the output cargo (input cargo has no effect) and keeping station ratings high.
- For secondaries with multiple outputs, an average of the station ratings is used. Ensure to deliver all cargo types to keep ratings high!
