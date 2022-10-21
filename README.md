# Maven-Space-Challenge
Data Set is Avaliable in [Maven_data_playground](https://www.mavenanalytics.io/data-playground)

-- Total No.of Missions.

Select count(*) from space_missions;

-- No.of Successful Missions.

Select missionstatus , count(missionstatus) from space_mission
where missionstatus = 'Success';

-- No.of Missions Failed.

Select missionstatus , count(missionstatus) from space_mission
where missionstatus in ('Failed', 'Partial Failure', 'Prelaunch Failure');

-- Total Investment.

Select sum(Price) from space_mission;

-- Total No.of Companies.

Select count(distinct Company) from space_missions;

-- Rocket Types

Select count(distinct Rocket) from space_missions;

-- Total No.of Active Rockets.

Select count(RocketStatus) from space_missions
where RocketStatus = 'Active' ;

-- Total No.of Retired Rockets.

Select count(RocketStatus) from space_missions
where RocketStatus = 'Retired' ;

-- Top-5 Companies by Mission.

Select distinct Company, count(Mission) from space_missions
group by Company
order by Count(Mission) desc
limit 5;

-- Top-5 Companies by Investment.

Select distinct Company, sum(Price) from space_missions
group by Company
order by sum(Price) desc
limit 5;

-- Top-3 Most Successful Rockets.

Select Rocket, Count(Mission) from space_missions
where MissionStatus = 'Success'
group by Rocket
order by Count(Mission) desc
limit 3;

