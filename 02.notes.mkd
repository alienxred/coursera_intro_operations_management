# 02 Process Analysis

In this module, you'll learn how to identify key elements of process analysis:
*flow rates (throughput)*, and *flow times*, how to uncover bottlenecks, how to
optimize labor and *inventory*, and how to handle the complexities of multiple
flow units. 

At the end of this module, you'll be able to break down operations into
*processes* which can then be improved to *maximize profits and efficiency*.

## 02.01 The 3 Measures: Flow Rate, Inventory, and Flow Time

### Subway - Sitting in Front of the Store

![](images/02-04-subway-sitting-store.png)

Draw a graph of Customers (y) vs Time (x)
- Cumulative Inflow = point when customer enters
- Cumulative Outflow = point when customer leaves
- **Inventory** = Vertical distance in (Cumulative Inflow - Cumulative Outflow)
- **Flow Time** = horizontal distance in (Time to serve the customer)

### The 3 Basic Measures

- *Flow rate / throughput*: number of flow units going through the process per
  unit of time
  - = (Customer/hour)
- *Flow Time*: time it takes a flow unit to go from the beginning to the end of
  the process
  - horizontal dist in 2 lines
- *Inventory*: the number of flow units in the process at a given moment in
  time
  - vertical dist in 2 lines
- *Flow Unit*: What we want to measure e.g. Customer or Sandwich

|       | Immigration department  | Champagne             |
| ----- | ----------------------- | --------------------- | 
| FU  = | Applications            | Bottle of champagne   |
| FT  = | Approved/rejected cases | Bottles sold per year |
| FT  = | Processing time         | Time in the cellar    |
| Inv = | Pending cases           | Content of cellar     |

|       | MBA Program      | Auto company   |
| ----- | ---------------- | -------------- |
| FU  = | Student          | Car            |
| FT  = | Graduating class | Sales per year |
| FT  = | 2 years          | 60 days        |
| Inv = | Total population | Inventory      |
 

### Quiz

Between the hours of noon and 1pm, 70 customers enter ACME pizza and 60 leave
with pies in hand. What is ACME's inventory of customers at 1pm assuming it was
zero at noon?
- 2
- 5
- 10
- 20

### Summary

**Inventory** = # flow units in system

**Flow rate** = # flow units going through the system

**Flow Time** = total time for flow unit to go from beginning to end

Inventory happens whenever there is a mismatch between supply and demand

## 02.02 Finding the Bottleneck

3 Steps
- Create a process flow diagram
- Find the bottleneck of the process and determine the maximum flow rate
- Conduct a basic process analysis 3. Conduct a basic process analysis

### Example Subway 

![](images/02-10-subway-inside.png)

**Processing Times** = Unit of time / Flow Unit 
- e.g. Station 1 = 37 secs/customer
- e.g. Station 2 = 46 secs/customer
- same as **activity times**

Image above
- need 3 workers
- understand activities to make a sandwich
- can calculate total processing times

**Process Flow Diagram**

![](images/02-12-drawing-process-flow.png)

- arrow = flow of unit
- box = activity i.e. 37s/unit processing time for station 1
- triangle = flow unit waiting

### Basic Process Vocabulary

- **Processing times**: how long does the worker spend on the task?
  - i.e. 46 secs/cust * 3600 sec/hour = 78 customers / hour
- **Capacity** = 1/processing time: how many units can the worker make per unit
  of time
  - If there are m workers at the activity: Capacity=m/activity time
- **Bottleneck**: process step with the _lowest capacity_
- **Process capacity**: capacity of the bottleneck
- **Flow rate** = Minimum{Demand rate, Process Capacity)
- **Utilization** = Flow Rate / Capacity
- **Flow Time**: The amount of time it takes a flow unit to go through the process
- **Inventory**: The number of flow units in the system

### Example spreadsheet for Subway example above 

| Resource           | Station 1 | Station 2 | Station 3 | Units      |
| ------------------ | --------- | --------- | --------- | ---------- |
| Proc Time          | 37        | 46        | 37        | sec/unit   |
| Capacity (1/ProcT) | 0.027027  | 0.021739  | 0.027027  | units/sec  |
| Capacity/Hour      | 97.2973   | 78.26087  | 97.2973   | units/hour |
| Proc Capacity      |           |           |           |            |
| Demand             | 50        | 50        | 50        |            |
| Utilization        | 0.513889  | 0.638889  | 0.513889  |            |

### Quiz

The flow rate of a process is always less or equal to the capacity of the process
- true
- false
- It depnds on the number of resources
- Cannot be determined

### Summary

Introduced lots of vocabulary.

Allow to calculate flow rate without viewing process in action.

We can now predict the flow rate

## 02.03 Labor Cost and Labor Utilization 

### Review of Capacity Calculations

![](images/02-15-labor-productivity-measures.png)

**Capacity** = 

    # Resources 
    ---------------
    Processing Time

**Process Capacity** = ``Min{Capacity}``

**Flow Rate** = `Min{Demand, Capacity}`

**Utiliziation** = 

    Flow Rate
    ---------
    Capacity

### Labor Productivity Measures

**Cycle time CT** = 

       1
    _________
    Flow Rate

**Direct Labor Content** = `p1 + p2 + p3 + p4` (total green in graph)

If one worker per resource:
**Direct Idle Time** = `(CT-p1) + (CT-p2) + (CT-p3)`

**Average labor utilization** = 

              labor content 
    ----------------------------------
    (labor content + direct idle time)

**Cost of direct labor** = 

    Total wages / time
    ------------------
    Flow rate   / time

### Example: Assembly Line with Six Stations

![](images/02-16-example-assembly-line-with-six-stations.png)


| Station         | 1   | 2   | 3   | 4   | 5   | 6   |  Measure  |
| --------------- | --- | --- | --- | --- | --- | --- | --------- |
| Processing Time | 3   | 5   | 2   | 3   | 6   | 2   |  min/unit |
| Capacity        | 0.3 | 1/5 | 1/2 | 1/3 | 1/6 | 1/2 |           |
| Proc Capacity   | 1/6 |     |     |     |     |     |           |
| Flow Rate       | 1/6 |     |     |     |     |     |           |
| Cycle Time      | 6   |     |     |     |     |     |           |
| Idle            | 3   | 1   | 4   | 3   | 0   | 4   |           |
| Total Idle Time | 15  | 1   | 4   | 3   | 0   | 4   |           |
| Labor content   | 21  |     |     |     |     |     |           |
| labor utilization | 0.58333
| Utilization     | 0.5 | 0.833 | 0.333 | 0.5 | 1 | 0.333 |
| Avg Utilization | 0.583333 

Assuming wages = $6/hr, Cost of Direct labor = (6 * 20) / 10 = $12/unit 

### Quiz

A process has four activities with processing times of 3, 2, 5, and 1 minutes per unit respectively. What is the direct labor content?

### Example from automative company

![](images/02-18-role-of-labor-costs-in-manufacturing-auto-industry.png)

While labor costs appear small at first, they are important
- look relative to value added look relative to value added
- role up costs throughout the value chain

Implications
- also hunt for pennies (e.g. line balancing)
- spread operational excellence through the value chain

### Summary

2 measures: labor utilization vs labor cost 

Firms can hide labor by relying on suppliers (i.e. outsourcing). e.g. Apple outsourcing to FoxCon. Looks good on Apple's books due to lower labor cost passed on to FoxCon.

## 02.04 Little’s Law

*Inventory* = Cumulative Inflow - Cumulative Outflow

*Little's Law*: Inventory (I) = `Flow Rate (R) * Flow Time (T)`

![](images/02-20-three-key-metrics.png)

**Flow Rate** = slope of the graph above on outflow

Customers (I) = Cust/Time (R) * Time (T)

Implications:
- Can only control for 2 of (I,R,T).
- Hold throughput constant: Reducing inventory = reducing flow time

Given two of the three measures, you can solve for the third:
- Indirect measurement of flow time: how long does it take you on average to
  respond to an email?
  - You write 60 email responses per day
  - You have 240 emails in your inbox

    240 = 60 * T
    T = 4 days 

i.e. takes an average of 4 days to respond to an email

### Examples for Little's Law Appliations

In a large Philadelphia hospital, there are 10 births per day.
- 80% of the deliveries are easy and require mother and baby to stay for 2 days
- 20% of the cases are more complicated and require a 5 day stay

What is the average occupancy of the department?

    R = 10 babies/day
    T = 80% * 2 +  20$ * 5  = 2.6 days

    I = R * T
      =  10 babies/day * 2.6 days = 26 babies

### Quiz

In a pizaa restaurant, on average, customers order 30 pizzas an hour. A pizza
needs to stay in the oven for 10 mintues. How many pizzas will there be, on
average, in the oven?
- 10
- 30
- 180
- 5

### Summary

- Not an empirical law - requires heavy math to optimize
- Robust to variation, what happens inside the black box
- Deals with **averages** – variations around these averages will exist
- Holds for every time window
- Shown by Professor Little in 1961

## 02.05 Inventory Turns / Inventory Costs

**REDO THIS: Doesn't make sense**

### Dell vs Compaq

| Dell                           | Compaq                         |    
| ------------------------------ | ------------------------------ | 
| Inventory = $ 391 M            | Inventory = $ 2.003 B          | 
| Cost of Goods = $20 B /yr      | Cost of Goods = $ 25.264 B /yr |
| T = (391/20000) * 365 = 7 days | T = 365 * (2.003/25.263) = 29  |
| Inv Turns = 1/T = 51           | Inv Turns = 1/T = 12           | 

Make sure to use **COGS** in this calculation and not revenue

**Inventory Turns** = `COGS / Inventory`

![](images/02-26-inventory-turns-at-dell.png)

Started with low inventory turn. In the 90s, optimized significantly.

2001 was the tech bubble.

More recent due to change in the business model incl. new manufacting e.g. TVs
etc.

### Inventory Turns in Retailing and Its Link to Inventory Costs

![](images/02-27-inventory-turns-in-retailing.png)

**Per Unit Inventory costs** = 

    Annual inventory costs 
    ----------------------
      Inventory turns

Annual inventory costs = cost to warehouse an item

Retailer A: per unit Inv Cost = 30% / 4 = 7.5%

Retailer B: per unit Inv Cost = 30% / 8 = 3.75%

Retailer B has dramatic competitive advantage just in per unit inventory cost.

Powerful metric to measure how well you're using inventory capital.

## 02.06 Make to Stock vs Make to Order | Reasons for Inventory

While we want to be lean, there are reasons to hole inventory despite the
holding cost.

5 reasons for inventory => 5 reasons for **longer flow time**

### Simple Process Flow - A Food Truck

Every five minutes:
- You get 0, 1, or 2 orders with equal probability
- You have a capacity of 0, 1, or 2 with equal probability
- It is not possible to make a sandwich before the order
- Customers are not willing to wait

=> How many sandwiches will you sell per five minute slot?

    R = Min{D, Cap} = 1 (this is misleading)

Variability will be a key factor in *waiting time*

| Scenario | D | Cap | R   | 
|--------- | - | --- | --- | 
|  A       | 0 | 0   | 0   | 
|  B       | 0 | 1   | 0   | 
|  C       | 0 | 2   | 0   | 
| -------- | - | --  | --- | 
|  D       | 1 | 0   | 0   | 
|  E       | 1 | 1   | 1   | 
|  F       | 1 | 2   | 1   | 
| -------- | - | --  | --- | 
|  G       | 2 | 0   | 0   | 
|  H       | 2 | 1   | 1   | 
|  I       | 2 | 2   | 2   | 
| -------- | - | --  | --- | 
| Avg      | 1 | 1   | 5/9 | 

**Buffer or Suffer** := in a system where we cannot buffer inventory, flow rate
will suffer
- decouples supply from demand
- By allowing for inventory, we can have a higher flow rate

Buffering is easier in production settings than in services (make to order vs
make to stock)
- Preview two different models: Queue and Newsvendor

### Difference Between Make-to-Order and Make-to-Stock - McDonald's vs Subway

| McDonald’s (Make-to-Stock)             | Subway (Make-to-Order)          |   
| -------------------------------------- | ------------------------------- |
| 1. Make a batch of sandwiches          | 1. Customer orders              |
| 2. Sandwiches wait for customer orders | 2. Customer waits for sandwich  |
| 3. orders filled immediately           | 3. orders filled with delay     |
| => Sandwich waits for customer         | => Customer waits for sandwich  |           

Which approach is better? 

**Make-to-Stock** advantages include:
- Scale economies in production
- Rapid fulfillment (short flow time for customer order) 

**Make-to-Order** advantages include:
- Fresh preparation (flow time for the sandwich)
- Allows for more customization - you can hold all versions of a sandwich in
  stock
- Produce exactly in the quantity demanded
- longer flow time for customer order

### Quiz

Suppose a pizza resturant wants ot make pizzas to order. Which of the following
actions would make their make-to-order system look a little more like a
make-to-stock-system?
- Reduce the time to make a pie so that customers do not wait as long
- Standardize the size and saucing (white/red) of offered pizzas in order to
  pre-make basic pies
- Prohibit orders for multiple pies to reduce the variability of order size
- none of the above

### Five Reasons for Inventory

**Pipeline inventory**: you will need some minimum inventory because of the flow time >0
- direct result of little's law I = R * T
- e.g. wine sales that need to be held for at least 2 years

**Seasonal inventory**: driven by seasonal variation in demand and constant capacity
- e.g. christmas sales spike

**Cycle inventory**: economies of scale in production (purchasing drinks)
- e.g. purchasing a 6-pack for home consumption instead of going to store for
  each single bottle 

**Safety inventory**: buffer against demand (Mc Donald’s hamburgers)
- safety stock to ensure inventory never runs out

**Decoupling inventory/ buffers**: buffers between several internal steps
- e.g. don't want to run out of lettuce when making burgers

### Examples of Demand Waiting for Supply

Service Examples
- ER Wait Times: 58-year-old Michael Herrara of Dallas died of a heart attack
  after an estimated 19 hours in the local Hospital ER. Some ER’s now post
  expected wait times online / via Apps
- It takes typically 45 days do get approval on a mortgage; Strong link between
  wait times and conversion
- Waiting times for drive-through at McDonald's: 159 seconds; Long queues deter
  customers to join

Production Examples
- Buying an Apple computer
- Buying a Dell computer
  - => Make to-order vs Make-to-Stock

### Summary

Inventory guides processes (supply and demand mismatches)

make-to-stock looks fast to the customer but may be slow internally

## 02.06 Multiple Flow Units

### Processes with Multiple Flow Units

![](images/02-35-processes-multiple-flow.png)

Finding the flow rate is more complex.

Approach 1: Adding-up Demand Streams to calculate total flow

| Resources | Capacity  | F Dem | Reg Dem | EZ Dem | Total | Dem/Cap |
| --------- | --------- | ----- | ------- | ------ | ----- | ------- |
| File      | 1/3       | 3     | 11      | 4      | 18    | 18/20
| Foreign   | 6         | 3     |         |        | 3     | 3/6
| D1        | 12        | 3     | 11      |        | 14    | 14/12 
| D2        | 15        |       |         | 4      | 14    | 4/15
| Print     | 30        | 3     | 11      | 4      | 18    | 18/30

- D1 has highest implied utilization (14/12) i.e. **bottleneck**
- Dem/Cap = **Implied Utilization**

Approach 2: A Generic Flow Unit ("Minute of Work")

| Resources | Min Avail | F Dem  | Reg Dem | EZ Dem | Total | Impl Util |
| --------- | --------- | -----  | ------- | ------ | ----- | ------- |
| File      | 60  mins  | 3 * 3  | 11 * 3  | 4 * 3  | 54 m  | 54/60
| Foreign   | 120       | 3 * 20 |         |        | 3     | 60/120
| D1        | 180       | 3 * 15 | 11 * 15 |        | 14    | 210/180 
| D2        | 120       |        |         | 4 * 8  | 14    | 32/120
| Print     | 60        | 3 * 2  | 11 * 2  | 4  * 2 | 18    | 36/60

- For Demand, Use min/app in each step
- Total = mins of work / hour
- **Bottleneck** is the same (D1)

**Note** Implied Utilization results are the same in both approaches

2nd approach gives more flexibility

### Processes with Attrition Loss

Example of script reviews for TV season.

![](images/02-39-processes-attrition-loss.png)

Only 2 scripts make it to "New Series"

Misleading to look at capacity to find the bottleneck (min{capacity, demand})

Better way:
1. Flow
2. Cap
3. Implied Utilization = flow / capacity (_unlike the previous example_)

Other examples where bottleneck calculation is more complex:
- underwriting
- assembly process with quality issues


### Steps for Basic Process Analysis with Multiple Types of Flow Units

1. For each resource, compute the number of minutes that the resource can
   produce
2. Create a process flow diagram, indicating how the flow units go through the
   process the process
3. Create a table indicating how much workload each flow unit is consuming at
   each resource
4. Add up the workload of each resource across all flow units Add up the
   workload of each resource across all flow units.  
5. Compute the implied utilization of each resource as

                            Result of Step 3 
    *Implied utilization =  ----------------
                            Result of Step 1

The resource with the highest implied utilization is the bottleneck

Note: you can also find the bottleneck based on calculating capacity for each
step and then dividing the demand at this resource by the capacity

## Review of Process Analysis

### Unfusion US

Infusion US is a startup that offers powerful and energiing infusions in a
non-hospital setting for competitive athletes (just electrolytes, no doping!).
The service process includes five activities that are conductind in the
sequence described below. (The time requried for each activity is shown in
parantheses): 
- Activity 1: (7 mins) Welcome a patient and explan the procedure 
- Activity 2: (13 mins) Take vitals, insert IV, and take blood
- Activity 3: (12 mins) Mix infusion treatment
- Activity 4: (30 mins) Chemo infusion
- Activity 5: (5 mins) Debrief the patient

Three nurses (S1, S2, S3) offer the services in a worker-paced line. The
assignment of activities to nurses is the following:
- S1 does Activitiy 1 and Activity 2
- S2 does Activitiy 3
- S3 does Activitiy 4 and Activity 5
Assume that there exists unlimited demand and that the process only admits patients at the rate of the bottleneck.

**IU1** Which nurse is the bottlneck of the process?

Capacity:
- S1 = 1/20
- S2 = 1/12
- S3 = 1/35

Bottleneck = S3 (lowest capacity)

**IU2** What is the process utilization (ie the utilization of the bottleneck resource)?

S3 Process Utilization = 100%

**IU3** What is the utilization of nurse 2?

U = FR / Cap = (1/35) / (1/12) = 12/35

**IU4** What is the cycle time (in minutes)?

CT = 1 / FR = 1 / (1/35) = 35 mins/customer

**IU5** What is the idle time per unit at nurse 1 (in minutes)?

IT = CT - p1 = 35 - 20 = 15 mins 

**IU6** What is the average labor utilization across all three nurses?

LU = (20 + 12 + 35)  / ( (20 + 12 + 35) + (15 + 23) ) = 67 / 105

**IU7** What are the costs of direct labor associated with serving one patient?
- assume a wage rate of $30 per hour for Nurses 1 and 2 and $60 for nurse 3
- assume workers are paid regardless of whether they are busy or idle

Cost DL = = $120/hr / [ (1/35 cust/hr) * (60 mins/hr) ] = $70/customer 

### Ruhpolding

Ruhpolding is a village in the German Alps. Given its enormous populatiry among
the Swiss, German, Austrian, and Italian skiers, all of its beds are always
booked in the winter season and there are 1200 beds in the village. On average,
skiers stay in Ruhpolding for 10 days.


**Qn 1.** How many new skiers are arriving on average in Ruhpolding every day? 

I = R * T 

I = 1200 skiers

T = 10 days

R = I / T = 120 skiers/day

**Qn 2.** A study done by the largets hoetle in the village has shown that
skiers spend on average $50 per person on the first day and $30 each additional
day in local restaurants. The study also forecasts that the average length of
stay for the 2010/2011 season will be reduced to five days. What will be the
impact on revenues of local restaurants compared to last year (when skiers sill
stayed for 10 days)? Assume that hotles continue to be fully booked! Express
your answers in $'s per day.

10 day R = 120 skiers/day

10 day Revenue = 120 * 50 + 1080 * 30 = $38400 / day

5 day R = 1200 / 5 = 240

5 day revenue = 240 * 50 + 960 * 30 = $40800 / day

Diff = 40800 - 38400  = $2400 / day

###  Summer's Sweets

Summer's Sweets is a small chain of gelato stores in E. North Carolina. In 2009
the company's revenue was $4.3M and its cost of sales was $2.6M. Assume 52
weeks and 365 days per year.

**SS1** Summer keeps only 4.5 days of supply of inventory on avg b'se much of
her inventory is gelato and fresh squeezed orange juice, both of which have a
short shelf life. What is his annual inventory turns?

Flow Time (T) = 4.5 days

Turns = 1 / T = 1 / 4.5 days * 365 days/yr = 81.4 (yearly) 

i.e. turning over inventory 81.4 times per year

**SS2** Given that he has 4.5 days of supply of inventory on average, how much
inventory does summer have on average (in $s)?

T = I/COGS * 365

4.5 = I / 2.6M * 365

I = (4.5 / 365) * 2.6M = $32054

### Dept of Motor Vehicles

To obtain your first drivers license you must successfully ocmplete several
activities. First you must produce the appropriate identification. Then you
must pass a written exam. Finally you must pass the road exam. At each of these
steps 1%, 15%, 30% of drivers license hopefuls fail to fulfill the step's
requirements. You are only allowed to take the written exam if your
identification is approved and you are only allowed to take the road test if
you have passed the written exam.

The average daily number of driver's license applicants is 400 people. Each
step takes 5, 3, and 20 minutes. Currently the DMV staffs 4 people to process
license applications, 2 to administer written exams, and 15 to judge the road
exam. DMV staff work 8 hours per day

**DMV1** How many liense applications would the DMV process each day if it had
unlimited capacity?

F1 (Id) = 400 * 99% = 396

F2 (exam) = 396 * 85% = 336.6

F3 (road) = 336.6 * 70% = 235.62

**DMV2** Which stage is the bottleneck according to the current staffing plan?

Capacity: (480 mins in 8 hours)
- C1 = 480 * 4 / 5 = 384
- C2 = 480 * 2 / 3 = 320
- C3 = 480 * 15 / 20 = 360

Demand:
- D1 = 400 
- D2 = 396 
- D3 = 336.6 

Implied Utilization:
- U1 = 400 / 384 = 1.04
- U1 = 396 / 320 = 1.23
- U1 = 360 / 336.6 = 0.935

Bottleneck = Station 2

i.e. system can only handle 320 applicants a day

**DMV3** with the current staffing plan, how many newly licensed drivers will
the DMV turn out each day?

85% * 320 * 70% = 190.4 people get their license

## Homework

Close
Homework Assignment: Module 2 - Process Analysis

10 questions

1. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

Which resource is the bottleneck of the process?

S2

Dryer chair

S3

S1
2. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

What is the utilization of server 2 (in decimal form)? Assume that there is unlimited demand and that the process only admits customers at the rate of the bottleneck.

Enter answer here
3. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

What is the average labor utilization of the servers (in decimal form)? Assume that there is unlimited demand and that the process only admits customers at the rate of the bottleneck.

Enter answer here
4. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

Assume a wage rate of $12 per hour. What are the direct labor costs for one customer (in dollars)?

Enter answer here
5. 
BN1. Butternut is a ski resort in Massachusetts. One of their triple chair lifts unloads 1296 skiers per hour at the top of the slope. (A triple chair lift can carry three passengers per chair. Note that each lift contains multiple chairs.) The ride from the bottom to the top takes 5 minutes. On average, how many skiers are riding on the lift at any one time?

Enter answer here
6. 
Tech Company is a medium-sized consumer electronics retailer. The company reported $155,000,000 in revenues for 2007 and $110,050,000 in Costs of Goods Sold (COGS). In the same year, Tech Co. held an average of $20,000,000 in inventory.

How many times did Tech Co. turn its inventory in 2007?

Enter answer here
7. 
Tech Company is a medium-sized consumer electronics retailer. The company reported $155,000,000 in revenues for 2007 and $110,050,000 in Costs of Goods Sold (COGS). In the same year, Tech Co. held an average of $20,000,000 in inventory.

Inventory cost at Tech Co. is 35 percent per year. What is the per unit inventory cost (in dollars) for an MP3 player sold at $50? Assume that the margin corresponds to the retailer’s average margin.

Enter answer here
8. 
The Gamer Company is a video game production company that specializes in educational video games for kids. The company’s R&D department is always looking for great ideas for new games. On average, the R&D department generates about 25 new ideas a week. To go from idea to approved product, the idea must pass through the following stages: paper screening (a 1-page document describing the idea and giving a rough sketch of the design), prototype development, testing, and a focus group. At the end of each stage, successful ideas enter the next stage. All other ideas are dropped. The following chart depicts this process, and the probability of succeeding at each stage.


The paper screening for each idea takes 2 hours of a staff member’s time. After that, there is a stage of designing and producing a prototype. A designer spends 4 hours designing the game in a computer-aided-design (CAD) package. The actual creation of the mock-up is outsourced to one of many suppliers with essentially limitless capacity. It takes 4 days to get the prototype programmed, and multiple prototypes can be created simultaneously. A staff member of the testing team needs 2 days to test an idea. Running the focus group takes 2 hours of a staff member’s time per idea, and only one game is tested in each focus group. Finally, the management team meets for 3 hours per idea to decide if the game should go into production.

Available working hours for each staff member are 8 hours per day, 5 days a week. The current staffing plan is as follows:

A. Paper screening: 3 staff members.

B. Design and Production: 4 staff members.

C. Testing: 6 staff members.

D. Focus Group: 1 staff member.

E. Final Decision: 1 management team

How many new ideas would Gamer Co. approve for production per week if it had unlimited capacity (staff) in its R&D process?

Enter answer here
9. 
The Gamer Company is a video game production company that specializes in educational video games for kids. The company’s R&D department is always looking for great ideas for new games. On average, the R&D department generates about 25 new ideas a week. To go from idea to approved product, the idea must pass through the following stages: paper screening (a 1-page document describing the idea and giving a rough sketch of the design), prototype development, testing, and a focus group. At the end of each stage, successful ideas enter the next stage. All other ideas are dropped. The following chart depicts this process, and the probability of succeeding at each stage.


The paper screening for each idea takes 2 hours of a staff member’s time. After that, there is a stage of designing and producing a prototype. A designer spends 4 hours designing the game in a computer-aided-design (CAD) package. The actual creation of the mock-up is outsourced to one of many suppliers with essentially limitless capacity. It takes 4 days to get the prototype programmed, and multiple prototypes can be created simultaneously. A staff member of the testing team needs 2 days to test an idea. Running the focus group takes 2 hours of a staff member’s time per idea, and only one game is tested in each focus group. Finally, the management team meets for 3 hours per idea to decide if the game should go into production.

Available working hours for each staff member are 8 hours per day, 5 days a week. The current staffing plan is as follows:

A. Paper screening: 3 staff members.

B. Design and Production: 4 staff members.

C. Testing: 6 staff members.

D. Focus Group: 1 staff member.

E. Final Decision: 1 management team

Which stage is the bottleneck according to the current staffing plan?

Focus group

Final decision

Design and production

Testing

Paper screening
10. 
The Gamer Company is a video game production company that specializes in educational video games for kids. The company’s R&D department is always looking for great ideas for new games. On average, the R&D department generates about 25 new ideas a week. To go from idea to approved product, the idea must pass through the following stages: paper screening (a 1-page document describing the idea and giving a rough sketch of the design), prototype development, testing, and a focus group. At the end of each stage, successful ideas enter the next stage. All other ideas are dropped. The following chart depicts this process, and the probability of succeeding at each stage.


The paper screening for each idea takes 2 hours of a staff member’s time. After that, there is a stage of designing and producing a prototype. A designer spends 4 hours designing the game in a computer-aided-design (CAD) package. The actual creation of the mock-up is outsourced to one of many suppliers with essentially limitless capacity. It takes 4 days to get the prototype programmed, and multiple prototypes can be created simultaneously. A staff member of the testing team needs 2 days to test an idea. Running the focus group takes 2 hours of a staff member’s time per idea, and only one game is tested in each focus group. Finally, the management team meets for 3 hours per idea to decide if the game should go into production.

Available working hours for each staff member are 8 hours per day, 5 days a week. The current staffing plan is as follows:

A. Paper screening: 3 staff members.

B. Design and Production: 4 staff members.

C. Testing: 6 staff members.

D. Focus Group: 1 staff member.

E. Final Decision: 1 management team

With the current staffing plan, how many new ideas will be put into production per week?

Enter answer here
9 questions unanswered
Submit Quiz


Close
Homework Assignment: Module 2 - Process Analysis

10 questions
1. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

Which resource is the bottleneck of the process?

S2

Dryer chair

S3

S1
2. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

What is the utilization of server 2 (in decimal form)? Assume that there is unlimited demand and that the process only admits customers at the rate of the bottleneck.

Enter answer here
3. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

What is the average labor utilization of the servers (in decimal form)? Assume that there is unlimited demand and that the process only admits customers at the rate of the bottleneck.

Enter answer here
4. 
Posh Nails

Katie Posh runs an upscale nail salon. The service process includes five activities that are conducted in the sequence described below. (The time required for each activity is shown in parentheses):

Activity 1: Welcome a guest. (1 minute)
Activity 2: Clip and file nails. (3 minutes)
Activity 3: Paint. (5 minutes)
Activity 4: Dry. (10 minutes)
Activity 5: Check out the customer. (4 minutes)
Three servers (S1, S2, and S3) offer the services in a worker-paced line. The assignment of tasks to servers is the following: S1 does Activity 1. S2 does Activities 2 and 3. S3 does Activities 4 and 5. The drying process does not require server 3’s constant attention; she/he needs to only escort the customer to the salon’s drying chair (equipped with fans for drying). The time to do this is negligible. There exists only one drying chair in the salon.

Assume a wage rate of $12 per hour. What are the direct labor costs for one customer (in dollars)?

Enter answer here
5. 
BN1. Butternut is a ski resort in Massachusetts. One of their triple chair lifts unloads 1296 skiers per hour at the top of the slope. (A triple chair lift can carry three passengers per chair. Note that each lift contains multiple chairs.) The ride from the bottom to the top takes 5 minutes. On average, how many skiers are riding on the lift at any one time?

Enter answer here
6. 
Tech Company is a medium-sized consumer electronics retailer. The company reported $155,000,000 in revenues for 2007 and $110,050,000 in Costs of Goods Sold (COGS). In the same year, Tech Co. held an average of $20,000,000 in inventory.

How many times did Tech Co. turn its inventory in 2007?

Enter answer here
7. 
Tech Company is a medium-sized consumer electronics retailer. The company reported $155,000,000 in revenues for 2007 and $110,050,000 in Costs of Goods Sold (COGS). In the same year, Tech Co. held an average of $20,000,000 in inventory.

Inventory cost at Tech Co. is 35 percent per year. What is the per unit inventory cost (in dollars) for an MP3 player sold at $50? Assume that the margin corresponds to the retailer’s average margin.

Enter answer here
8. 
The Gamer Company is a video game production company that specializes in educational video games for kids. The company’s R&D department is always looking for great ideas for new games. On average, the R&D department generates about 25 new ideas a week. To go from idea to approved product, the idea must pass through the following stages: paper screening (a 1-page document describing the idea and giving a rough sketch of the design), prototype development, testing, and a focus group. At the end of each stage, successful ideas enter the next stage. All other ideas are dropped. The following chart depicts this process, and the probability of succeeding at each stage.


The paper screening for each idea takes 2 hours of a staff member’s time. After that, there is a stage of designing and producing a prototype. A designer spends 4 hours designing the game in a computer-aided-design (CAD) package. The actual creation of the mock-up is outsourced to one of many suppliers with essentially limitless capacity. It takes 4 days to get the prototype programmed, and multiple prototypes can be created simultaneously. A staff member of the testing team needs 2 days to test an idea. Running the focus group takes 2 hours of a staff member’s time per idea, and only one game is tested in each focus group. Finally, the management team meets for 3 hours per idea to decide if the game should go into production.

Available working hours for each staff member are 8 hours per day, 5 days a week. The current staffing plan is as follows:

A. Paper screening: 3 staff members.

B. Design and Production: 4 staff members.

C. Testing: 6 staff members.

D. Focus Group: 1 staff member.

E. Final Decision: 1 management team

How many new ideas would Gamer Co. approve for production per week if it had unlimited capacity (staff) in its R&D process?

Enter answer here
9. 
The Gamer Company is a video game production company that specializes in educational video games for kids. The company’s R&D department is always looking for great ideas for new games. On average, the R&D department generates about 25 new ideas a week. To go from idea to approved product, the idea must pass through the following stages: paper screening (a 1-page document describing the idea and giving a rough sketch of the design), prototype development, testing, and a focus group. At the end of each stage, successful ideas enter the next stage. All other ideas are dropped. The following chart depicts this process, and the probability of succeeding at each stage.


The paper screening for each idea takes 2 hours of a staff member’s time. After that, there is a stage of designing and producing a prototype. A designer spends 4 hours designing the game in a computer-aided-design (CAD) package. The actual creation of the mock-up is outsourced to one of many suppliers with essentially limitless capacity. It takes 4 days to get the prototype programmed, and multiple prototypes can be created simultaneously. A staff member of the testing team needs 2 days to test an idea. Running the focus group takes 2 hours of a staff member’s time per idea, and only one game is tested in each focus group. Finally, the management team meets for 3 hours per idea to decide if the game should go into production.

Available working hours for each staff member are 8 hours per day, 5 days a week. The current staffing plan is as follows:

A. Paper screening: 3 staff members.

B. Design and Production: 4 staff members.

C. Testing: 6 staff members.

D. Focus Group: 1 staff member.

E. Final Decision: 1 management team

Which stage is the bottleneck according to the current staffing plan?

Focus group

Final decision

Design and production

Testing

Paper screening
10. 
The Gamer Company is a video game production company that specializes in educational video games for kids. The company’s R&D department is always looking for great ideas for new games. On average, the R&D department generates about 25 new ideas a week. To go from idea to approved product, the idea must pass through the following stages: paper screening (a 1-page document describing the idea and giving a rough sketch of the design), prototype development, testing, and a focus group. At the end of each stage, successful ideas enter the next stage. All other ideas are dropped. The following chart depicts this process, and the probability of succeeding at each stage.


The paper screening for each idea takes 2 hours of a staff member’s time. After that, there is a stage of designing and producing a prototype. A designer spends 4 hours designing the game in a computer-aided-design ()
