# Description:
## Background
At Shadowfax, part of our business includes delivering food orders from clients such as Swiggy and Zomato to customers. The typical order flow goes something like this: </br>
  A client creates the order in our system </br>
  The order gets allocated to a rider</br>
  The rider accepts the order</br>
  The rider goes to the pickup location</br>
  The rider picks up the order</br>
  The rider goes to the delivery location and delivers the order</br>
  The rider also has the option to get the order cancelled before delivery by calling the client’s call centre. </br>
      We would like to predict this kind of cancellation before it happens so that we can try and reassign the order 
      to another rider before it gets cancelled.</br>

## Problem Statement:
Given the order and rider details as described below, create a model that can predict rider-driven cancellation in 
  advance (i.e. before getting marked as cancelled or delivered) </br>

## Data Description:
### Files </br>
  train.csv - the training set</br>
  test.csv - the test set</br>
  sample_submission.csv - a sample submission file in the correct format</br>

### Columns
train.csv: This file contains one row for each order created in a specific time frame. </br>
The columns are:</br>

  order_id : unique id for each order</br>
  order_time: time of the creation of order by the client</br>
  order_date : date of the order</br>
  allot_time: time of allocation of order to the rider</br>
  accept_time: time of acceptance of the order by the rider (if available)</br>
  pickup_time: time of pickup of the order (if available)</br>
  delivered_time: time of delivery of the order (if available)</br>
  cancelled_time: time of cancellation of order (if the order was cancelled)</br>
  cancelled: whether the order was cancelled</br>
  rider_id: unique id for each rider</br>
  first_mile_distance: road distance from rider’s location to the pickup location</br>
  last_mile_distance: road distance from pickup location to the delivery location</br>
  allotted_orders: total number of orders allotted to the rider in the 30 days before (not including) order_date</br>
  delivered_orders: total number of orders delivered by the rider in the 30 days before (not including) order_date</br>
  undelivered_orders: total number of orders allotted to but not delivered by the rider (i.e. cancelled) in the 30 days before (not including) order_date</br>
  lifetime_order_count: total number of orders delivered by the rider at any time before order_date</br>
  reassigned_order: whether the order was reassigned to this rider</br>
  reassignment_method: if the order was reassigned, whether the reassignment was done manually (by the ops team) or automatically</br>
  reassignment_reason: a more detailed reason for the reassignment</br>
  session_time: total time the rider had been online on order_date before order_time</br>
