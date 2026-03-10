# Endurance Testing Report

Endurance testing (also known as **Soak Testing**) was conducted to evaluate how the system behaves when it is subjected to a **steady load for a long duration**. Unlike stress testing, which pushes the system beyond its limits, endurance testing focuses on **long-term stability and performance degradation over time**.

The tests were executed with increasing numbers of concurrent users running continuously for extended durations to simulate **real-world sustained system usage**.

The endurance tests were performed with:

- **100 users**
- **150 users**
- **200 users**
- **300 users**

---

# Objectives of Endurance Testing

The objective of this testing was to analyze:

- System stability during long-running operations  
- Performance degradation over time  
- Memory leaks and resource exhaustion  
- Response time consistency under sustained load  
- Error rates during prolonged system usage  

These results help determine whether the system can **maintain stable performance during extended user activity**.

---

# Test 1 – 100 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 100 |
| Ramp-up Period | 60 seconds |
| Loop Count | Forever |
| Duration | 20 minutes |

This test evaluates the system behavior under a **moderate sustained workload**.

Possible observations include:

- Gradual increase in response time  
- Occasional request failures  
- Performance fluctuations under sustained load  

---

# Test 2 – 150 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 150 |
| Ramp-up Period | 60 seconds |
| Loop Count | Forever |
| Duration | 25 minutes |

This test increases the sustained workload to observe system performance under **higher continuous traffic**.

Possible observations include:

- Increased response times  
- Higher server resource utilization  
- Occasional request timeouts  
- Slight increase in failure rates  

---

# Test 3 – 200 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 200 |
| Ramp-up Period | 120 seconds |
| Loop Count | Forever |
| Duration | 30 minutes |

At this stage the system is exposed to **heavier long-duration traffic conditions**.

Possible observations include:

- Significant increase in response times  
- Increased error rates  
- Resource exhaustion over time  
- Throughput fluctuations  

---

# Test 4 – 300 Concurrent Users

## Test Configuration

| Parameter | Value |
|----------|------|
| Number of Threads (Users) | 300 |
| Ramp-up Period | 180 seconds |
| Loop Count | Forever |
| Duration | 40 minutes |

This test represents **heavy sustained load conditions**.

Possible observations include:

- Higher latency and response time spikes  
- Increased request failure rates  
- Reduced throughput over time  
- Infrastructure resource limitations  

---

# Endurance Test Summary

| Users | Ramp-up | Duration |
|------|--------|---------|
| 100 | 60 sec | 20 min |
| 150 | 60 sec | 25 min |
| 200 | 120 sec | 30 min |
| 300 | 180 sec | 40 min |

---

# Conclusion

The endurance testing results help evaluate the system’s **long-term reliability under sustained traffic conditions**.

As the number of users increases and the system continues running for longer durations, the application may experience:

- Gradual performance degradation  
- Increased response times  
- Higher failure rates under sustained load  
