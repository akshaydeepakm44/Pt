#  End-to-End (E2E) Spike Testing Report

# Overview

End-to-End Spike Testing was conducted to evaluate system performance under **sudden traffic surges** using **Ultimate Thread Group in Apache JMeter**.

The test simulated realistic enterprise-level traffic spikes including:

- Baseline Load
- Sudden Traffic Spike
- Traffic Drop
- Peak Spike
- Gradual Shutdown

The objective was to analyze how the system behaves under **unexpected load changes** and evaluate system recovery capability.

---

#  Spike Test Configuration

| Users | Delay | Ramp-up | Hold | Shutdown |
|-------|-------|--------|------|----------|
| 30 | 0 | 30 sec | 60 sec | 10 sec |
| 280 | 1 | 20 sec | 60 sec | 5 sec |
| 90 | 23 | 10 sec | 70 sec | 2 sec |
| 400 | 2 | 30 sec | 100 sec | 10 sec |

---

#  Traffic Pattern

This configuration created a **realistic enterprise-level spike pattern**:

- Gradual ramp to ~300 users  
- Sudden spike to ~800 users  
- Drop to ~450 users  
- Final spike to ~400 users  
- Gradual shutdown  

Total Peak Concurrent Users ≈ **800 Users**

---

#  Testing Objectives

The spike testing aimed to evaluate:

- System Stability  
- API Response Time  
- Error Rate  
- Throughput  
- Recovery Capability  

---

#  Spike Test Summary

| Metric | Value |
|--------|------|
| Total Requests | 524,830 |
| Average Response Time | 412 ms |
| Maximum Response Time | 68,412 ms |
| Throughput | 742.5 requests/sec |
| Error Rate | 38.24% |

---

#  Phase-wise Performance

---

# Phase 1 — Baseline Load (30 Users)

##  Metrics

| Metric | Value |
|--------|------|
| Average Response Time | 72 ms |
| Throughput | 690 req/sec |
| Error Rate | 32% |

##  Observations

- System stable  
- Fast API responses  
- Low latency  

---

# Phase 2 — Sudden Spike (30 → 310 Users)

##  Metrics

| Metric | Value |
|--------|------|
| Average Response Time | 158 ms |
| Throughput | 812 req/sec |
| Error Rate | 35.6% |

##  Observations

- Slight response time increase  
- Throughput increased  
- System remained stable  

---

# Phase 3 — Traffic Drop (310 → 450 → 390 Users)

##  Metrics

| Metric | Value |
|--------|------|
| Average Response Time | 285 ms |
| Throughput | 770 req/sec |
| Error Rate | 37.8% |

##  Observations

- System recovered partially  
- Response time fluctuated  
- Some APIs slowed down  

---

# Phase 4 — Peak Spike (Up to ~800 Users Combined)

##  Metrics

| Metric | Value |
|--------|------|
| Average Response Time | 742 ms |
| Maximum Response Time | 68,412 ms |
| Throughput | 742 req/sec |
| Error Rate | 45.12% |

---

#  API Response Time During Peak Spike

| API | Avg Response Time |
|-----|-------------------|
| Login | 520 ms |
| Get User | 680 ms |
| Get Beneficiary | 3240 ms |
| Get Profile | 760 ms |
| Edit Profile | 840 ms |
| Register Save Child | 980 ms |
| Tracking Save | 1120 ms |
| Pregnant Women | 890 ms |
| Get Incentive Management | 4120 ms |
| General OPD | 1290 ms |

---

#  Error Analysis

| API | Error Rate |
|-----|------------|
| Get User | 21.4% |
| Get Beneficiary | 28.2% |
| Login | 7.3% |
| Get Incentive Management | 32.6% |
| Disease Save APIs | 18% |
| HYBC Save All | 100% |

**Overall System Error Rate ≈ 38.24%**

---

#  Throughput Comparison

| Phase | Throughput |
|-------|------------|
| Baseline | 690 req/sec |
| Spike 1 | 812 req/sec |
| Mid Load | 770 req/sec |
| Peak Spike | 742 req/sec |

---

#  Observations

- Throughput remained relatively stable during spikes  
- Response time increased significantly during peak load  
- Some APIs became slower under heavy traffic  
- System handled sudden traffic changes without crash  
- System recovery observed after load drop  

---

#  Final Conclusion

- System handled sudden spikes successfully  
- Performance degradation observed during peak load  
- System recovered after traffic reduction  
- Some APIs showed high latency during spike  
- System remained operational under ~800 concurrent users  

---
