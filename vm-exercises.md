# Virtual Machine (VM) Exercises

## :information_source: Read this before getting started
- The goal of exercises in case study is for learners to apply what was learned in the previous courses to new problems or situations. This is best pedagogical practice for retaining and building skills.
- We can only run free versions of BI software in our virtual machine exercises. In the case of Power BI, make sure the exercises can run on [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) without any additional paid products. 
- Unsure what the scope of an exercise should be? Here's an [example](https://campus.datacamp.com/courses/case-study-analyzing-customer-churn-in-tableau/exploratory-analysis-1?ex=4) from the Case Study: Analyzing Customer Churn in Tableau. The first chapter of most DataCamp courses are free, so take a look at our [BI courses](https://learn.datacamp.com/courses?technologies=Tableau&technologies=Power%20BI) to get a feel for how we assess and guide learners in **case studies**.

## 1st VM Exercise

### Dataset

- [X] Add datasets used to the `datasets/` folder

### Files

- [X] **Initial**: Add file to the `exercises/`  folder with the name `ex-1-intial.twbx` or `ex-1-intial.pbix`, depending if you are auditioning for a Tableau or Power BI course.
- [X] **Solution**: Add file to the `exercises/`  folder with the name `ex-1-sol.twbx` or `ex-1-sol.pbix`

### Learning Objective

- (Calculations): Ability to calculate KPIs using date and logical functions.
- (Visualization): Ability to visualize insights as a 100% stacked area chart.
- (Business): Understanding of the importance of Shipment Timeliness as a KPI in Supply Chain.

### Context

**Are we there yet? Visualizing the timeliness of our shipments.**

Timely shipment of our goods is critical to the commercial success of our company. It is heavily impacted by various factors and is a good KPI for the follow-up of the efficiency of our Supply Chain.

In this exercise we will learn how to calculate and visualize this KPI!

_Click on File > Open ... and opent the workbook `shipment.twbx`_.

### Steps to be executed by the student (max 6)

**STEP 1:**

Create a continuous `Order Date` and `Shipment Date` dimensions based on available fields `Order Day`,`Order Month`,`Order Year` and `Shipment Day`,`Shipment Month`,`Shipment  Year`.

**HINT:**

Use function `MAKEDATE()` and convert the two newly created dimensions to continuous by right-clicking on them in "Data Pane".

**STEP 2:**

Visualize the monthly `Order Item Quantity` volumes and present it as a line chart using a continuous date dimension.

**HINT:**

- Select both data fields in "Data Pane" and select the line chart using "Show Me".
- Adapt your date dimension in the "Columns" to display months.

**STEP 3:**

In our dataset we already have the `Shipping Days - Scheduled` dimension, but not the actual shipping days! Create `Shipping Days - Actual` by deducting the shipment date from the order date.

**HINT:**

Create a new calculated field which is a subtraction of two respective dates: `[____]-[____]`.

**STEP 4:**

Finally, we need to calculate `Shippment Delay` which will be a conditional statement based on the difference between the actual and scheduled shipment date: if it's negative then it's "Before Schedule", if on time then "On Schedule", otherwise split it into "Delay (<5 days)" and "Delay (>=5 days)" based on the correct logic statements.

**HINT:**

Your calculation should look like:
`IF [____]-[____]<0 THEN '....'
ELSEIF [____]-[____]=0 THEN '....' 
ELSEIF[____]-[____]<5 THEN '....'
ELSEIF [____]-[____]>=5 THEN '....' END`

**STEP 5:**

- Visualize the data as a colored 100% stacked area chart, split by `Shipment Delay`
- Exclude the orders which were not yet shipped and order the `Shipment Delay` in a logical way.

**HINT:**

- Filter out the null `Shipment Delay`.
- Convert the graph to area chart, colour it by `Shipment Delay dimension` and apply the correct Quick Table calculation on the measure in the "Rows". Pay attention to the correct direction of the calculation.
- To order the stacked areas, drag the items on the legend in the right order.

### Exercise question:
- **Question**: What was the % of "Delay (5>= days) Order Item Quantity in October 2017?
- **Answer**: 13.66%

### End goal:

![image](https://user-images.githubusercontent.com/95186405/224835001-8e98cd46-c5be-43bd-8a1a-9b62905baaa4.png)

## Finalized Workbook

### Files
- [X] You can upload your final workbook in the exercises folder as `ex-final-sol.twbx` or `ex-final-sol.pbix`.

### Explanation & Description
- Understanding of various Tableau functions and the need to create a set of calculations before arriving to a meaningful KPI. 
- Understanding of the applications of area chart in visualization of the evolution.
- Ability to use Quick Table Calculations.
- Ability (understand the need) to order various dimension in a logical sense in order to enhance the meaningfullness of the chart.
