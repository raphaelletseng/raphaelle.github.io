---
layout: post
title: "Getting to know MatPlotLib and Python-docx"
date: 2019-10-05
---

Recently, my boss asked me if I'd be able to automate and expedite the analysis of a set of data
so that my colleagues would be able to avoid manually copying and pasting numbers into 
columns on excel. For me this proposed a few new challenges I had not yet encountered:
1. Writing a working piece of code in python, a language I'd used sparingly and never 
for any kind of big project up until now.
2. Figuring out how to generate graphs using matplotlib
3. Figuring out how to output everything as a word document containing images that depended on the raw
input data. 

Essentially, the task was this: How do I take this raw data that represents x, y, z, execute certain
transformations on the numbers to get adjusted values, turn the results into a series of graphs, 
and then output these graphs as a word document along with a set of images that vary depending on 
all the results? 
It seemed simple enough and doable on python. But I ended up learning a bunch of new things I thought
I would throw into a little post for future reference. 

## Transformations

Honestly, the maths was probably the easiest part. I had excel formulas and all I had to do was apply
them to my data. I imported my data using pandas and shoved everything into an array:
```
import pandas as pd
data = pd.read_csv ('Raw data.csv')
dataset = data.values
```
I mostly used while loops to iterate through everything and apply the right changes. Once I had the final
numbers, I threw them into a new array and rounded them up to integers.

## Graphs

Matplotlib is a Python 2D plotting library used to make graphs and figures.
You can generate plots, histograms, bar charts, scatterplots etc. 
```
from matplotlib import pyplot as plt
from math import pi
```
I wanted 3 plots, a radar chart, horizontal bar charts and a polar bar chart. 
The radar was created using [this link](https://python-graph-gallery.com/390-basic-radar-chart/):
```
df = pd.DataFrame({
'group': ['A'],
'Comp' : [finals[0]],
'Pos': [finals[1]],
'EmC':[finals[2]],
'Soc':[finals[3]],
'Ene':[finals[4]],
'As': [finals[5]],
'Co':[finals[6]],
'Tr':[finals[7]],
'Re':[finals[8]],
'Ac':[finals[9]],
'Res':[finals[10]],
'Pro':[finals[11]],
'Tho':[finals[12]],
})

categories=list(df)[1:]
N = len(categories)
values=df.loc[0].drop('group').values.flatten().tolist()
values += values[:1]
angles = [n / float(N) * 2 * pi for n in range(N)]
angles += angles[:1]
ax = plt.subplot(111, polar=True)
plt.xticks(angles[:-1], categories, color='black', size=8)
ax.set_rlabel_position(0)
plt.yticks([10,20,30,40,50,60,70,80,90,100], ["10","20","30","40","50","60","70","80","90"], color="grey", size=7)
plt.ylim(0,100)
ax.plot(angles, values, linewidth=1, linestyle='dotted')
ax.fill(angles, values, 'b', alpha=0.3)
```
The dataframe defines the categories for the plot with the relevant results. 
plt.yticks sets the continuous axis labels and plt.ylim (0,100) sets the range.
ax.plot and ax.fill are used to customise the aesthetic of the plot. 

- The bar charts were made using matplotlib's references:

```
import numpy as np
np.random.seed(1234)
plt.rcdefaults()
fig, ax = plt.subplots()#figsize = (2,5)
fig.set_size_inches(9,2, forward=True)

ax.spines['top'].set_visible(False)
ax.spines['right'].set_visible(False)
ax.spines['bottom'].set_visible(False)
ax.spines['left'].set_color('grey')
ax.spines['left'].set_alpha(0.3)
ax.spines['left'].set_lw(1.5)

fontprop = {'family':'arial'}

x = np.array([0,30,60,90])
my_xticks = ['0', '30%', '60%', '90%']
plt.xticks(x, my_xticks, color ='grey', fontsize = 9)

plt.axvline(x=30, color = 'grey',  alpha = 0.3)
plt.axvline(x=60, color = 'grey',  alpha = 0.3)
plt.axvline(x=90, color = 'grey',  alpha = 0.3)

titles = ('Creative Imagination', 'Intellectual Curiosity', 'Adventurousness')
y_pos = np.arange(len(titles))
result = (finals[15], finals[16], finals[17])

ax.barh(y_pos, result, color = 'lightgreen', height = 0.4)
ax.set_yticks(y_pos)
ax.set_yticklabels(titles, color = 'grey', fontsize = 12, family = {'arial'})

#a = gca()
#a.set_yticklabels(a.get_yticks(), fontprop)

for line in ax.yaxis.get_ticklines(): 
    line.set_markersize(0)
for line in ax.xaxis.get_ticklines():
    line.set_markersize(0)

for i, v in enumerate(result):
    ax.text(v + 3, i - 0.1, str(v) + str('%'), color = 'grey', fontsize = 13)
    
plt.savefig('Open.png', bbox_inches = 'tight')
```
NumPy is the numerical mathematics extension of matplotlib.
ax.barh() is the line that edits the colour, look and overall aesthetic of the bars.
The forloop serves to add labels to the end of the bars that indicate their values. 
I wanted to save the graphs to be able to use them in my word doc later. I found that if I didn't add 'bbox_inches='tight', my saved png would be cropped and I would lose some information.

![Bar chart](/assets/img/barcharteg.PNG)

My polar bar chart was done using Matplotlib's documentation:
```
import numpy as np
import matplotlib.pyplot as plt
np.random.seed(19680801)
N = 18
theta = np.linspace(0.0, 2*np.pi, N, endpoint=False)
radii = 100 
width = 2*np.pi/(N+0.7)
colors = ["palevioletred","palevioletred","palevioletred", "mediumorchid","mediumorchid","mediumorchid", "rebeccapurple",
          "rebeccapurple", "rebeccapurple", "slateblue", "slateblue", "slateblue", "lightblue", "lightblue", "lightblue",
         "lightgreen", "lightgreen", "lightgreen"]
#plt.cm.hsv(theta/2/np.pi)
y_ticks = [0,10,20,30,40,50,60,70,80,90,100]
ax = plt.subplot(111, projection='polar')
ax.bar(theta, finals, width=width, bottom=0.0, color=colors, alpha=0.8, align = 'edge')
ax.set_yticks(y_ticks)
ax.set_yticklabels(["0%",'10%','20%', '30%', '40%',
                   '50%', '60%', '70%', '80%', '90%', '100%'], color = 'grey', fontsize = 6)
ax.set_xticklabels([])
ax.set_theta_zero_location('N')
ax.set_theta_offset(pi/2)
ax.set_theta_direction(-1)
ax.spines['polar'].set_color("grey")
ax.spines['polar'].set_alpha(0.3)
ax.set_axisbelow(True)
plt.savefig('PolarPlot.png')
```
![Polar Plot](/assets/img/polarplot.png)


## Python-docx
Python-docx is a Python library for creating and updating Microsoft Word (.docx) files.

Firstly, I had to install python-docx and set up what I'd need:
```
pip install python-docx
from docx import Document
from docx.shared import Inches
from docx.shared import Pt
```
Python-docx essentially writes information to a word document as indicated.
This line opens a new document without specifying a file to open, creating a new document
from the built-in default template. This is just a Word file with no content, stored
with the installed python-docx package. I've linked the python-docx documentation [here](https://python-docx.readthedocs.io/en/latest/index.html).
```
document= Document()
document.add_heading("My results!")
```
If you wanted to open an existing document you would just specify the path of that document in the brackets as follows:
```
document = Document("existing-file.docx")
```
I didn't like the default font so I decided to change it to Arial. 
Styles defined in the document can be accessed using the Document.styles property.
```
font = document.styles['Normal'].font
font.name = 'Arial'
font.size =Pt(10)
```
And then I just started writing my saved graphs to the document.
document.save("MA.docx") saves the document to a file named 'result.docx'.

add_run appends a run to a paragraph containing text. 
style is the object representing the style assigned to this paragraph, in this case 
the style we defined earlier, 'Normal'.
r1 stands for run objects - r1.add_picture(image_path, width, height) returns an in line shape instance. 

```
p = document.add_paragraph("EI \n")
p.style = document.styles['Normal']
r1 = p.add_run()
r1.add_picture('EI.png', width = Inches(4))

document.save("result.docx") # At the end of your code to generate the docx file
```
The next set of images I wanted to add were dependent on the final results. Depending on whether my numbers fell
between 0 - 30, 31 - 60 and 61 - 100, a different set of images would have to be generated.
For this, I just used a simple if elif statement to determine which of the images to load using:
```
r1.add_picutre('IMAGE.PNG', width = Inches (6))
```
And once I'd done that I had a word document filled with information about the raw data that I'd inputted.
It was pretty cool to see that my code was able to take a raw set of numbers and spit out 
useful information and graphs. I learnt how to output word documents, a skill I think will come in 
pretty handy in the future, and began to learn the basics of matplotlib, which is always useful. 

