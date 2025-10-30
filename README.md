# COMP6032AIcoursework-NoahAslan-19197248
AI Coursework1Repository
Part 1(a) Baseline Setup

I began by running the original RoboUber system for several simulated days to build a baseline for performance.
During these runs I recorded the average income per taxi, the dispatcher’s total revenue, and the joint return across all participants.
I also tracked how the number of active taxis changed over time.
This baseline showed the normal operating behaviour of the system before any optimisation.
It provided a clear reference point for evaluating later algorithmic improvements.

Part 1(b) Path Planning Improvement

I modified the taxi path-planning process to make routing more efficient.
The new implementation uses the A* search algorithm, which combines actual travel-time costs with a Euclidean-distance heuristic to find the optimal route between two nodes in the network.
The algorithm explores nodes in order of lowest estimated total cost, reconstructing the full path once the destination is reached.
If no route exists it safely returns to the start node to avoid errors.
This change reduced unnecessary travel, improved pickup efficiency, and increased overall system throughput compared with the baseline in 1(a).

Part 2(a) Fare Allocation Enhancement

I redesigned the dispatcher’s fare-allocation logic to improve efficiency and fairness.
The new version scores each taxi’s bid using a revenue-per-minute metric, calculated by dividing the fare price by the sum of the estimated pickup time and the trip duration.
The dispatcher then assigns the job to the taxi with the highest score.
A small fairness adjustment reduces the score slightly for taxis that have already earned more during the day, ensuring a more balanced distribution of work.
This modification increased total revenue while maintaining equitable task allocation among taxis.

Part 2(b) Dynamic Fare Costing

I implemented a new fare-costing model that introduces distance-based and demand-responsive pricing.
Each fare’s base price is determined by the travel distance between the pickup and drop-off points multiplied by a fixed rate.
A dynamic multiplier adjusts the fare according to the ratio of open fares to active taxis—raising prices when demand is high and lowering them when demand is low.
Upper and lower bounds keep prices realistic and prevent instability.
This adaptive approach increased revenue during busy periods and made the simulation’s pricing behave more like a real-world ride-hailing system.
<img width="451" height="702" alt="image" src="https://github.com/user-attachments/assets/9b0a4ddf-9f63-45e5-b3a5-3064a86b895e" />
