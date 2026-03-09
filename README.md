# Load Testing Report


Load testing was conducted to evaluate how the system behaves under increasing numbers of concurrent users. The tests were executed using different load levels: **50 users, 100 users, 200 users, and 300 users**.

The objective of this testing was to analyze:

* System stability under increasing load
* API response times
* Throughput (requests processed per second)
* Error rates during execution
The results help identify the **performance limits of the system** and determine the load level at which performance degradation begins.



### Example approach:

# Test 1 – 50 Concurrent Users

## Test Summary

| Metric                | Value            |
| --------------------- | ---------------- |
| Total Requests        | 2000             |
| Average Response Time | 78 ms            |
| Maximum Response Time | 1486 ms          |
| Throughput            | 155 requests/sec |
| Error Rate            | 2.50%            |

## Error Analysis

| Endpoint       | Error Rate |
| -------------- | ---------- |
| HYBC Save All  | 100%       |
| Overall System | ~2.5%      |

The **HYBC Save All** endpoint consistently failed during the test beacause it is representing the 400 bad request error from the imported collection, indicating a potential issue with that specific API.


# Test 2 – 100 Concurrent Users

## Test Summary

| Metric                | Value            |
| --------------------- | ---------------- |
| Total Requests        | 4000             |
| Average Response Time | ~100 ms          |
| Maximum Response Time | 3249 ms          |
| Throughput            | 169 requests/sec |
| Error Rate            | 2.53%            |

## Error Analysis

| Endpoint       | Error Rate |
| -------------- | ---------- |
| HYBC Save All  | 100%       |
| Login          | 1%         |
| Overall System | 2.53%      |

A small increase in errors was observed when the number of users doubled.
---

# Test 3 – 200 Concurrent Users

## Test Summary

| Metric                | Value            |
| --------------------- | ---------------- |
| Total Requests        | 8000             |
| Average Response Time | 95 ms            |
| Maximum Response Time | 2325 ms          |
| Throughput            | 185 requests/sec |
| Error Rate            | 2.55%            |

## Error Analysis

| Endpoint                 | Error Rate |
| ------------------------ | ---------- |
| HYBC Save All            | 100%       |
| Get Incentive Management | 2%         |
| Overall System           | 2.55%      |

---

# Test 4 – 300 Concurrent Users

## Test Summary

| Metric                | Value            |
| --------------------- | ---------------- |
| Total Requests        | 12,000           |
| Maximum Response Time | 9201 ms          |
| Throughput            | 160 requests/sec |
| Error Rate            | 5.10%            |

## Error Analysis

| API                      | Error Rate |
| ------------------------ | ---------- |
| Login                    | 42.67%     |
| HYBC Save All            | 100%       |
| Get Incentive Management | 43%        |
| Get Beneficiary          | 18.33%     |



The load testing results indicate that the system performs efficiently under **50–100 concurrent users**. Performance begins to degrade at **200 users**, where latency increases and minor errors appear.
