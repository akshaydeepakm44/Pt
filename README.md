### Spike Testing – FLW Application

Spike testing was performed using Apache JMeter to evaluate how the FLW application behaves when there are sudden and extreme increases or decreases in user traffic.

The objective of this test is to observe:
System performance during sudden load spikes
Response time degradation under high concurrency
Error rates during traffic bursts
System recovery behavior after the load drops
The test simulates real-world situations such as flash sales, sudden user logins, or unexpected traffic surges.

Test Setup
The spike testing scenario was implemented using the Ultimate Thread Group in Apache JMeter.
User data was provided through a CSV dataset of users, allowing each virtual user to simulate an independent session.
The test was divided into four phases to replicate realistic traffic behavior.

## Phase 1 — Normal Load
Start Threads	Initial Delay	Startup Time	Hold Load	Shutdown
50	0 sec	5 sec	30 sec	5 sec

## Description
50 virtual users start the test.
Users ramp up gradually over 5 seconds.
The system maintains a stable load for 30 seconds.
This phase represents normal system usage conditions.

## Phase 2 — Sudden Traffic Spike
Start Threads	Initial Delay	Startup Time	Hold Load	Shutdown
400	30 sec	1 sec	20 sec	5 sec

## Description
The number of users suddenly increases to 400.
The spike occurs within 1 second, creating a sharp surge in traffic.
The system handles this load for 20 seconds.
This phase evaluates system stability under sudden high load.

## Phase 3 — Load Reduction (Recovery Phase)
Start Threads	Initial Delay	Startup Time	Hold Load	Shutdown
50	55 sec	2 sec	20 sec	5 sec

## Description
Load drops from 400 users back to 50 users.
The system is monitored to observe how quickly it stabilizes after the spike.
This phase tests the application's recovery capability.

## Phase 4 — Second Traffic Spike
Start Threads	Initial Delay	Startup Time	Hold Load	Shutdown
350	75 sec	1 sec	20 sec	5 sec

## Description
A second spike increases the load to 350 users within 1 second.
This tests the application's ability to handle repeated traffic spikes.
Assertions Used
A Duration Assertion was configured to ensure that response times remain within acceptable limits.

Maximum allowed response time
2000 ms
Any request exceeding this threshold is marked as a failure.

## Outcome
This spike testing scenario helps analyze:
System behavior during sudden load increases
Performance bottlenecks under extreme traffic
Error rates during spikes

System stability and recovery after traffic drops

The results provide insights into the scalability and robustness of the FLW application under unpredictable traffic patterns.
