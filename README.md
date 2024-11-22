# Bandwidth Sharing Docker Setup

This repository provides Docker Compose configurations that run bandwidth-sharing applications in isolated containers. Each service includes carefully configured resource limits and security measures.

## Supported Services

- [Honeygain](https://www.honeygain.com/)
- [EarnApp](https://earnapp.com/) — Note: This service prohibits using Docker containers
- [Bitping](https://bitping.com/)
- [PacketStream](https://packetstream.io/)
- [Pawns.app](https://pawns.app/)
- [Traffmonetizer](https://traffmonetizer.com/)
- [Repocket](https://repocket.com/)
- [ProxyRack](https://proxyrack.com/)
- [EarnFM](https://earn.fm/)

## Setup Instructions

1. Clone this repository
2. Copy `.env.example` to `.env` and fill in your credentials for each service
3. Run `RANDOM_DEVICE="docker-$RANDOM" docker compose up --build --detach` to start all containers.

### **Important Notes**

**RANDOM_DEVICE**: You **must** set the RANDOM_DEVICE environment variable before starting Docker Compose. This variable creates a unique identifier for your device, which services like Honeygain require.

## Security Considerations

- All containers run with minimal privileges
- Each container operates in an isolated network

## Contributing

We welcome issues, enhancement requests, and pull requests.

## Disclaimer

This setup is intended for educational purposes only. Before use, review each platform's terms of service carefully. Note that some services do not officially support containerized environments.

## License

This project is licensed under the Unlicense - a license with no conditions whatsoever which dedicates works to the public domain. For more information, see http://unlicense.org/
