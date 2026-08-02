

	relationship a8346ad2-a9d6-5bfb-c8d2-3fed25365d76
		fromColumn: fact_waittimes_gold_new.port_number
		toColumn: dim_port.port_number

	relationship df331c80-c465-4f69-fa03-541ceadfae65
		fromColumn: fact_waittimes_gold_new.lane_id
		toColumn: dim_lane_new.lane_id

	relationship 4f03c9a8-5fb2-d4bd-b132-f7ac1b08b7ba
		fromColumn: fact_waittimes_gold_new.snapshot_hour
		toColumn: dim_time.hour_of_day

	relationship 0e5c6341-3ae0-aec6-cc90-4c3f2b24c7ac
		fromColumn: fact_waittime_predictions.port_number
		toColumn: dim_port.port_number

	relationship 3bd4bb45-5929-b05b-e531-c892105a1b47
		fromColumn: fact_waittime_predictions.lane_id
		toColumn: dim_lane_new.lane_id

	relationship ef9edcea-172c-7f0b-f8ba-de0d24b5e9a2
		fromColumn: fact_waittime_predictions.snapshot_date
		toColumn: dim_date.date

	relationship 2625e899-4525-265c-9770-24ae952a27e0
		fromColumn: fact_waittime_predictions.snapshot_hour
		toColumn: dim_time.hour_of_day

	relationship 6ad3d61b-9ddd-975e-ca80-042c18245717
		fromColumn: fact_waittimes_gold_new.snapshot_date
		toColumn: dim_date.date

