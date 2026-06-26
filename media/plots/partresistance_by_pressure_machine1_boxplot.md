library(ggplot2)
library(plotly)
library(htmlwidgets)

# Assuming 'x025_machine1_plot' is already defined with 'Pressure_Factor' and 'PartResistance' columns
plot_partresistance_pressure <- ggplot(x025_machine1_plot, aes(x = Pressure_Factor, y = PartResistance, fill = Pressure_Factor)) +
  geom_boxplot() +
  labs(
    title = 'PartResistance by Pressure for Machine 1',
    x = 'Pressure',
    y = 'Part Resistance'
  ) +
  scale_fill_manual(values = c('#0072B2', '#D55E00', '#009E73')) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, face = 'bold', hjust = 0.5, color = 'black'),
    axis.title.x = element_text(size = 18, face = 'bold', color = 'black'),
    axis.title.y = element_text(size = 18, face = 'bold', color = 'black'),
    axis.text.x = element_text(size = 14, color = 'black'),
    axis.text.y = element_text(size = 14, color = 'black'),
    legend.position = 'none',
    panel.background = element_rect(fill = 'white', color = NA),
    plot.background = element_rect(fill = 'white', color = NA)
  )

plotly_partresistance_pressure <- ggplotly(plot_partresistance_pressure)
saveWidget(plotly_partresistance_pressure, file = 'media/plots/partresistance_by_pressure_machine1_boxplot.html', selfcontained = TRUE)
