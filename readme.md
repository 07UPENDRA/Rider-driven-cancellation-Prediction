## Description:
### Background
At Shadowfax, part of our business includes delivering food orders from clients such as Swiggy and Zomato to customers. The typical order flow goes something like this:
A client creates the order in our system
  The order gets allocated to a rider
  The rider accepts the order
  The rider goes to the pickup location
  The rider picks up the order
  The rider goes to the delivery location and delivers the order
  The rider also has the option to get the order cancelled before delivery by calling the client’s call centre. 
      We would like to predict this kind of cancellation before it happens so that we can try and reassign the order 
      to another rider before it gets cancelled.

Problem Statement:
Given the order and rider details as described below, create a model that can predict rider-driven cancellation in 
  advance (i.e. before getting marked as cancelled or delivered)

Data Description:
Files
  train.csv - the training set
  test.csv - the test set
  sample_submission.csv - a sample submission file in the correct format

Columns
train.csv: This file contains one row for each order created in a specific time frame. 
The columns are:

  order_id : unique id for each order
  order_time: time of the creation of order by the client
  order_date : date of the order
  allot_time: time of allocation of order to the rider
  accept_time: time of acceptance of the order by the rider (if available)
  pickup_time: time of pickup of the order (if available)
  delivered_time: time of delivery of the order (if available)
  cancelled_time: time of cancellation of order (if the order was cancelled)
  cancelled: whether the order was cancelled
  rider_id: unique id for each rider
  first_mile_distance: road distance from rider’s location to the pickup location
  last_mile_distance: road distance from pickup location to the delivery location
  allotted_orders: total number of orders allotted to the rider in the 30 days before (not including) order_date
  delivered_orders: total number of orders delivered by the rider in the 30 days before (not including) order_date
  undelivered_orders: total number of orders allotted to but not delivered by the rider (i.e. cancelled) in the 30 days before (not including) order_date
  lifetime_order_count: total number of orders delivered by the rider at any time before order_date
  reassigned_order: whether the order was reassigned to this rider
  reassignment_method: if the order was reassigned, whether the reassignment was done manually (by the ops team) or automatically
  reassignment_reason: a more detailed reason for the reassignment
  session_time: total time the rider had been online on order_date before order_time
