[Research1.pdf](https://github.com/user-attachments/files/23536028/Research1.pdf)# teleop-capstone
Packet captures and analysis of XR robot network experiments (Quest ↔ Boston setup)

# XR Network Research
This repository tracks all packet captures, analysis scripts, and experimental data from the Real Robot (Boston) - Quest (IITH).

## Objective
This contains network traffic captures and related artifacts collected from various teleoperation and XR/robotics communication scenarios. The data will be used for analysis, benchmarking, and future research.

## Structure
- `/data/pcaps/` → raw capture files
- `/analysis/` → Python notebooks and throughput/jitter analysis
- `/docs/` → network setup diagrams and notes

# System Architecture
The experimental setup consists of a Client (Quest device) communicating with a Server, with traffic routed through multiple network layers:
[Research1.pdf](https://github.com/user-attachments/files/23536029/Research1.pdf)


Client Side
- Quest Device
- IP: **172.28.84.21**
- Connected to a personal Access Point using 4G/5G.
- Traffic then passes through the Gateway Router
- IP: 106.208.15.218  // this IP might be different across the experiments.

Server Side
- Traffic reaches the ISP Gateway Router
- IP: **71.192.240.172**
- Then forwarded to the raspberry pi that acts like a pass through devices which forwards to the real robot.
- Port 10000 : for state of the robot, 10001: for the video data; 10002: for ML interaction.

The packets are captured at 2 different devices 
1. server side: At raspberry pi.
2. client side: via monitor mode on the same wireless channel as the quest and Access point.
This setup is used to capture realistic teleop network behavior during XR streaming, robot control, and digital-twin synchronization.
