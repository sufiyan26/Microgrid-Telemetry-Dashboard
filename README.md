# Microgrid Telemetry Dashboard

**End-to-end monitoring pipeline** connecting C microgrid simulator to live Chart.js dashboard. Features 100ms voltage charts, fault injection, real-time status, and event logging—bridging embedded simulation to cloud-native visualization.

## Core Concept & Objective

- **Goal:** Transform raw C voltage logs into actionable monitoring UI.
- **Key Demo:** Fault injection → detection → recovery workflow visualization.

## Technical Architecture

C Backend (NodeSource.c):
├── Reference Node: 3.68-3.70V
├── Load Node: 3.01-3.03V (normal)
└── microgrid_log.txt (high-freq samples)

Web Dashboard (Replit Agent generated):
├── Chart.js dual-line telemetry (100ms refresh)
├── Voltage gauges + status indicators
├── "Trigger Fault" → Node2 drops to 2.9V
├── "Reset System" → Recovery + event log
└── SQLite event storage


## Project Structure
├── backend/
│ ├── NodeSource.c # Voltage simulation + logging
│ └── microgrid_log.txt # Sample data for replay
├── frontend/
│ ├── index.html # Chart.js dashboard
│ ├── charts.js # Live 100ms updates
│ └── events.db # Fault/recovery history
└── docs/
└── replit_agent_log.md # AI scaffolding trace


## Live Dashboard Features

| Component | Function |
|-----------|----------|
| **Voltage Charts** | Node1/Node2 real-time lines |
| **Gauges** | Current voltage + color-coded |
| **Status** | "Optimal" → "Fault Detected" |
| **Controls** | Fault injection + recovery |
| **Events** | Timestamped history |

## Demo Flow
Normal: Both nodes stable ~3.6V
"Trigger Fault" → Node2 crashes to 2.9V
Status: "FAULT DETECTED" + event logged
"Reset System" → Recovery to normal
Event: "Recovery successful" timestamped


## Skills Demonstrated

C data generation • Chart.js real-time visualization • SQLite event storage • Fault tolerance workflow • AI-assisted full-stack development (Replit Agent) • Embedded-to-cloud data pipeline






