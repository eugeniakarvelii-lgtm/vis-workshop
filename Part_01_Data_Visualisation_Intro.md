# Introduction to Data Visualisation

This is a supplementary resource for the workshop.

The live session is mainly hands-on, so this page provides extra background on data visualisation theory, interactive visualisation, Digital Humanities examples, and tools for further learning.

You do not need to read this before the workshop. It is designed as a reference you can return to before, during, or after the session.

In the workshop, we will focus on a practical web-based example using HTML, CSS, JavaScript, D3.js, Leaflet, and GitHub Pages. This resource gives some of the wider ideas behind those practical choices.

---

## Contents

- [How this resource fits the workshop](#how-this-resource-fits-the-workshop)
- [What is data visualisation?](#what-is-data-visualisation)
- [Why visualise Digital Humanities data?](#why-visualise-digital-humanities-data)
- [The workshop example: people, places, and time](#the-workshop-example-people-places-and-time)
- [A useful design question: what, why, and how?](#a-useful-design-question-what-why-and-how)
- [Data types and visual encodings](#data-types-and-visual-encodings)
- [Visual variables](#visual-variables)
- [Maps, timelines, and linked views](#maps-timelines-and-linked-views)
- [Interactivity in visualisation](#interactivity-in-visualisation)
- [Humanities data: uncertainty, interpretation, and bias](#humanities-data-uncertainty-interpretation-and-bias)
- [Design principles and common pitfalls](#design-principles-and-common-pitfalls)
- [Accessibility and inclusive design](#accessibility-and-inclusive-design)
- [Tools for data visualisation](#tools-for-data-visualisation)
  - [Tools used in this workshop](#tools-used-in-this-workshop)
  - [Other programming tools](#other-programming-tools)
  - [Web development frameworks](#web-development-frameworks)
  - [No-code and low-code tools](#no-code-and-low-code-tools)
- [Digital Humanities examples and inspiration](#digital-humanities-examples-and-inspiration)
- [Getting started with your own visualisation project](#getting-started-with-your-own-visualisation-project)
- [Further reading](#further-reading)
- [License](#license)

---

## How this resource fits the workshop

In the workshop, we build a small interactive web visualisation using:

- **HTML** for the page structure;
- **CSS** for styling;
- **JavaScript** for interaction;
- **D3.js** for data-driven visualisation;
- **Leaflet** for interactive mapping;
- **GitHub Pages** for publishing.

The practical workshop focuses on a historical dataset from the University of Edinburgh records:

[University of Edinburgh Alumni Collections](https://collections.ed.ac.uk/alumni)

The live coding will show how a dataset can be loaded into a webpage, displayed on a map, and summarised as a simple timeline.

This page gives the wider context: why we visualise data, how visualisation design choices work, and how these ideas apply to Digital Humanities research.

---

## What is data visualisation?

Data visualisation is the practice of representing data using visual forms such as charts, maps, diagrams, timelines, networks, dashboards, and interactive interfaces.

Visualisation is a way of making patterns, relationships, uncertainty, and absences easier to inspect and discuss.

Good visualisation can help people:

- explore data;
- identify patterns;
- compare values;
- notice exceptions;
- communicate evidence;
- ask new questions;
- explain an argument;
- make a dataset more accessible to others.

The [Royal Statistical Society Best Practices for Data Visualisation guide](https://royal-statistical-society.github.io/datavisguide/) is a useful general introduction. It provides a view to visualisation as a technical and creative practice, involving choices about data, charts, perception, readability, annotation, colour, and communication.

---

## Why visualise Digital Humanities data?

Digital Humanities data often includes complex cultural, historical, spatial, textual, and archival material.

Visualisation can help researchers work with:

- people;
- places;
- dates and time periods;
- correspondence;
- journeys and movement;
- institutions;
- texts;
- networks;
- uncertainty;
- missing or partial records.

In humanities research, visualisation is a research method as much as it is a communication mode and output medium. What it offers as an expansion to written synthesis of complex information, is a way to engage further sense, interpretive modes, and flexibility for connecting themes and ideas. 

A visualisation can help us ask:

- What patterns appear across time?
- Which places are represented or missing?
- Which people or groups are central?
- How do records cluster or disperse?
- What has been simplified by the data model?
- What assumptions were made during data cleaning?
- What histories become more visible?
- What histories remain hidden?

---

## The workshop example: people, places, and time

The workshop uses a historical dataset connected to University of Edinburgh records.

The live visualisation focuses on two common humanities dimensions:

| Dimension | Workshop example | Possible visual form |
|---|---|---|
| **Place** | Birthplace coordinates or study locations | Map |
| **Time** | Entry year or period of study | Timeline |
| **People** | Individual records | Map markers or data points |
| **Counts** | Number of records per year | Line chart or bar chart |

The current starter visualisation uses:

- **Leaflet** to show locations on a map;
- **D3.js** to group records by year;
- **SVG** to draw a timeline chart;
- **popups** to show additional information on map markers.

This is a useful workshop example because it connects three important questions:

1. **Where** are people connected to?
2. **When** do records appear?
3. **How** can we move between individual records and aggregate patterns?

---

## A useful design question: what, why, and how?

A helpful way to design a visualisation is to ask three questions:

| Question | Meaning | Workshop example |
|---|---|---|
| **What?** | What data do we have? | Records with dates, places, names, and metadata |
| **Why?** | What task or question are we supporting? | Explore where people came from and how entries changed over time |
| **How?** | How should the data be visually encoded? | Map markers for places, a timeline for years, popups for details |

This kind of thinking is associated with Tamara Munzner’s work on visualisation analysis and design:

[Tamara Munzner — Visualization Analysis and Design](https://www.cs.ubc.ca/~tmm/vadbook/)

For a Digital Humanities project, the **why** question is especially important.

A visualisation for exploration may need interaction and detail.  
A visualisation for communication may need annotation and a clearer narrative.  
A visualisation for public engagement may need more context, accessibility, and explanation.

---

## Data types and visual encodings

Before choosing a chart or map, it is helpful to identify the types of data you have.

| Data type | Meaning | Example | Possible encoding |
|---|---|---|---|
| **Quantitative** | Numeric values | Number of records per year | Position, length, size |
| **Temporal** | Dates or time periods | Entry year | Timeline, line chart |
| **Geographic** | Places or coordinates | Birthplace latitude/longitude | Map position |
| **Categorical / nominal** | Named categories | Institution, gender, subject, place name | Colour, shape, grouping |
| **Ordinal** | Ordered categories | Low, medium, high certainty | Ordered colour or size |
| **Relational** | Connections between things | Person-to-person or person-to-place links | Network diagram |

The workshop uses several of these:

- geographic data for the map;
- temporal data for the timeline;
- individual records for markers;
- aggregate counts for the chart.

---

## Visual variables

Visual variables are the visual properties we use to encode data.

Common visual variables include:

- position;
- size;
- shape;
- colour hue;
- colour lightness;
- line width;
- texture;
- orientation;
- opacity.

For example:

| Data feature | Possible visual encoding |
|---|---|
| Entry year | x-position on a timeline |
| Number of records | y-position or line height |
| Birthplace | position on a map |
| Category | colour or shape |
| Uncertainty | opacity, outline, annotation, or separate category |

### Bertin's visual variables

![Bertin's visual variables](./images/visualisation-intro/bertins-visual-variables.png)

*Figure 1. Visual variables describe how data can be encoded visually, such as through position, size, shape, colour, and texture.*

Jacques Bertin’s work on visual variables and graphical semiology is foundational for thinking about how data becomes visual form.

Further reading:

- [Jacques Bertin and cartographic semiology](https://www.mappingasprocess.net/blog/2021/8/20/some-thoughts-on-jacques-bertins-cartographic-semiology)
- [Mackinlay, 1986: Automating the design of graphical presentations of relational information](https://dl.acm.org/doi/10.1145/22949.22950)
- [Financial Times Visual Vocabulary](https://ft-interactive.github.io/visual-vocabulary/)

### Mackinlay's rankings

![Mackinlay's rankings of visual encodings](./images/visualisation-intro/mackinlays-rankings.png)

*Figure 2. Mackinlay’s rankings compare the effectiveness of different encodings for different data types.*



## Maps, timelines, and linked views

This workshop focuses on maps and timelines.

### Maps

Maps are useful when place matters.

They can show:

- birthplaces;
- study locations;
- movement;
- institutional networks;
- regional patterns;
- coverage.

However, maps can also be misleading if the data is incomplete or uncertain.

A map may suggest precision even when the original record is vague. For example, a birthplace may be recorded as a town, region, or country rather than an exact coordinate.

When mapping humanities data, ask:

- How precise are the coordinates?
- Are the places modern or historical?
- Have place names changed?
- Are some records missing location data?
- Does the map over-emphasise geography when another view might be better?

### Timelines

- changes over time;
- clusters of activity;
- gaps in records;
- growth or decline;
- relationships between events and periods.

In the workshop code, D3 groups records by `entry_year` and counts how many records appear in each year.

A timeline can help us move from individual records to a wider historical pattern.

### Linked views

A linked view connects two or more visualisations.

For example:

- clicking a year on the timeline could filter the map;
- hovering over a marker could highlight a record in a table;
- selecting a region could update a chart;
- clicking a category could show only related people.

This is useful when no single chart can show everything clearly.

---

## Interactivity in visualisation

Interactivity allows viewers to explore a visualisation rather than only look at a fixed image.

Common interactions include:

| Interaction | What it does | Workshop relevance |
|---|---|---|
| **Click** | Select an item or open details | Click a map marker to show a popup |
| **Hover** | Show lightweight information | Hover over a chart point to see year/count |
| **Zoom and pan** | Move around a large view | Navigate the Leaflet map |
| **Filter** | Show a subset of the data | Filter by date, category, or location |
| **Highlight** | Emphasise selected items | Highlight records from a chosen year |
| **Brushing and linking** | Connect selections across views | Select a timeline range and update the map |
| **Overview and detail** | Show the whole dataset and local detail | Map overview plus popup detail |

Interactivity should have a purpose.

It is most useful when it helps the viewer:

- inspect details without cluttering the whole page;
- move between overview and detail;
- compare subsets;
- follow their own research question.

It is less useful when it adds complexity without improving understanding.

---

## Humanities data: uncertainty, interpretation, and bias

Humanities datasets often require interpretation before they can be visualised and as is the case for any dataset, pre-processing and tidying are core steps prior to analyses or explorations.

Historical records may include:

- missing values;
- inconsistent spelling;
- variant names;
- uncertain dates;
- ambiguous places;
- changing borders;
- incomplete institutional records;
- categories that reflect historical bias;
- digitisation or transcription errors.

For this workshop, useful questions include:

- Which records have coordinates?
- Which records do not?
- Which places are over-represented?
- Which years have many records?
- Which years have few or no records?
- What has been lost during data cleaning?
- What does the map make visible?
- What does the map make harder to see?
---

## Design principles and common pitfalls

### Useful design principles

A useful way to think about this is:

```text
Domain → Data and task abstraction → Visual encoding → Interaction and implementation
```
1. **Start with the question**
   - What do you want the visualisation to help someone understand?

2. **Know the data**
   - What fields/variables do you have?
   - What is missing?
   - What has been cleaned or transformed?

Some visual encodings are easier to read than others. Cleveland and McGill’s work on graphical perception showed that people tend to judge some visual properties more accurately than others, especially when comparing quantitative values. Position and length are usually easier to compare than area, angle, volume, or colour saturation.

This is why bar charts and line charts are often clearer than more decorative chart forms when precise comparison matters.

3. **Familiarity with domain and specificity**

Domain knowledge also affects design choices. For example:

colours may carry different meanings in different disciplines;
historical categories may need explanation;
place names may be uncertain, contested, or historically variable;
missing data may be meaningful rather than simply a technical problem.

This connects to the first layer of Munzner’s model: characterising the problem in the vocabulary of the domain before moving into technical design.

4. **Choose suitable encodings**
   - Use position and length for numeric comparison where possible (however this is not a universal principle).
   - Use colour carefully, consider accessibility and where colour is applied, for instance with categories, where they become too numerous be careful not to overload with a colour encoding.
   - Avoid making viewers decode too many visual meanings at once.

Note: For maps, tools such as ColorBrewer [https://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3] can help with colour schemes designed for cartographic use.

For web-based visualisations, colour should also be considered alongside accessibility guidance, including sufficient contrast and not relying on colour alone.

5. **Use labels and legends clearly**
   - Explain what colours, sizes, shapes, and axes mean.

6. **Show uncertainty where relevant**
   - Use annotation, categories, opacity, or notes to explain uncertain data.

7. **Avoid unnecessary clutter**
   - Not every data field needs to be visible at once.

Edward Tufte’s writing on “chartjunk” is often used to discuss visual elements that distract from, rather than clarify, the data. The point is not that visualisations must be plain, but that design choices should support meaning.

One solution is to separate views.

Instead of trying to show everything in one visualisation, consider:

a map for place;
a timeline for time;
a table for detailed records;
filters for categories;
popups for individual details;
linked views for exploration.

This is especially relevant to interactive visualisation. Interaction can help reveal detail without placing everything on the screen at once.

Balance **precision** & **expressiveness**

8. **Design for the audience**
   - A domain expert, student, public visitor, and software developer may need different levels of explanation.

### Common pitfalls

| Pitfall | Implications |
|---|---|
| Misleading axes | A chart can exaggerate or hide change |
| Too many colours | Colour becomes confusing rather than helpful |
| Missing labels | Viewers cannot interpret the chart |
| Over-precise maps | Points may imply certainty that the data does not support |
| Ignoring missing data | Absences may be historically meaningful |
| Visual clutter | Too much information can make patterns harder to see |
| Decorative effects | Visual style should not obscure the data |
| Unsupported claims | A visual pattern is not automatically an explanation |

Another common pitfall seen widely is starting with a chosen tool before considering audience, data and the task the visualisation needs to perform. Early reliance on a tool may end up driving the design and then backtracking to adapt rather than working with the research question. 

Further reading:

- [Alberto Cairo — The Truthful Art](https://www.oreilly.com/library/view/the-truthful-art/9780133440492/)
- [Edward Tufte on chartjunk](https://www.edwardtufte.com/notebook/chartjunk/)

---

## Accessibility and inclusive design

A visualisation should be understandable by as many people as possible.

Accessibility is especially important for web-based visualisations because people may view them on different devices, with different needs, and with different assistive technologies.

Consider:

- readable text size;
- sufficient colour contrast;
- not relying on colour alone;
- clear labels and legends;
- keyboard access where possible;
- captions or descriptions for complex visualisations;
- alt text for images;
- plain-language summaries;
- providing the data or a table when appropriate.

For complex charts, maps, or diagrams, a short alt text may not be enough. A longer description near the visualisation can help explain what the viewer should notice.

Further reading:

- [W3C Web Content Accessibility Guidelines WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [W3C WAI: Complex images](https://www.w3.org/WAI/tutorials/images/complex/)
- [GOV.UK: Text descriptions for data visualisations](https://accessibility.blog.gov.uk/2023/04/13/text-descriptions-for-data-visualisations/)

---

## Tools for data visualisation

There are many ways to make visualisations. The right tool depends on your data, your audience, your skills, and your output.

### Tools used in this workshop

| Tool | use cases |
|---|---|
| [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) | Structuring a web page |
| [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) | Styling a page |
| [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) | Adding data loading and interaction |
| [D3.js](https://d3js.org/) | Custom data-driven visualisation on the web |
| [Leaflet](https://leafletjs.com/) | Interactive web maps |
| [GitHub Pages](https://pages.github.com/) | Publishing a static website online |

D3 is useful when you need custom control over marks, scales, axes, layouts, and interactions. D3 has an expansive use case portfolio and can be used in many settings.

Leaflet is useful when the visualisation needs an interactive map.

### Other programming tools

| Tool | Language | Useful for |
|---|---|---|
| [Matplotlib](https://matplotlib.org/) | Python | Static charts and publication figures |
| [Seaborn](https://seaborn.pydata.org/) | Python | Statistical charts |
| [Plotly](https://plotly.com/python/) | Python / JavaScript / R | Interactive charts and dashboards |
| [Bokeh](https://bokeh.org/) | Python | Interactive browser-based visualisations |
| [ggplot2](https://ggplot2.tidyverse.org/) | R | Grammar-of-graphics charts |
| [Tidyverse](https://www.tidyverse.org/) | R | Data cleaning, analysis, and visualisation |
| [Observable Plot](https://observablehq.com/plot/) | JavaScript | Concise exploratory web visualisation |
| [Vega-Lite](https://vega.github.io/vega-lite/) | JSON / JavaScript | Declarative interactive graphics |

### Web development frameworks

For this workshop, we are using a simple static webpage with HTML, CSS, JavaScript, D3, and Leaflet.

Larger projects may use web development frameworks. These are useful when a project needs reusable components, multiple pages, state management, or a more complex interface.

| Framework or library | Useful for |
|---|---|
| [React](https://react.dev/) | Building component-based user interfaces |
| [Vue](https://vuejs.org/) | Building approachable, flexible web interfaces |
| [Svelte](https://svelte.dev/) | Building compiled, component-based web interfaces |
| [Observable Framework](https://observablehq.com/framework/) | Building data apps and reports with JavaScript and Markdown |

A framework is not always necessary. For a smaller projects plain HTML, CSS, JavaScript, D3, and Leaflet are easier to understand and work with.

### No-code and low-code tools

No-code tools are useful for fast prototyping, teaching, and exploratory visualisation.

| Tool | Useful for |
|---|---|
| [RAWGraphs](https://www.rawgraphs.io/) | Turning tabular data into charts without coding |
| [Tableau Public](https://public.tableau.com/) | Interactive dashboards and public visualisations |
| [Flourish](https://flourish.studio/) | Interactive stories, charts, and maps |
| [Datawrapper](https://www.datawrapper.de/) | Clear charts, maps, and tables for publication |
| [Figma](https://www.figma.com/) | Designing interfaces, wireframes, prototypes, layout mockups, and visualisation concepts before coding |
| [Charticulator](https://charticulator.com/) | Custom chart layouts without traditional coding |

These tools can be a good route if the goal is to communicate quickly rather than build a fully custom web visualisation.

---

## Digital Humanities examples and inspiration

The following examples are useful for thinking about how visualisation can support humanities research.

### Mapping the Republic of Letters

[Mapping the Republic of Letters](https://republicofletters.stanford.edu/) is a major Digital Humanities project that explores correspondence networks across space and time.

It is useful for thinking about:

- correspondence;
- networks;
- geography;
- historical movement;
- distant reading;
- the relationship between maps and archives.

### Kindred Britain

[Kindred Britain](http://kindred.stanford.edu/) is an interactive network visualisation of relationships among thousands of British historical figures.

It is useful for thinking about:

- networks;
- biography;
- cultural history;
- interaction;
- public-facing Digital Humanities design.

Further information:

[Kindred Britain notes and credits](https://kindred.stanford.edu/notes.html)

### W. E. B. Du Bois's data portraits

W. E. B. Du Bois and collaborators created powerful hand-drawn data visualisations for the 1900 Paris Exposition.

These works are useful for thinking about:

- visualisation and social justice;
- design and argument;
- colour and form;
- historical data storytelling;
- visualisation before computers.

[Library of Congress: W. E. B. Du Bois data visualizations](https://www.loc.gov/pictures/search/?st=grid&co=anedub)

### Dear Data

[Dear Data](https://www.dear-data.com/theproject) is a hand-drawn data project by Giorgia Lupi and Stefanie Posavec.

It is useful for thinking about:

- personal data;
- drawing as analysis;
- slow visualisation;
- data as lived experience.

### Data Sketches

[Data Sketches](https://www.datasketch.es/) by Nadieh Bremer and Shirley Wu is a collection of creative web-based visualisation experiments.

It is useful for thinking about:

- expressive visualisation;
- interaction;
- storytelling;
- custom web design;
- the creative possibilities of D3.

---

## Getting started with your own visualisation project

When starting your own visualisation, try this sequence.

### 1. Define the question

Ask:

```text
What do I want someone to understand, explore, or question?
```

### 2. Inspect the data

Ask:

```text
What fields/variables do I have?
What types of variables are they?
What do I want to ask of the data?
Who is my audience?
What is missing?
What has been cleaned or transformed?
```

### 3. Identify the data types

Ask:

```text
Which fields are dates?
Which fields are places?
Which fields are categories?
Which fields are numbers?
Which fields describe relationships?
```

### 4. Choose a visual form

| If your question is about... | Think about... |
|---|---|
| Change over time | Timeline, line chart, area chart |
| Place | Map |
| Relationships | Network diagram/Sankeys/Connections
| Categories | Bar chart, grouped chart |
| Parts of a whole | Stacked bar chart, treemap, carefully used pie chart |
| Distributions | Histogram, dot plot, box plot |
| Individual records plus detail | Map markers, table, popups, linked views |

### 5. Sketch before coding

A quick sketch can help you decide:

- what should be visible first;
- what should be interactive;
- where labels should go;
- whether a map is actually needed;
- whether a chart is too crowded.

Further reading:

[Five Design-Sheet Methodology](https://doi.org/10.1109/TVCG.2011.199)

### 6. Build a small version first

Start with a simple version.

For example:

```text
Load the cleaned data → show one map marker → show all map markers → add popups → add a timeline → link the views
```

A small working version is easier to improve than a complex broken version.

### 7. Add explanation

A visualisation is stronger when it includes:

- a title;
- labels;
- a short explanation;
- a note about the data source;
- a note about missing or uncertain data;
- accessible text descriptions;
- clear instructions for interaction.

---

## Further reading

### Core visualisation theory

- [Royal Statistical Society: Best Practices for Data Visualisation](https://royal-statistical-society.github.io/datavisguide/)
- [Tamara Munzner — Visualization Analysis and Design](https://www.cs.ubc.ca/~tmm/vadbook/)
- [Tamara Munzner — Research group](https://www.cs.ubc.ca/~tmm/)
- [Alberto Cairo — The Truthful Art](https://www.oreilly.com/library/view/the-truthful-art/9780133440492/)
- [Edward Tufte — Chartjunk](https://www.edwardtufte.com/notebook/chartjunk/)
- [John Mackinlay, 1986 — Automating the design of graphical presentations](https://dl.acm.org/doi/10.1145/22949.22950)
- [Johanna Drucker - Digital Humanities Quarterly - Humanities Approaches to Graphical Display](https://dhq.digitalhumanities.org/vol/5/1/000091/000091.html)

### Articles and write-ups on visualisation

- [UW Interactive Data Lab](https://medium.com/@uwdata/next-steps-for-data-visualization-research-3ef5e1a5e349)

### Visual vocabularies and chart choice

- [Financial Times Visual Vocabulary](https://ft-interactive.github.io/visual-vocabulary/)
- [Data Visualisation Catalogue](https://datavizcatalogue.com/)
- [Chart Maker Directory](https://chartmaker.visualisingdata.com/)
- [Datawrapper Academy](https://academy.datawrapper.de/)

### Web visualisation tools

- [D3.js](https://d3js.org/)
- [Leaflet](https://leafletjs.com/)
- [Observable Plot](https://observablehq.com/plot/)
- [Vega-Lite](https://vega.github.io/vega-lite/)
- [Plotly Python](https://plotly.com/python/)
- [Bokeh](https://bokeh.org/)

### No-code and low-code tools

- [RAWGraphs](https://www.rawgraphs.io/)
- [Tableau Public](https://public.tableau.com/)
- [Datawrapper](https://www.datawrapper.de/)
- [Flourish](https://flourish.studio/)

### Digital Humanities examples

- [Mapping the Republic of Letters](https://republicofletters.stanford.edu/)
- [Kindred Britain](http://kindred.stanford.edu/)
- [Kindred Britain notes and credits](https://kindred.stanford.edu/notes.html)
- [W. E. B. Du Bois data visualizations, Library of Congress](https://www.loc.gov/pictures/search/?st=grid&co=anedub)
- [Dear Data](https://www.dear-data.com/theproject)
- [Data Sketches](https://www.datasketch.es/)

### Visualisation Labs & Teams (non-exhausive)
- [UCLAB](https://uclab.fh-potsdam.de/)
- [uw Interactive Data Lab](https://idl.uw.edu/)
- [VisHub - University of Edinburgh](https://vishub.net/)
- [Data Visualisation Society](https://www.datavisualizationsociety.org/)
- [giCentre](https://www.gicentre.net/)
- [Georgia Tech Visualisation Lab](https://vis.gatech.edu/)
- [MIT visualisation Lab](https://vis.mit.edu/)

### Community initiatives

- [Makeover Monday](https://makeovermonday.co.uk/)
- [TidyTuesday](https://github.com/rfordatascience/tidytuesday)
- [Information is Beautiful](https://informationisbeautiful.net/)
- [VisHub Edinburgh](https://vishub.net/)

### Design, critique, and storytelling

- [Nightingale: Journal of the Data Visualization Society](https://nightingaledvs.com/)
- [Data Visualization Society](https://www.datavisualizationsociety.org/)
- [The Pudding](https://pudding.cool/)
- [Visual Cinnamon](https://www.visualcinnamon.com/)
- [FlowingData](https://flowingdata.com/)
---

## License

This workshop resource is intended for teaching and learning.

Workshop resource created for the DH-RSE Summer School, visualisation.

[![License: CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc/4.0/)







