![alt text](https://github.com/DigitalArtifex/QGaugeWidget/blob/main/images/screenshot.png)
# QGaugeWidget
A Gauge Cluster Widget for Qt

## Usage

``` C++
    m_temperatureGauge = new QGaugeWidget(this, QGaugeWidget::Temperature);
    m_temperatureGauge->setFixedSize(150,150);
    m_temperatureGauge->setIconSize(QSize(36,36));
    m_temperatureGauge->setIcon(QIcon(":/icons/temperature.png"));
    m_temperatureGauge->setMaximum(QIcon(":/icons/temperature.png"));
    m_temperatureLayout->addWidget(m_temperatureGauge);
```

QGaugeWidget supports the display format for temperature, percentage and raw values by passing either `QGaugeWidget::Temperature`, `QGaugeWidget::Percent` or `QGaugeWidget::Value` to the constructor as the Mode flag.

Temperature
![alt text](https://github.com/DigitalArtifex/QGaugeWidget/blob/main/images/screenshot.png)

Percentage
![alt text](https://github.com/DigitalArtifex/QGaugeWidget/blob/main/images/percent.png)

Raw Value
![alt text](https://github.com/DigitalArtifex/QGaugeWidget/blob/main/images/value.png)

### Icons

Icons can either be a QIcon object or an animated GIF. If you prefer to use an animated GIF as an icon use `QGaugeWidget::setAnimatedIcon` with the URI of the GIF

``` C++
    m_temperatureGauge->setAnimatedIcon(":/icons/temperature.gif");
```

### Customization

Typical customization for font, text color, background color, icon size etc are available through their respective setter functions and can be customized via QSS.

You can also set the pen style of the bar and fill if you want dashed lines etc

![alt text](https://github.com/DigitalArtifex/QGaugeWidget/blob/main/images/pen-style.png)

``` C++
    m_temperatureGaugePen.setCapStyle(Qt::FlatCap);
    m_temperatureGaugePen.setColor(m_temperatureGaugeColor);
    m_temperatureGaugePen.setWidth(m_pathWidth + 4);
    m_temperatureGauge->setProgressBarPen(m_temperatureGaugePen);

    m_temperatureGaugeFillPen.setWidth(m_pathWidth);
    m_temperatureGaugeFillPen.setColor(m_temperatureGaugeFillColor);
    m_temperatureGaugeFillPen.setCapStyle(Qt::FlatCap);
    m_temperatureGaugeFillPen.setStyle(Qt::DashDotDotLine);
    m_temperatureGauge->setProgressBarFillPen(m_temperatureGaugeFillPen);
```
