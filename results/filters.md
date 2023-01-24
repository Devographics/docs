# Filters

## Accessing Filters

Filters can be accessed by clicking the Filters icon in a chart's side tabs when it's available. Note that not all chart types support filters. 

<img width="700" alt="Accessing filters" src="https://user-images.githubusercontent.com/358832/214194870-b1ba8a0d-8447-4d06-8c18-df0ec76c50b3.png">

## Filters Mode

Filters are actually divided into two modes: regular filters mode, and "facet" mode. 

### The Filters Panel

When you first access the Filters panel, you will be presented with a range of control that let you define what data series you want to compare. 

#### UI Overview
<img width="700" alt="The Filters panel" src="https://user-images.githubusercontent.com/358832/214195202-f934b051-3982-4129-9a6f-da37fb5aaecf.png">

1. **Mode Switch**: switch between Filters and Facet mode.
2. **Filter Presets**: click any preset to auto-fill the data series.
3. **New Preset**: save your current filters definition as a new preset that you'll be able to easily reuse across all charts.
4. **Default Series Toggle**: toggle the default series (the "default" chart representing the entirety of all survey respondents) on and off.
5. **Add Series**: add a new data series (more on this below).
6. **GraphQL Query**: get the raw GraphQL query corresponding to the current set of filters, which you can [use with our GraphQL API](https://graphiql.devographics.com/).
7. **Update Chart**: apply current filters and update the chart. 

#### How-To

The easiest way to get started is to **pick a preset**, such as Gender, to auto-populate the data series below. Then, click **Update Chart** to update the chart with your new filtered data. 

### Defining Data Series

Alternatively, you can also define your own data series. 

#### UI Overview

<img width="700" alt="Defining data series" src="https://user-images.githubusercontent.com/358832/214195644-4b507143-6163-41c2-9cd6-7d9c423bc1c5.png">

1. **Year Picker**: pick the year you want to fetch data for. Note that some year might not have data. 
2. **Delete Series**: delete this data series.
3. **Field Picker**: pick the field (in other words, the survey question) that you want to filter by.
4. **Operator Picker**: pick one of: is, is one of, is not one of. 
5. **Value Picker**: pick the value to match.
6. **Delete Condition**: delete this condition from the current series. 
7. **Add Value**: when using the `is one of` or `is not one of` operators, this lets you add multiple values to the condition.
8. **Delete Value**: delete current value from the condition. 
9. **Add Filter**: add another filter to the series. 

#### How-To

If you've used a preset, begin by clearing the filters by click the **Delete Series** button until no series remain. Then, click **Add Series**, which will create a new data series initialized with the first field in the list.  

You can modify a series by adding more filters to build complex conditions. Note that within a series, filters are added using the `AND` operator. In other words, data must match the **intersection** of all defined filters. For example, selecting `country is United States` and `gender is man` will match all United States men. There is currently no way to define `OR` filters (""). 

You can add **up to four** data series. 

### Visualizing Your Filters

Depending on the chart, your data series will be displayed in either **Combined Mode** or **Multiple Mode**. 

#### Combined Mode

<img width="700" alt="Combined mode" src="https://user-images.githubusercontent.com/358832/214197395-7c22c78d-5069-4185-9e90-102f9bb4f95e.png">

In combined mode, your data series are all displayed on the same chart. By default, the chart will switch to representing the "% of question respondents" unit. For example, a values of 10% for `gender is women` in bracket "1-2 years of experience" means that 10% of women respondents fell in that bracket. It does **not** mean that 10% of respondents with 1-2 years of experience are women (this is what Facet Mode is for, but more on that later). 

## Facet Mode
