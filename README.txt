---------
Problem 1
---------

You have been provided two files, scenario1.txt and scenario2.txt
which each contain simulated application logs in the following format:

Column 1: # seconds since time t=0
Column 2: # requests processed since last log
Column 3: Mean response time for requests processed since last log

The logging frequency is 1 per second, but there are no logs for seconds in
which there were no requests. The data span two simulated weeks and were
generated under an idealized/simplified model in which there is a single
application server which processes requests sequentially using a single thread.
If a request arrives while the server is busy, it waits in a queue until
the server is free to process it. There is no limit to the size of the queue.

For each scenario, please answer the following questions.
Note that we define "week 2" to begin at second 626400 (6 am on the 8th day).

1) How much has the mean response time (specifically, the mean of the response
times for each individual request) changed from week 1 to week 2?

2) Create a plot illustrating the probability distribution of the amount of
server time it takes to process a request (excluding the time the request
spends waiting in the queue).

3) Propose a potential cause for the change in response times. Give both a
qualitative answer as if you were explaining it to a client and a quantitative
answer as if you were explaining it to a statistician. Create 1 or 2 plots to
support and illustrate your argument.

Your submission should include sufficient code and instructions to reproduce
your analysis (any quantitative results as well as your plots).

---------
Problem 2
---------

A government agency is using Datadog to monitor response times for one of
their web applications. They are launching social media marketing campaigns to
build public awareness for their services. Management wants to ensure that 
they can elastically scale their server capacity to meet the uncertain demand
produced by these initiatives, while minimizing server costs when capacity is
not needed. They have tasked you with designing an algorithm that dynamically
determines when to spin-up or shut down servers in the cloud (assume this is
an alternate universe where AWS Auto Scaling doesn't exist).

Imagine that you have 1 year's worth of training data in the same format as in
Problem 1. For this year, the client had a static configuration of 4 servers
that were continually active (you can assume load balancing is perfect and
that there is no server downtime). Your algorithm will receive new data in
this format at 1 second intervals over the course of each day. Due to the
complexity of this government web application, assume that servers take about
15 minutes to spin-up or to be shut down.

In words, describe how a simple algorithm for this problem could work.
By simple, we mean something you could prototype quickly, not something
you would publish in a scientific journal. Be sure to describe your
algorithm's parameters.

Finally, write pseudo-code that demonstrates how you would optimize your
algorithm's parameters. You may assume that you have a function:

simulate_algo(algo_params, log_data) that returns a set of tuples:
(timestamp, n_requests, avg_response_time,
 n_servers_active, n_servers_starting, n_servers_shutting_down)
for input data of your choice (either training data or simulated data).
