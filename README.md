# MinIO Object Storage Template

S3-compatible object storage for Quix Cloud, using MinIO with a public access proxy.

## Components

| Component | Description |
|-----------|-------------|
| **MinIO** | S3-compatible object storage server |
| **MinIO Proxy** | Public access proxy for MinIO in Quix platform |

## Architecture

```
┌─────────────────────────────────────────┐
│           MinIO Template                │
│                                         │
│  ┌─────────────────┐                   │
│  │   MinIO (S3)    │  Object Storage   │
│  │                 │  - Port 9000      │
│  │                 │  - Persistent     │
│  └────────┬────────┘    state          │
│           │                             │
│           │                             │
│  ┌────────┴────────┐                   │
│  │  MinIO Proxy    │  Public Access    │
│  │                 │  - Port 80        │
│  │                 │  - URL prefix:    │
│  │                 │    minioproxy     │
│  └─────────────────┘                   │
│                                         │
└─────────────────────────────────────────┘
```

## Getting Started

### Prerequisites

- Quix account ([sign up](https://portal.platform.quix.io/signup))

### Quick Start

1. **Deploy to Quix**
   - Log in to your Quix account
   - Navigate to Templates
   - Click "Deploy template"

2. **Configure Secrets**

   Set the following secrets in your Quix environment:
   ```
   s3_user: <your-minio-username>
   s3_secret: <your-minio-password>
   ```

   > For detailed setup instructions, see [SETUP.md](SETUP.md).

3. **Verify**

   Access the MinIO console through the MinIO Proxy public URL to confirm storage is working.

## Project Structure

```
template-quixlake/
├── images/              # Documentation images
├── minio/               # MinIO application
├── minio-proxy/         # MinIO proxy application
├── quix.yaml            # Quix deployment configuration
├── template.json        # Template metadata
├── SETUP.md             # Initial setup guide
├── LICENSE              # Apache 2.0 license
└── README.md            # This file
```

## Resources

- **Quix Platform**: [https://quix.io/](https://quix.io/)
- **Documentation**: [https://docs.quix.io/](https://docs.quix.io/)
- **MinIO**: [https://min.io/](https://min.io/)

## Support

- **GitHub Issues**: [https://github.com/quixio/template-quixlake/issues](https://github.com/quixio/template-quixlake/issues)
- **Quix Community**: [https://quix.io/slack-invite](https://quix.io/slack-invite)
- **Email**: support@quix.io

## License

This project is licensed under the Apache 2.0 License - see the [LICENSE](LICENSE) file for details.
