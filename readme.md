# VMWatch: Seamless Observability Stack Setup for Your Virtual Machines

VMWatch is a powerful application that allows you to effortlessly set up an open-source, proven observability stack on your virtual machines (VMs) and small environments. By leveraging VMWatch, you can quickly deploy and interact with various observability components, such as Grafana, Mimir, Loki, Tempo, and Vector, enabling you to build robust monitoring and logging solutions tailored to your needs.

## Key Features

- **Effortless Setup**: VMWatch simplifies the setup and configuration of multiple observability components, including Grafana, Mimir, Loki, Tempo, and Vector.

- **Accelerated Development**: Streamline the development and testing process for observability components, ensuring changes are thoroughly validated before being deployed to production.

- **Discover and Experiment**: Explore interactions between different observability tools, like OpenTelemetry and Grafana Lab, to identify and optimize configurations that work best for your environment.

- **SDK and Application Development**: VMWatch provides a comprehensive playground to accelerate the development and testing of software development kits (SDKs) and applications that rely on diverse observability tools.

---
**Note**: The following sections below provide instructions and additional information for using the VMWatch application.

## Installation

1. Clone the VMWatch repository:

`git clone https://github.com/VMWatch/vmwatch.git`

2. Update the configuration files as needed:
- Loki: `vim config/loki`
- Vector: `vim config/vector/vector.toml`
- Mimir: `vim config/mimir` (optional)

3. Start the observability components using Docker Compose:

`sudo docker-compose up -d`

## Usage

Once the environment is up and running, you can access the following services:

- Mimir: `http://localhost:9090/`
- Grafana: `http://localhost:3000/`
- Vector: `http://localhost:8686/`
- Loki: `http://localhost:3100/`
- Tempo: `http://localhost:3200/`
- OTEL GRPC: `http://localhost:5555/`

### How to use MimirTool

1. Set up an alias for `mimirtool` for easier usage:

`alias mimirtool='docker run --rm --net examples_net grafana/mimirtool:latest'`

2. Run `mimirtool` commands, for example:

`mimirtool rules get --address http://load-balancer:9009 --id=demo demo_namespace demo_group`

### Rules

- VMWatch comes pre-configured with both Alert and Recording rules for Mimir and Loki setups.

### Using the Postman Collection

We provide a Postman collection to simplify interactions with the observability components. To use the Postman collection:

1. Download and install [Postman](https://www.postman.com/downloads/).

2. Import the Postman collection from the `postman` directory in the VMWatch repository.

3. Customize the collection variables to match your VMWatch environment (e.g., update base URLs).

4. Explore the API endpoints and execute requests to interact with Grafana, Mimir, Loki, Tempo, and Vector.

## Development Prerequisites

If you want to contribute to the VMWatch project and work on the code, make sure you have the following utilities installed:

- [Docker](https://docs.docker.com/)
- [Vector dev](https://vector.dev/docs/)
- [Prometheus](https://prometheus.io/docs/introduction/overview/)
- [Python-Prometheus-client](https://github.com/prometheus/client_python)

## Resources

Here are some useful resource links for understanding VMWatch components and related practices:

- [Metric Naming](https://prometheus.io/docs/practices/naming/)
- [Labels](https://prometheus.io/docs/practices/instrumentation/#use-labels)
- [Docker Setup Guide](https://thepylot.dev/setup-grafana-with-prometheus-for-python-projects-docker-included/)
- [Grafana Documentation](https://docs.grafana.com/)
- [Loki Documentation](https://grafana.com/docs/loki/latest/)
- [Tempo Documentation](https://grafana.com/docs/tempo/latest/)
- [Vector Documentation](https://vector.dev/docs/)

## Authors

- **Puneet Gupta**

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contribution Guidelines

We welcome contributions from the community. If you want to contribute to VMWatch, please follow our [Contribution Guidelines](CONTRIBUTING.md).

## Code of Conduct

Please review and adhere to our [Code of Conduct](CODE_OF_CONDUCT.md) to foster an inclusive and welcoming community.

## Support

For any questions or issues, please use our [Issue Tracker](https://github.com/VMWatch/vmwatch/issues) or join our [Discord Server](https://discord.gg/vmwatch) for community support.

## Acknowledgments

If your project is built on the work of other developers, organizations, or libraries, acknowledge them here.

By using VMWatch, you can set up a powerful observability stack on your virtual machines and small environments with ease, benefiting from a unified platform to experiment, develop, and test observability tools effectively. Start leveraging VMWatch today to enhance your monitoring and logging capabilities!
