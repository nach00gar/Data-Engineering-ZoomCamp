1)
docker --help
docker build --help

2)
docker run -it --entrypoint=bash python:3.9
and then pip list

shows pip, wheels and setuptools,so 3 packages

3)
SELECT count(*) from green_taxi_data where DATE(lpep_pickup_datetime) = '2019-01-15' and DATE(lpep_dropoff_datetime) = '2019-01-15'

4)
SELECT lpep_pickup_datetime FROM green_taxi_data WHERE trip_distance = (SELECT MAX(trip_distance) from green_taxi_data);

5)
SELECT COUNT(*) FROM green_taxi_data WHERE DATE(lpep_pickup_datetime) = '2019-01-01' AND passenger_count=2;
SELECT COUNT(*) FROM green_taxi_data WHERE DATE(lpep_pickup_datetime) = '2019-01-01' AND passenger_count=3;

6)
SELECT "Zone" FROM green_taxi_data JOIN taxi_zones ON "DOLocationID" = "LocationID" WHERE tip_amount = (SELECT MAX(tip_amount) FROM green_taxi_data WHERE "PULocationID" = (SELECT "LocationID" FROM taxi_zones WHERE "Zone"='Astoria'));
