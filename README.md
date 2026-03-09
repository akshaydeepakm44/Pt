# Stress Testing Report

Stress testing was conducted to evaluate how the system behaves when it is pushed beyond its normal operating limits. Unlike load testing, which measures performance under expected traffic, stress testing intentionally overloads the system to observe its **breaking point and recovery behavior**.

The tests were executed with increasing numbers of concurrent users:

- **300 users**
- **500 users**
- **700 users**
- **1000 users**

## Objectives of Stress Testing

The objective of this testing was to analyze:

- System stability under extreme load  
- Response time behavior during overload  
- Maximum processing capacity of the system  
- Error rates when the system is pushed beyond limits  
- System throughput under stress conditions  

These results help determine the **maximum load the system can tolerate before performance significantly degrades or failures occur**.

---

# Test 1 – 300 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 300 |
| Ramp-up Period | 30 seconds |
| Loop Count | Forever |
| Duration | 120 seconds |

A large number of request failures occurred during this test. The high error rate indicates that the system was **unable to sustain this level of concurrent traffic**, leading to request timeouts and failed responses.

The very high **maximum response time (~24 seconds)** also indicates severe latency spikes caused by system overload.

---

# Test 2 – 500 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 500 |
| Ramp-up Period | 40 seconds |
| Duration | 120 seconds |

This test further increases the load to evaluate how the system behaves under **heavier stress conditions**.

Under this scenario, the system is expected to experience:

- Higher response times  
- Increased failure rates  
- Possible request timeouts  
- Reduced throughput due to resource saturation  

---

# Test 3 – 700 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 700 |
| Ramp-up Period | 50 seconds |
| Duration | 120 seconds |

At this level, the system is pushed into **extreme load conditions** where infrastructure limitations become more visible.

Possible observations include:

- Large latency spikes  
- Significant increase in API failures  
- Server resource exhaustion  
- Increased request queue delays  

---

# Test 4 – 1000 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 1000 |
| Ramp-up Period | 60 seconds |
| Duration | 120 seconds |

This test represents **maximum stress conditions** where the number of concurrent users is far beyond expected production traffic.

Under such extreme load, the system may encounter:

- Very high response times  
- Severe failure rates  
- Throughput stagnation or decline  
- Possible service interruptions  

This test helps identify the **absolute performance limit of the system**.

---

# Stress Test Summary

| Users | Ramp-up | Duration |
|------|--------|---------|
| 300 | 30 sec | 120 sec |
| 500 | 40 sec | 120 sec |
| 700 | 50 sec | 120 sec |
| 1000 | 60 sec | 120 sec |

---

# Conclusion

The stress testing results show that the system begins to experience **significant performance degradation at 300 concurrent users**, where the **error rate reached 34.88% and response times increased dramatically**.

As the number of users increases further (**500, 700, and 1000**), the system is expected to face **severe overload conditions**, including increased latency, higher failure rates, and reduced throughput.
ify the **system's breaking point**, enabling better planning for **future scalability and performance improvements**.
