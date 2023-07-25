# Project: Web-App Experiment

## Experiment 1: DDoS Attack

### Overview
In this experiment, I will focus on my personal website/portfolio to assess its resilience against a DDoS attack. By simulating a DDoS attack using Selenium WebDriver, the objective is to stress test the server and evaluate its ability to handle a high volume of requests. This experiment will provide valuable insights into the appropriate DDoS prevention mechanisms to use, considering the average number of users accessing the application.

### Metrics
Two primary metrics will be used to assess the server's performance during the simulated DDoS attack:
- Load average: Measures the average number of processes waiting for CPU time over a given period. A high load average value indicates the server is struggling to keep up with the demand, leading to slow response times and degraded performance.
- %CPU(s): Indicates the percentage of CPU resources utilized by the server. High %CPU(s) values mean the server's CPU is under heavy load, potentially causing performance issues.

### Setup
To perform this experiment, I set up the following components:
- Selenium WebDriver: Used Python to simulate a DDoS attack by sending multiple requests to the personal website/portfolio. The Selenium script runs in a loop, sending requests with varying sleep durations to simulate different traffic intensities.
- Server-side metrics monitoring: On the server, I ran a script to record the load average and %CPU(s) metrics at one-second intervals during the experiment. The collected data will be saved in a file (metrics.txt) for further analysis.

### Execution
With both the Selenium WebDriver script and the server-side script ready, I started the server-side script first to begin collecting metrics. Then, I ran the Selenium WebDriver script to initiate the simulated DDoS attack.

### Results
The analysis of the collected data showed the following observations:
- The load average increased as the sleep duration between requests decreased, indicating higher load on the server due to increased traffic intensity.
- The %CPU(s) utilization remained relatively low throughout the experiment, suggesting the server's CPU is not the primary bottleneck in this setup.
- The highest load average reached 0.54, indicating the server can handle moderate traffic without significant overwhelm. However, as traffic intensity increases, the load average is expected to rise, leading to degraded performance.

### Conclusion
The results indicate the server is capable of handling moderate traffic loads but may struggle under a real DDoS attack. To ensure better performance and resilience, upgrading the server instance or configuration and implementing DDoS prevention mechanisms such as rate limiting and IP filtering is recommended.

---

## Experiment 2: Apache vs. Nginx Comparison

### Overview
Continuing from Experiment 1, this experiment focuses on benchmarking the performance of Apache and Nginx web servers in handling the added features to our personal website/portfolio. The goal is to determine which web server offers better performance in serving different types of files.

### Metrics
Two key metrics are used for comparison:
- Requests per second (RPS): Measures how many requests a web server can handle within one second. Higher RPS values indicate better scalability and efficiency.
- Time per request: The average time taken by the server to process a single request, measured in milliseconds. Lower values signify a more responsive and efficient server.

### Setup
Apache was previously installed and set up. Nginx was installed and configured to use a separate port number.

### Execution
The benchmarking tests were performed on three files: birthday.html, fileshare.php, and logo.jpg, using both Apache and Nginx web servers.

### Results
The benchmarking results revealed significant differences in performance between Apache and Nginx:
- Nginx consistently demonstrated higher RPS and lower Time per request values compared to Apache for all three file types.
- Apache showed decent performance but had slightly lower RPS and higher Time per request values compared to Nginx.

### Conclusion
Based on the benchmarking results and analysis of potential bottlenecks, I recommend using Nginx as the web server for the upgraded personal website/portfolio. Nginx consistently demonstrated superior performance in handling added features. It provides a more responsive and efficient browsing experience for users compared to Apache.

However, monitoring the performance of the Nginx server as the website grows and evolves is crucial. Implementing dynamic content may introduce new challenges, and periodic performance evaluation will ensure optimal performance and an enhanced user experience.

---
