Charting many variables
-----------------------

This lecture tells how you can make plots in R to represent many
variables

    boxplot(pm25 ~ region, data = pollution, col = "red")

![](Img/BoxPlot1.jpeg)

Same thing can be done with histograms

    par(mfrow = c(2, 1), mar = c(4, 4, 2, 1))
    hist(subset(pollution, region == "east")$pm25, col = "green", main = "Pm25 in East Region")
    hist(subset(pollution, region == "west")$pm25, col = "green", main = "Pm25 in West Region")

![](Img/hist1.jpeg )

The most obvious thing is to plot the latitude. We can put the limit
with an horizontal line. We can see that in the highest latitude the
value of the pm25 is not that high

    with(pollution, plot(latitude, pm25))
    abline(h = 12, lwd = 2, lty = 2)

![](Img/scatter1.jpeg)

Colours can be used to add another dimension. Black is west and red is
east.

    with(pollution, plot(latitude, pm25, col = region))
    abline(h = 12, lwd = 2, lty = 2)

![](Img/scatter2.jpeg)

Another way to look at the same thing is to make 2 plots in the
following way

    par(mfrow = c(1, 2), mar = c(5, 4, 2, 1))
    with(subset(pollution, region == "west"), plot(latitude, pm25, main = "West"))
    with(subset(pollution, region == "east"), plot(latitude, pm25, main = "East"))

![](Lect1_ManyVa![](Img/scatter3.jpeg)
