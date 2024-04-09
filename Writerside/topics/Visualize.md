---
switcher-label: Framework/Library
---

# Visualizing Data

> Visualizing data is an essential part of data analysis and exploration. It helps to understand complex data sets, identify patterns, trends, and outliers, and communicate insights effectively. In Python, there are several libraries and tools available for creating visualizations, each with its own strengths and capabilities. Some popular libraries for data visualization in Python include Matplotlib, Seaborn, Plotly, Bokeh, Altair, Plotnine, and Pygal. In this guide, we will explore how to create visualizations using these libraries.

{ style="note" }

## Why is visualization important?

<table>
    <tr>
        <th>Reason</th>
        <th>Explanation</th>
    </tr>
    <tr>
        <td>Understanding complex data</td>
        <td>Visualizations can help simplify complex data sets and make it easier to identify patterns and trends.</td>
    </tr>
    <tr>
        <td>Communicating insights</td>
        <td>Visualizations are an effective way to communicate insights and findings to others in a clear and concise manner.</td>
    </tr>
    <tr>
        <td>Identifying outliers</td>
        <td>Visualizations can help identify outliers and anomalies in data that may not be apparent from raw data alone.</td>
    </tr>
    <tr>
        <td>Comparing data</td>
        <td>Visualizations make it easy to compare different data sets and understand relationships between variables.</td>
    </tr>
    <tr>
        <td>Decision-making</td>
        <td>Visualizations can help support decision-making processes by providing a visual representation of data.</td>
    </tr>
</table>


## Popular Libraries for Data Visualization

> *_Note : matplotlib, plotly, and altair are the only ones working with edstem._*

### [MatPlotLib](https://matplotlib.org/)

Matplotlib is one of the most widely used libraries for creating static, interactive, and animated visualizations in Python. It provides a wide range of plotting functions to create various types of charts, graphs, and plots. Matplotlib is highly customizable and allows users to create publication-quality visualizations.

<table>
<tr>
<td>

**Example**

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [1, 4, 9, 16, 25]

plt.plot(x, y)
plt.show()
```

</td>
<td>

![](matplotlib.png)
</td>
</tr>
</table>

#### Pros and Cons of Matplotlib

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Widely used and well-documented</td>
    <td>Steep learning curve</td>
</tr>
<tr>
    <td>Highly customizable</td>
    <td>Verbose syntax</td>
</tr>
<tr>
    <td>Supports a wide range of chart types</td>
    <td>Not ideal for interactive visualizations</td>
</tr>
<tr>
    <td>Works well with Pandas data structures</td>
    <td></td>
</tr>
<tr>
    <td>Can create publication-quality visualizations</td>
    <td></td>
</tr>
</table>

### [Altair](https://altair-viz.github.io/index.html)

Altair is a declarative statistical visualization library for Python that is based on the Vega and Vega-Lite visualization grammars. It allows users to create complex visualizations with minimal code by specifying the data and visual encoding rules. Altair is designed to work well with Pandas data structures and is ideal for creating interactive visualizations.

<table>
<tr>
<td>

**Example**

```Python
import altair as alt
import pandas as pd

data = pd.DataFrame({
    'x': [1, 2, 3, 4, 5],
    'y': [1, 4, 9, 16, 25]
})

alt.Chart(data).mark_line().encode(
    x='x',
    y='y'
)
```

</td>
<td>

![](altair.png)
</td>
</tr>
</table>


#### Pros and Cons of Altair

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Declarative syntax</td>
    <td>Less customizable than Matplotlib</td>
</tr>
<tr>
    <td>Minimal code required</td>
    <td>Not ideal for custom visualizations</td>
</tr>
<tr>
    <td>Works well with Pandas data structures</td>
    <td></td>
</tr>
<tr>
    <td>Ideal for interactive visualizations</td>
    <td></td>
</tr>
</table>


### [Plotly](https://plotly.com/python/)

Plotly is a powerful library for creating interactive visualizations in Python. It supports a wide range of chart types, including line charts, bar charts, scatter plots, and 3D plots. Plotly visualizations can be embedded in web applications and dashboards, making it ideal for data visualization in web development.

<table>
<tr>
<td>

**Example**

```python
import plotly.express as px

x = [1, 2, 3, 4, 5]
y = [1, 4, 9, 16, 25]

fig = px.line(x=x, y=y)
fig.show()
```

</td>
<td>

![](plotly.png)
</td>
</tr>
</table>

#### Pros and Cons of Plotly

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Interactive visualizations</td>
    <td>Requires an internet connection to render plots</td>
</tr>
<tr>
    <td>Supports a wide range of chart types</td>
    <td>Less customizable than Matplotlib</td>
</tr>
<tr>
    <td>Ideal for web development</td>
    <td></td>
</tr>
<tr>
    <td>Works well with Pandas data structures</td>
    <td></td>
</tr>
</table>

### [Bokeh](https://docs.bokeh.org/en/latest/index.html)

Bokeh is a Python library for creating interactive visualizations that are optimized for the web. It provides a flexible and powerful framework for creating interactive plots, dashboards, and applications. Bokeh supports a wide range of chart types and can handle large datasets efficiently.

<table>
<tr>
<td>

**Example**

```python
from bokeh.plotting import figure, show

# prepare some data
x = [1, 2, 3, 4, 5]
y = [1, 4, 9, 16, 25]

# create a new plot with a title and axis labels
p = figure(
title="Simple line example", 
x_axis_label="x", 
y_axis_label="y")

# add a line renderer with legend and line thickness
p.line(x, y, legend_label="Temp.", line_width=2)

# show the results
show(p)
```

</td>
<td>

![](bokeh.png)
</td>
</tr>
</table>

#### Pros and Cons of Bokeh

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Interactive visualizations</td>
    <td>Steep learning curve</td>
</tr>
<tr>
    <td>Optimized for the web</td>
    <td>Requires JavaScript knowledge for advanced customization</td>
</tr>
<tr>
    <td>Works well with Pandas data structures</td>
    <td></td>
</tr>
<tr>
    <td>Supports large datasets</td>
    <td></td>
</tr>
</table>


### [Seaborn](https://seaborn.pydata.org/tutorial/relational.html)

Seaborn is built on top of Matplotlib and provides a high-level interface for creating attractive and informative statistical graphics. It simplifies the process of creating complex visualizations such as heatmaps, violin plots, and pair plots. Seaborn is designed to work well with Pandas data structures and is ideal for exploratory data analysis.

#### Pros and Cons of Seaborn

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Attractive and informative visualizations</td>
    <td>Less customizable than Matplotlib</td>
</tr>
<tr>
    <td>High-level interface for complex plots</td>
    <td>Not ideal for custom visualizations</td>
</tr>
<tr>
    <td>Works well with Pandas data structures</td>
    <td></td>
</tr>
<tr>
    <td>Supports a wide range of chart types</td>
    <td></td>
</tr>
</table>


### [Plotnine](https://plotnine.org)

Plotnine is a Python implementation of the Grammar of Graphics, a powerful data visualization framework. It provides a high-level interface for creating complex visualizations by specifying the data, aesthetics, and geometries. Plotnine is designed to work well with Pandas data structures and is ideal for creating publication-quality visualizations.

#### Pros and Cons of Plotnine

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Grammar of Graphics implementation</td>
    <td>Steep learning curve</td>
</tr>
<tr>
    <td>High-level interface for complex visualizations</td>
    <td>Less customizable than Matplotlib</td>
</tr>
<tr>
    <td>Works well with Pandas data structures</td>
    <td></td>
</tr>
<tr>
    <td>Can create publication-quality visualizations</td>
    <td></td>
</tr>
</table>


### [Pygal](https://www.pygal.org/en/stable/index.html)

Pygal is a Python library for creating scalable vector graphics (SVG) visualizations. It provides a simple and intuitive interface for creating line charts, bar charts, pie charts, and more. Pygal visualizations can be embedded in web applications and documents, making it ideal for creating interactive visualizations.

#### Pros and Cons of Pygal

<table>
<tr>
    <th>Pros</th>
    <th>Cons</th>
</tr>
<tr>
    <td>Scalable vector graphics</td>
    <td>Less customizable than Matplotlib</td>
</tr>
<tr>
    <td>Simple and intuitive interface</td>
    <td>Not ideal for complex visualizations</td>
</tr>
<tr>
    <td>Works well with web applications</td>
    <td></td>
</tr>
<tr>
    <td>Can create interactive visualizations</td>
    <td></td>
</tr>
</table>

## Installation

To install these libraries, you can use the following commands:

```bash
pip install matplotlib
pip install seaborn
pip install plotly
pip install bokeh
pip install altair
pip install plotnine
pip install pygal
```

Once installed, you can import the libraries in your Python script and start creating visualizations.
