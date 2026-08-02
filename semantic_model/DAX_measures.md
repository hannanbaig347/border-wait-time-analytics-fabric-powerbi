1. Total Snapshots = COUNTROWS('Fact_WaitTimes_Gold_New')


2. Sensor Failure Rate = 
DIVIDE(
    CALCULATE([Total Snapshots], 'Fact_WaitTimes_Gold_New'[operational_status] = "Update Pending"), 
    [Total Snapshots]


3. Average Dwell Time = AVERAGE('Fact_WaitTimes_Gold_New'[wait_time_min])


4. Max Bottleneck = MAX('Fact_WaitTimes_Gold_New'[wait_time_min])


5. Commercial Dwell Time = CALCULATE([Average Dwell Time], 'Dim_Lane_New'[traffic_pillar] = "commercial_vehicle_lanes")


6. Critical Delay Count = CALCULATE(COUNTROWS('Fact_WaitTimes_Gold_New'), 'Fact_WaitTimes_Gold_New'[wait_time_min] > 60
   
   
7. Previous Day Dwell Time = CALCULATE([Average Dwell Time], PREVIOUSDAY('Dim_Date'[date]))


8. DoD Dwell Time Growth % =  DIVIDE([Average Dwell Time] - [Previous Day Dwell Time], [Previous Day Dwell Time])
   

9.  Predicted Dwell Time (RF) = AVERAGE('Fact_WaitTime_Predictions'[predicted_wait_time_min])


10. Predicted Dwell Time (Baseline) = AVERAGE('Fact_WaitTime_Predictions'[lag_1h])


11.  Model Variance (How far off the AI is from reality)  = [Average Dwell Time] - [Predicted Dwell Time (RF)]
