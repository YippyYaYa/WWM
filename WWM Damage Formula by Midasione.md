*Translated from [Yoka’s damage calculator sheet](https://docs.google.com/spreadsheets/d/1UFopWBwYlBSLdcQ3r94irw_1LzZLCNwj/edit?usp=drive_link&ouid=114593518924144928325&rtpof=true&sd=true) with extra added clarifications gathered from various sources ([WindsFromCN](https://www.youtube.com/@WindsFromCN), [Whispers of the Wind](https://www.youtube.com/@Whisperwindyysls), Chinese forums (NGA, 9Game, 360game, etc.), self testing) and self-added notes*

**Total Damage \= Base Dmg \* Crit Multiplier (if crit) \* Affinity Multiplier (if affinity) \* Dmg Bonus Multiplier \* Independent Multiplier \* Dmg Reduction Multiplier \* Penetration Multiplier \* Dmg Amplification Multiplier**

**1\. Base Dmg**  
Base Dmg \= (Physical Atk \- Physical Defense) \* Physical Scaling \+ Flat Dmg \+ (Matching Path Attribute Atk \+ Formless Attribute Atk) \* Matching Path Attribute Scaling \+ Non-Matching Path Attribute Atk \* Non-Matching Path Attribute Scaling 

- Atk values fluctuate in a range from Min to Max Atk  
- If a hit is Abrasion, Base Dmg is calculated using Min Atk  
- Attribute Atk are Bellstrike/Bamboocut/Silkbind/Stonesplit Atk  
- Formless is like a “universal” attribute that is always added to your matching path. Only appears at level 91+  
- If Min Atk \> Max Atk, all dmg (including affinity) is calculated using Min Atk value instead  
  - *Self note: For matching path, Attribute Atk starts at a non-zero Min-Max range, so by adding more Min/Max Matching Path Attribute Attack, it is still being affected by this range. However, for Non-Matching Paths, since Min-Max starts at 0-0, by adding a non-zero Non-Matching Path Min Attribute Atk, it will always take that Min Atk value into calculation since Min Atk \> Max Atk now, the calculation is not affected by a range. Therefore, Non-Matching Path Min Atk is widely considered to be better than Matching Path Min/Max Atk.*  
- The final dmg may receive an extra bonus of \+1 or \+2  
- Damage over Time (DoT) doesn’t benefit from Flat Dmg, and doesn’t have a higher Matching Path Attribute Scaling compared to Non-Matching Path. This applies to Dragon’s Breath, Divinecrafts, Strategic Sword’s Bleed, and Fivefold Bleed  
- *Self note: For Martial Art Skills, Physical Scaling is always around 1.5 times lower than Attribute Scalings. Therefore, in a 1-to-1 comparison, Attribute Atk is better than Physical Atk. HOWEVER, on gear’s sub-stat rolls, Attribute Atk’s numeric value range is much smaller than Physical Atk’s to the point that it’s worse to roll Attribute Atk than Physical Atk. Mystic Skills also scales significantly better with Physical Atk than Attribute Atk.*

**2\. Crit Dmg**  
Crit Multiplier \= 1 \+ Base Crit Dmg \+ Bonus Crit Dmg

**3\. Affinity Dmg**  
Affinity Multiplier \= 1 \+ Base Affinity Dmg \+ Bonus Affinity Dmg  
Affinity always uses Max Atk, unless Min Atk \> Max Atk, in which case Min Atk is used instead

**4\. Dmg Bonus**  
All dmg bonus sources **and debuffs** stack **additively** in a single multiplier  
Some examples of dmg bonus sources:

- Exhaustion debuff (10% dmg bonus)  
- Heavenquaker Spear’s River Flow dmg buff  
- Stormbreaker Spear’s Vulnerability debuff

**5\. Independent Multiplier**  
A separate dmg bonus multiplier that stacks multiplicatively instead of additively  
Only source of independent multiplier is Vendetta Inner Way’s Rodent dmg bonus

**6\. Damage Reduction**  
All dmg reduction sources stack **multiplicatively**  
Dmg Reduction Multiplier \= 1 \* (1 − DR1) \* (1 − DR2) \* (1 − DR3) \* ... \* (1 − DRn)

**7\. Penetration Multiplier**  
If (Penetration \- Resistance) \<= 0:  
	Penetration Multiplier \= 1 \+ (Penetration − Resistance) / 200  
Else:  
	Penetration Multiplier \= 1 \+ (Penetration − Resistance) / 100  
Physical Penetration/Resistance applies to Physical Atk, and Attribute Penetration/Resistance applies to the corresponding Attribute Atk Type. Formless Penetration also exists (at level 91+) and is added to your matching path’s penetration

**8\. Precision / Crit / Affinity / Abrasion Rate**  
Precision Rate is checked first. If a hit is precision, it can be Affinity (orange), Crit (yellow), or Standard (white). If a hit is non-precision, it can be Affinity or Abrasion (gray)  
All stats in this section are final post-resistance rates. For formulas regarding resistances and direct rates, check section 11\. Overall:  
When (Crit Rate \+ Affinity Rate) \<= 100%:

- Actual Affinity Rate \= Affinity Rate   
- Actual Crit Rate \= Precision Rate \* Crit Rate  
- Abrasion Rate \= (1 − Precision Rate) \* (1 − Affinity Rate)  
- Standard Rate \= 1 \- Actual Affinity Rate \- Actual Crit Rate \- Abrasion Rate

When (Crit Rate \+ Affinity Rate) \> 100%:

- **Affinity Rate overrides Crit Rate**  
- Actual Affinity Rate \= Affinity Rate   
- Actual Crit Rate \= Precision Rate \* (1 \- **Affinity Rate**)  
- Abrasion Rate \= (1 − Precision Rate) \* (1 − Affinity Rate)  
- Standard Rate \= 1 \- Actual Affinity Rate \- Actual Crit Rate \- Abrasion Rate

*Self note: In this formula, it’s clear that Affinity/Crit/Standard/Abrasion are 4 **distinct** outcomes of a single hit, whose probabilities add up to 100%. Using simple maths:*

- *If Precision Rate is 100%, then Abrasion Rate is 0% \=\> only 3 outcomes remain (Affinity/Crit/Standard)*  
- *If Precision Rate is 100% and (Crit Rate \+ Affinity Rate) \> 100%, then Standard Rate is also 0% \=\> only 2 favorable outcomes remain (Affinity/Crit). This is the stat goal to aim for to never hit white/gray damage.*  
- *Being distinct means 2 different outcomes can’t happen at the same time: A hit can never be both Crit and Affinity, which means Crit Multiplier and Affinity Multiplier are never applied at the same time.*

**9\. Dmg Amplification**  
This refers to passive talents found in Martial Art Breakthrough. For example: Physical/Attribute Atk DMG UP by XX%. These can be treated as independent multipliers to the corresponding physical/attribute atk types.

**10\. Healing**  
Precision, Abrasion, Affinity do not apply to healing.  
Healing is always 100% precision hits.  
Only Crit vs Non-Crit heals exist.  
Non-Matching Path Attribute Atk types provide 0 benefit to healing, only Physical Atk and Silkbind Atk count.  
Healing has an independent fluctuation of \+/-10%

**11\. Precision/Crit/Affinity Resistances**  
Final Precision Rate \= 65% \+ Precision Bonuses / (1 \+ Resistance)  
Final Crit Rate \= MIN(80%, Raw Crit Rate / (1 \+ Resistance))  \+ Direct Crit Rate  
Final Affinity Rate \= MIN(40%, Raw Affinity Rate / (1 \+ Resistance)) \+ Direct Affinity Rate  
The MIN function is to cap Crit/Affinity Rate at 80%/40% respectively, after Resistances, but before adding Direct Rates  
Resistance values:

- Level 81-85: 15%  
- Level 86-90: 30%  
- Level 91-95: 45%  
- Level 96-100: 65%

All sources of raw Precision Rate, Crit Rate, and Affinity Rate are affected by resistances, **EXCEPT** ~~Thundercry Blade’s charged attack bonus Crit Rate from Martial Art Breakthrough, which is a flat addition to Final Crit Rate~~ (this was changed to Max Phys Atk in 2.0)

**12\. Five Basic Attributes**  
1 Body \= 60 HP  
1 Defense \= 17 HP \+ 0.5 Physical Defense  
1 Agility \= 0.9 Min Physical Atk \+ 0.076% Crit Rate  
1 Momentum \= 0.9 Max Physical Atk \+ 0.038% Affinity Rate  
1 Power \= 0.225 Min Physical Atk \+ 1.36 Max Physical Atk

**BONUS: Gear Roll Guide (PvE)**  
For an offensive (non-healer) build, generally (*not definitively*):  
Main stats (1st line):

- On the 4 weapons and charms slots, Max Physical Atk is best  
- On the helm and armor slots, Crit/Affinity Rate is best  
- On the gloves and greaves slots, Power is best

Sub-stats (each sub-stat can only be rolled once on each piece, but they can be the same as main stat):

- The “God” lines (EXTREMELY rare, good to have, but don’t discard a good piece just because they don’t have these lines):  
- On the 2 weapon slots: Art of \<Weapon\> Boost  
- On the 2 charm slots: Increase All Martial Arts Boost  
- On the helm and armor slots: Single-target/AoE Mystic Skills Boost (build/playstyle dependant)  
- On the gloves and greaves slot: Increase Dmg to Bosses/Players (PvE/PvP)  
- Precision/Crit/Affinity Rate to breakpoint is the highest priority  
- Then Max Physical Atk \> Min Physical Atk \> Non-Matching Path Min Attribute Atk \> Matching Path Max Attribute Atk \> Matching Path Min Attribute Atk (as explained in section 1\)  
- Power is the best amongst the basic attributes

Attunement line:

- On the 4 weapons and charms slots, Physical Penetration \> Attribute Penetration (or Formless at level 91+)  
- On the 4 armor slots, the best option is whichever gives Dmg Boost to your main source of dmg.  
  - For example, a Stonesplit \- Might build would want to roll 4 lines of Thundercry Blade Charged Skill Dmg Boost

**BONUS: Can a hit be both Crit and Affinity?**  
A common misconception disproved with math and in-game testing:  
[Can a Hit be both Crit and Affinity?](https://docs.google.com/document/d/1DuanY6YXQYdUgBxmYrhFsxx8LYzGuYCoU-qVvEbDAOs/edit?usp=sharing)

**BONUS: Personal Observations**  
There are a lot of interesting quirks and design choices in this formula by the devs. However, the more I think about it, the more I realize that almost every choice benefits the player’s damage output (which is honestly really cool\!). Let me explain:

- When Min Atk \> Max Atk, there is a choice between (1) setting Min \= Max or (2) Max \= Min. Option (1) causes all Min Atk rolls to be wasted, option (2) is a big dmg boost. They chose option (2).  
- When there are multiple sources of Attribute Atk, there is a choice between (1) disregarding Non-Matching Path Attribute Atk and (2) keeping them in the formula. Option (2) causes less “wasted” offensive stat rolls, which is what they chose.  
- Regarding Precision/Crit/Affinity, there is a choice between (1) doing 2-3 sequential checks separately for precision, then affinity, then crit, or (2) making it a single check with 4 different outcomes. Option (1) makes it impossible to avoid Standard Dmg since Crit and Affinity Rates are capped, option (2) makes it possible since the 2 rates are now additive. They chose (2).  
- Regarding Penetration, when it is lower than Resistance, the negative effect of having low Penetration is halved, which favors Dmg dealt.  
- Although the choice of additive Dmg Bonus stacking is mathematically worse than multiplicative, I believe it’s to prevent game-breaking one-shot builds, since multiplicative stacking can get out of hand VERY quickly. Dark Souls / Elden Ring one-shot showcases demonstrate this clearly, since FromSoftware uses multiplicative buff stacking in all their games.