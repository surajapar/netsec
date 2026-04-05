# Autonomous Self-Healing Network Defense System

A lightweight, college-level network defense system that monitors, detects threats, and takes automated responses.

## Features
- Real-time network traffic monitoring
- Rule-based threat detection
- Automated response system (block IPs, kill processes)
- Modern dashboard with real-time updates
- Role-based access control
- Comprehensive logging and event tracking

## Tech Stack
- **Backend**: Python 3.9+, Flask
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Libraries**: scapy, psutil, sqlite3, Chart.js
- **OS Integration**: iptables (Linux), netsh (Windows)

## Quick Start

### Prerequisites
- Python 3.9+
- Administrator/sudo privileges (for firewall operations)
- Modern web browser

### Installation

1. Clone repository:
   ```bash
   git clone https://github.com/surajapar/netsec.git
   cd netsec
   ```

2. Create virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run backend:
   ```bash
   python backend/api.py
   ```

5. Open frontend:
   Open `frontend/index.html` in your browser, or run:
   ```bash
   python -m http.server 8000 --directory frontend
   ```

6. Access dashboard:
- Backend API: http://localhost:5000
- Frontend: http://localhost:8000

## Configuration

Edit `config.json` to customize:
- Detection thresholds
- Response actions
- Logging levels
- Whitelisted IPs

## Architecture

```
netsec/
├── backend/
│   ├── monitor.py       # Network packet capture & analysis
│   ├── detector.py      # Threat detection engine
│   ├── responder.py     # Auto-response system
│   ├── logger.py        # Event logging
│   ├── api.py           # Flask REST API
│   └── config.py        # Configuration loader
├── frontend/
│   ├── index.html       # Main dashboard
│   ├── dashboard.js     # UI logic & real-time updates
│   └── styles.css       # Cybersecurity theme
├── logs/
│   ├── events.json      # Event log
│   └── threats.db       # SQLite database
├── config.json          # Configuration
└── requirements.txt     # Dependencies
```

## Usage

### Dashboard Sections
1. **Overview**: Real-time statistics and threat heatmap
2. **Traffic Monitor**: Live network connections
3. **Threats**: Detected threats with severity
4. **Logs**: Searchable event history
5. **Controls**: Enable/disable features, manage rules

### Example Rules
- Detect port scanning: >10 new ports from single IP in 60s
- DoS detection: >100 requests from single IP in 10s
- Brute-force detection: >5 failed login attempts in 60s

## API Endpoints

- `GET /api/traffic` - Get live traffic
- `GET /api/events` - Get detected threats
- `GET /api/logs` - Get event logs
- `POST /api/control` - Control settings
- `POST /api/rules` - Add/manage rules

## Demo & Testing

Run the attack simulator to test detection:
```bash
python backend/simulator.py
```

## Security Notes
- This is educational software
- Requires administrator privileges
- Test in safe environment first
- Review rules before enabling auto-response

## License

MIT License