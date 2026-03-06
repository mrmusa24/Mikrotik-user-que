# MikroTik PCQ Queue Settings for ISP Networks

## 1. Configuration for \~500 Users

**Queue Type** - Type Name: ISP-10M-500U - Kind: pcq - Rate: 10M - Queue
Size: 80 - Total Queue Size: 8000 - Burst Rate: 20M - Burst Threshold:
12M - Burst Time: 10s - Classifier: dst-address

**Upload Queue** - Classifier: src-address

**Expected Result** - Fast speed feel for users - Stable ping - Lower
router load

------------------------------------------------------------------------

## 2. Configuration for \~1000 Users

**Queue Type** - Type Name: ISP-10M-1K - Kind: pcq - Rate: 10M - Queue
Size: 100 - Total Queue Size: 20000 - Burst Rate: 20M - Burst Threshold:
12M - Burst Time: 10s - Classifier: dst-address

**Upload Queue** - Classifier: src-address

**Expected Result** - Handles heavy traffic better - Less buffering for
YouTube and streaming - Stable latency for gaming

------------------------------------------------------------------------

## 3. Configuration for \~1500 Users

**Queue Type** - Type Name: ISP-10M-1.5K - Kind: pcq - Rate: 10M - Queue
Size: 120 - Total Queue Size: 30000 - Burst Rate: 20M - Burst Threshold:
12M - Burst Time: 10s - Classifier: dst-address

**Upload Queue** - Classifier: src-address

**Expected Result** - Lower congestion during peak time - Stable router
RAM usage - Smooth user experience during high traffic

------------------------------------------------------------------------

# Important ISP Optimization Tips

## Disable FastTrack (if using queues)

/ip firewall filter disable \[find action=fasttrack-connection\]

## Consider fq-codel Queue Type

fq-codel helps reduce bufferbloat and improves latency for gaming, VoIP,
and streaming.

------------------------------------------------------------------------

# General Best Practice

-   Download Queue: classifier = dst-address
-   Upload Queue: classifier = src-address
-   Monitor router CPU and RAM usage regularly
-   Adjust queue size depending on total bandwidth and router
    performance
