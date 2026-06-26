# Filter data for Machine == 1
x025_machine1_pt_interact <- X025[X025$Machine == 1, ]

# Convert Pressure and Temperature to factors for ANOVA
x025_machine1_pt_interact$Pressure_Factor <- factor(x025_machine1_pt_interact$Pressure)
x025_machine1_pt_interact$Temperature_Factor <- factor(x025_machine1_pt_interact$Temperature)

# Perform ANOVA for PartResistance vs Pressure * Temperature for Machine 1
anova_result_pt_interact <- aov(PartResistance ~ Pressure_Factor * Temperature_Factor, data = x025_machine1_pt_interact)

# Print ANOVA summary
summary(anova_result_pt_interact)
