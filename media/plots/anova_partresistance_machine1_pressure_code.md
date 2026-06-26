# Filter data for Machine == 1
x025_machine1 <- X025[X025$Machine == 1, ]

# Convert Pressure to a factor for ANOVA
x025_machine1$Pressure_Factor <- factor(x025_machine1$Pressure)

# Perform ANOVA for PartResistance vs Pressure for Machine 1
anova_result <- aov(PartResistance ~ Pressure_Factor, data = x025_machine1)

# Print ANOVA summary
summary(anova_result)
