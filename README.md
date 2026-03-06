# MikroTik ISP Optimization Handbook

Author: Md. Abu Musa\
Role: System Network Engineer & Admin\
Company: Asian Network

------------------------------------------------------------------------

# 1. PCQ Queue Design for ISP Networks

## 500 User Network

Queue Type: - Name: PCQ-DL-500U - Kind: pcq - Rate: 10M - Queue Size:
80 - Total Queue Size: 8000 - Burst Rate: 20M - Burst Threshold: 12M -
Burst Time: 10s - Classifier: dst-address

Upload Queue: - Classifier: src-address

Expected Result: - Stable latency - Fast user experience - Low CPU load

------------------------------------------------------------------------

## 1000 User Network

Queue Type: - Name: PCQ-DL-1K - Kind: pcq - Rate: 10M - Queue Size:
100 - Total Queue Size: 20000 - Burst Rate: 20M - Burst Threshold: 12M -
Burst Time: 10s - Classifier: dst-address

Upload Queue: - Classifier: src-address

Expected Result: - Better congestion control - Smooth video streaming -
Stable gaming latency

------------------------------------------------------------------------

## 1500 User Network

Queue Type: - Name: PCQ-DL-1.5K - Kind: pcq - Rate: 10M - Queue Size:
120 - Total Queue Size: 30000 - Burst Rate: 20M - Burst Threshold: 12M -
Burst Time: 10s - Classifier: dst-address

Upload Queue: - Classifier: src-address

Expected Result: - Stable during peak time - Reduced packet drop -
Balanced bandwidth distribution

------------------------------------------------------------------------

# 2. FastTrack Recommendation

If you are using queue tree or heavy traffic shaping, disable fasttrack.

Command:

/ip firewall filter disable \[find action=fasttrack-connection\]

This ensures queues work properly.

------------------------------------------------------------------------

# 3. Bufferbloat Fix

Use fq-codel queue type.

Advantages:

-   Reduces latency
-   Improves gaming performance
-   Improves VoIP quality
-   Prevents queue delay

------------------------------------------------------------------------

# 4. Recommended Router Models for ISP

Small ISP (0‑500 users) - CCR1009 - RB4011

Medium ISP (500‑1500 users) - CCR1036 - CCR2004

Large ISP (1500‑5000 users) - CCR2116 - CCR2216

------------------------------------------------------------------------

# 5. Monitoring Tips

Always monitor:

CPU Usage RAM Usage Interface Traffic Packet Drop Queue Usage

Tools: - Torch - Interface Monitor - Queue Statistics

------------------------------------------------------------------------

# 6. Best Practice for Stable ISP

1.  Use PCQ queues for fairness
2.  Avoid extremely large queue sizes
3.  Use proper burst configuration
4.  Monitor router CPU regularly
5.  Keep firmware updated

------------------------------------------------------------------------

# 7. Latency Optimization Tips

For best user experience:

-   Use local IX / NIX peering
-   Use good upstream providers
-   Keep DNS cache enabled
-   Monitor packet loss regularly

------------------------------------------------------------------------

# 8. DNS Optimization

Recommended public DNS:

8.8.8.8 1.1.1.1 9.9.9.9

Local DNS caching improves browsing speed.

------------------------------------------------------------------------

# 9. Common ISP Problems

High Ping: - Caused by congestion or bufferbloat

Slow Speed: - Insufficient bandwidth - Queue misconfiguration

Packet Loss: - Bad upstream - Hardware overload

------------------------------------------------------------------------

# 10. Final Advice

A stable ISP network depends on:

-   Good routing
-   Proper queue management
-   Strong monitoring
-   Reliable upstream bandwidth

------------------------------------------------------------------------

End of Handbook
