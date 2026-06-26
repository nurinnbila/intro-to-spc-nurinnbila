library(ggplot2)
library(plotly)
library(htmlwidgets)

# Assuming 'x025_filtered' is already defined with 'Machine' and 'PartLength' columns
plot_x025 <- ggplot(x025_filtered, aes(x = Machine, y = PartLength, fill = Machine)) +
  geom_boxplot() +
  labs(
    title = 'PartLength by Machine (Pressure=100, Temp=303)',
    x = 'Machine',
    y = 'Part Length'
  ) +
  scale_fill_manual(values = c('1' = '#0072B2', '2' = '#D55E00')) +
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

plotly_plot_x025 <- ggplotly(plot_x025)
saveWidget(plotly_plot_x025, file = 'media/plots/partlength_by_machine_boxplot.html', selfcontained = TRUE)
