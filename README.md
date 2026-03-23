About Dataset  关于数据集
Context  背景
As the world transitions to sustainable transportation, the infrastructure supporting Electric Vehicles (EVs) faces unprecedented scaling challenges. This dataset captures complex, multi-variable interactions within a smart-grid EV charging network. It includes temporal data, vehicle battery dynamics, station queue lengths, weather conditions, and dynamic pricing.
随着世界向可持续交通转型，支撑电动汽车（EV）的基础设施面临前所未有的扩展挑战。该数据集捕捉了智能电网电动汽车充电网络中复杂的多变量交互。它包含时序数据、车辆电池动态、站点排队长度、天气状况和动态定价等信息。

Inspiration  灵感来源
This dataset was inspired by the need to bridge the gap between transportation engineering and machine learning. It provides a playground for predicting charging demand, optimizing queue times, and applying Reinforcement Learning (RL) to balance grid loads while maximizing renewable energy usage. What are the key drivers of station overload? Can we predict the exact waiting time for an incoming vehicle?
该数据集的灵感来自于弥合交通工程与机器学习之间差距的需求。它为预测充电需求、优化排队时间以及应用强化学习（RL）在最大化可再生能源使用的同时平衡电网负载提供了一个试验场。导致站点过载的关键因素有哪些？我们能否预测进入车辆的精确等待时间？

Column Name  列名	Description  说明
timestamp  时间戳	Date and time of the record logging.
记录日志的日期和时间。
station_id	Unique identifier for the charging station.
充电站的唯一标识符。
location_type  位置类型	Categorical location of the station (e.g., Urban, Highway).
车站的类别位置（例如：市区、高速公路）。
vehicle_id	Unique identifier for the electric vehicle.
电动汽车的唯一标识符。
vehicle_type	Type of EV (e.g., Two-Wheeler, Bus, Sedan).
电动车类型（例如，两轮车、公交车、轿车）。
arrival_time	Exact time the vehicle arrived at the station.
车辆到达车站的准确时间。
charging_start_time	Time when the active charging session began.
主动充电会话开始的时间。
charging_end_time	Time when the active charging session finished.
主动充电会话结束的时间。
waiting_time	Time spent in the queue before charging started (in minutes).
充电开始前在队列中等待的时间（以分钟为单位）。
battery_capacity_kWh	Total battery capacity of the vehicle (kWh).
车辆的总电池容量（千瓦时）。
initial_soc	State of Charge (percentage) when the vehicle arrived.
车辆到达时的电荷状态（百分比）。
final_soc	State of Charge (percentage) upon session completion.
会话结束时的电荷状态（百分比）。
energy_consumed_kWh	Total energy transferred to the vehicle during the session (kWh).
会话期间传输到车辆的总能量（kWh）。
charging_power_kW	The power delivery rate of the assigned charger (kW).
分配的充电器的供电速率（千瓦）。
charging_duration	Total time spent actively charging.
实际充电的总时长。
queue_length  队列长度	Number of vehicles waiting at the station upon arrival.
到达时在站点等待的车辆数量。
station_load	Current electrical load on the station's local grid.
站点本地电网的当前电力负载。
electricity_price	Dynamic cost of electricity during the session.
会话期间的电力动态成本。
renewable_energy_ratio	Proportion of grid energy coming from renewable sources.
来自可再生能源的电网能源比例。
traffic_density	Local traffic conditions around the station (e.g., Low, High).
充电站周边的本地交通状况（例如：低、 高）。
weather_condition  天气状况	Weather during the session (e.g., Clear, Cloudy).
会话期间的天气（例如：晴朗、多云）。
day_of_week  星期几	Day the session occurred (e.g., Wednesday, Friday).
会话发生的星期几（例如：星期三、星期五）。
time_slot	Categorical time block (e.g., Peak, Off-Peak).
类别时间段（例如，高峰、非高峰）。
charging_demand	The aggregated demand score for the station at that time.
该时段站点的聚合需求得分。
assigned_charger_id	Specific charger unit allocated to the vehicle (e.g., CH4).
分配给车辆的具体充电桩单元（例如，CH4）。
charging_priority	Priority level assigned to the vehicle's session.
分配给车辆充电会话的优先级。
optimization_reward	A synthetic reward metric used for reinforcement learning.
用于强化学习的合成奖励指标。
Include Column Descriptors (Feature Engineering Guide)
包含列描述（特征工程指南）
To empower data scientists, the features can be grouped into the following conceptual blocks:
为了赋能数据科学家，这些特征可分为以下概念块：

Temporal Features: timestamp, arrival_time, charging_start_time, charging_end_time, day_of_week, time_slot. (Crucial for Time-Series Forecasting).
时间特征：timestamp、arrival_time、charging_start_time、charging_end_time、day_of_week、time_slot。（对时间序列预测至关重要）。
Vehicle/Battery Dynamics: vehicle_type, battery_capacity_kWh, initial_soc, final_soc. (Used for clustering EV types and predicting energy needs).
车辆/电池动态：vehicle_type、battery_capacity_kWh、initial_soc、final_soc。（用于对电动汽车类型聚类和预测能量需求）。
Grid & Economic Metrics: station_load, energy_consumed_kWh, charging_power_kW, electricity_price, renewable_energy_ratio. (Ideal for cost-optimization and load balancing models).
电网与经济指标：station_load、energy_consumed_kWh、charging_power_kW、electricity_price、renewable_energy_ratio。（适用于成本优化和负载平衡模型）。
Environmental/Contextual Constraints: location_type, queue_length, traffic_density, weather_condition. (Perfect for queue-theory models and predicting waiting times).
环境/情境约束：location_type、queue_length、traffic_density、weather_condition。（适用于排队论模型和预测等待时间）
RL / System Targets: charging_demand, charging_priority, optimization_reward. (Target variables for supervised learning or reward functions for Reinforcement Learning agents).
强化学习/系统目标：charging_demand、charging_priority、optimization_reward。（用于监督学习的目标变量或用于强化学习智能体的奖励函数）
