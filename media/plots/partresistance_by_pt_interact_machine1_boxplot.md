library(ggplot2)
library(plotly)
library(htmlwidgets)

# Assuming 'x025_machine1_pt_interact' is already defined with 'PT_Interaction_Factor' and 'PartResistance' columns
plot_partresistance_pt_interact <- ggplot(x025_machine1_pt_interact, aes(x = PT_Interaction_Factor, y = PartResistance, fill = PT_Interaction_Factor)) +
  geom_boxplot() +
  labs(
    title = 'PartResistance by Pressure:Temperature Interaction (Machine 1)',
    x = 'Pressure:Temperature Combination',
    y = 'Part Resistance'
  ) +
  scale_fill_manual(values = c('#0072B2', '#D55E00', '#009E73', '#CC79A7', '#E69F00', '#56B4E9', '#F0E442', '#999999', '#0072B2')) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, face = 'bold', hjust = 0.5, color = 'black'),
    axis.title.x = element_text(size = 18, face = 'bold', color = 'black'),
    axis.title.y = element_text(size = 18, face = 'bold', color = 'black'),
    axis.text.x = element_text(size = 14, color = 'black', angle = 45, hjust = 1),
    axis.text.y = element_text(size = 14, color = 'black'),
    legend.position = 'none',
    panel.background = element_rect(fill = 'white', color = NA),
    plot.background = element_rect(fill = 'white', color = NA)
  )

plotly_partresistance_pt_interact <- ggplotly(plot_partresistance_pt_interact)
saveWidget(plotly_partresistance_pt_interact, file = 'media/plots/partresistance_by_pt_interact_machine1_boxplot.html', selfcontained = TRUE)
