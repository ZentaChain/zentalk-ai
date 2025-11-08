# zentalk-ai

Zentalk-AI is a peer-to-peer AI compute network where users, developers, and GPU providers collaborate in a secure, decentralized environment.
The network utilizes the Zentalk Node for end-to-end encrypted, peer-to-peer GPU computation, allowing users to access AI models without exposing their data.
All computation, storage, and participation are incentivized through the CHAIN Token economy, creating a trustless and privacy-preserving AI infrastructure.

## Project Structure

```
zentalk-ai/
├── config/                         # Configuration files
│   ├── config.yaml                 # Main configuration (ports, network settings)
│   ├── encryption.yaml             # Encryption settings and keys
│   ├── gpu-pool.yaml               # GPU pool configuration
│   ├── database.yaml               # Database connection / Mesh integration
│   ├── chain.yaml                  # CHAIN Token config
│   ├── integration.yaml            # Integration settings for zentalk ecosystem
│   ├── privacy.yaml                # Privacy and data handling settings
│   ├── models.yaml                 # AI model configurations
│   └── features.yaml               # Feature flags and AI features config
│
├── docs/                           # Documentation
│   ├── api/                        # API documentation
│   │   ├── endpoints.md
│   │   ├── websocket.md
│   │   └── authentication.md
│   │
│   ├── architecture/               # Architecture documentation
│   │   ├── SECURE_GPU_ENCRYPTION.md
│   │   ├── MESH_INTEGRATION.md
│   │   ├── CHAIN_REWARDS.md
│   │   └── AI_PIPELINE.md
│   │
│   ├── integration/                # Integration guides
│   │   ├── MESH_STORAGE.md         # How to use mesh storage
│   │   ├── RELAY_INTEGRATION.md    # Relay network integration
│   │   ├── API_BRIDGE.md           # API server integration
│   │   └── WEBSOCKET_RELAY.md      # WebSocket relay communication
│   │
│   ├── features/                   # Feature documentation
│   │   ├── SMART_REPLIES.md        # Smart reply system
│   │   ├── TRANSLATION.md          # Translation feature
│   │   ├── SUMMARIZATION.md        # Conversation summarization
│   │   ├── SPAM_DETECTION.md       # Spam detection system
│   │   └── SEARCH_ENHANCEMENT.md   # Semantic search
│   │
│   ├── deployment/                 # Deployment guides
│   │   ├── DOCKER.md               # Docker deployment
│   │   ├── KUBERNETES.md           # Kubernetes deployment
│   │   └── PRODUCTION.md           # Production deployment guide
│   │
│   ├── guides/                     # User guides
│   │   ├── GETTING_STARTED.md
│   │   ├── CONFIGURATION.md
│   │   └── TROUBLESHOOTING.md
│   │
│   └── privacy/                    # Privacy documentation
│       ├── DATA_HANDLING.md
│       ├── ENCRYPTION.md
│       └── COMPLIANCE.md
│
├── scripts/                        # Utility scripts
│   ├── start_inference.sh          # Start inference node
│   ├── start_orchestrator.sh       # Start orchestrator service
│   ├── update_models.sh            # Update model files
│   ├── verify_gpu_nodes.sh         # Verify GPU node health
│   ├── health_check.sh             # System health check
│   ├── sync_with_mesh.sh           # Sync with mesh storage
│   │
│   ├── deploy/                     # Deployment scripts
│   │   ├── deploy.sh               # Deploy to production
│   │   ├── rollback.sh             # Rollback deployment
│   │   ├── build.sh                # Build Docker images
│   │   └── setup_env.sh            # Setup environment
│   │
│   └── monitoring/                 # Monitoring scripts
│       ├── check_metrics.sh
│       └── view_logs.sh
│
├── src/
│   ├── auth/                       # Authentication & Authorization
│   │   ├── __init__.py
│   │   ├── wallet_verifier.py      # Verify Web3 wallet signatures
│   │   ├── token_validator.py      # Validate JWT tokens from zentalk-api
│   │   ├── permission_checker.py   # Check user permissions
│   │   └── session_manager.py      # Manage user sessions
│   │
│   ├── cache/                      # Caching layer
│   │   ├── __init__.py
│   │   ├── model_cache.py          # Cache loaded AI models
│   │   ├── result_cache.py         # Cache AI inference results
│   │   ├── mesh_cache_adapter.py   # Use mesh storage for distributed cache
│   │   ├── redis_adapter.py        # Redis cache integration
│   │   └── cache_strategy.py       # Cache eviction strategies
│   │
│   ├── client/                     # Secure API client used by frontend/API server
│   │   ├── __init__.py
│   │   ├── client_api.py           # Main client API interface
│   │   ├── encryption_adapter.py   # Encryption adapter for client
│   │   ├── websocket_client.py     # WebSocket client implementation
│   │   └── mesh_connector.py       # Secure access to Mesh DB
│   │
│   ├── distributed/                # Distributed computing
│   │   ├── __init__.py
│   │   ├── node_discovery.py       # Discover GPU nodes via DHT
│   │   ├── load_balancer.py        # Balance AI workload across nodes
│   │   ├── failover_handler.py     # Handle node failures
│   │   ├── peer_coordination.py    # Coordinate with other AI nodes
│   │   └── consensus.py            # Consensus mechanism for distributed tasks
│   │
│   ├── encryption/                 # Encryption & TEE integration
│   │   ├── __init__.py
│   │   ├── e2e_crypto.py           # End-to-end encryption (AES-GCM, X25519)
│   │   ├── secure_transport.py     # Encrypted data transfer protocols
│   │   ├── tee_manager.py          # Trusted Execution Environment management
│   │   └── key_exchange.py         # Key exchange protocols
│   │
│   ├── features/                   # AI features for messaging
│   │   ├── __init__.py
│   │   ├── smart_replies.py        # Generate smart reply suggestions
│   │   ├── message_summarization.py # Summarize conversations
│   │   ├── translation.py          # Message translation
│   │   ├── spam_detection.py       # Spam and abuse detection
│   │   ├── search_enhancement.py   # Semantic search enhancement
│   │   ├── auto_categorization.py  # Auto-categorize channels/chats
│   │   ├── sentiment_analysis.py   # Sentiment analysis
│   │   └── content_moderation.py   # Content moderation
│   │
│   ├── gpu/                        # GPU compute abstraction
│   │   ├── __init__.py
│   │   ├── executor.py             # Run jobs on local GPU (PyTorch)
│   │   ├── pool_manager.py         # Manage GPU worker pool
│   │   ├── job_queue.py            # Async job queue (Redis/RabbitMQ)
│   │   ├── monitor.py              # GPU health, load, temperature metrics
│   │   └── resource_allocator.py   # Allocate GPU resources efficiently
│   │
│   ├── integrations/               # Integration with zentalk ecosystem
│   │   ├── __init__.py
│   │   ├── mesh_storage.py         # Connect to zentalk-node mesh storage
│   │   ├── relay_client.py         # Connect to relay network
│   │   ├── api_bridge.py           # Bridge to zentalk-api
│   │   ├── websocket_relay.py      # WebSocket communication with relays
│   │   └── dht_client.py           # DHT client for peer discovery
│   │
│   ├── message_processing/         # Message processing pipeline
│   │   ├── __init__.py
│   │   ├── decrypt_handler.py      # Handle encrypted message input
│   │   ├── context_builder.py      # Build conversation context
│   │   ├── intent_detection.py     # Detect user intent
│   │   ├── entity_extraction.py    # Extract entities from messages
│   │   └── preprocessing.py        # Preprocess messages for AI
│   │
│   ├── models/                     # AI model definitions
│   │   ├── __init__.py
│   │   ├── llm/                    # Custom LLM models
│   │   │   ├── __init__.py
│   │   │   ├── base_model.py
│   │   │   ├── chat_model.py
│   │   │   ├── completion_model.py
│   │   │   └── fine_tuned_models.py
│   │   ├── loaders.py              # Model loading utilities
│   │   └── registry.py             # Model registry
│   │
│   ├── monitoring/                 # Monitoring & observability
│   │   ├── __init__.py
│   │   ├── metrics.py              # Prometheus metrics
│   │   ├── health_check.py         # Health check endpoints
│   │   ├── performance_tracker.py  # Track AI performance
│   │   ├── error_reporter.py       # Error reporting and alerting
│   │   └── telemetry_collector.py  # Collect telemetry data
│   │
│   ├── orchestrator/               # Distribute jobs across GPU nodes
│   │   ├── __init__.py
│   │   ├── scheduler.py            # Assign jobs based on node availability
│   │   ├── verifier.py             # Verify results (hash/TEE proof)
│   │   ├── rewards.py              # Compute CHAIN token reward logic
│   │   ├── registry.py             # Track node registration and reputation
│   │   ├── database_sync.py        # Sync job/reward info with Mesh DB
│   │   ├── payment_queue.py        # Queue CHAIN token payouts
│   │   └── task_manager.py         # Manage task lifecycle
│   │
│   ├── privacy/                    # Privacy & data protection
│   │   ├── __init__.py
│   │   ├── data_anonymization.py   # Anonymize data before AI processing
│   │   ├── local_processing.py     # Process data locally when possible
│   │   ├── privacy_filters.py      # Filter sensitive data
│   │   ├── audit_logger.py         # Privacy-compliant logging
│   │   └── gdpr_compliance.py      # GDPR compliance utilities
│   │
│   ├── realtime/                   # Real-time processing
│   │   ├── __init__.py
│   │   ├── stream_processor.py     # Process streaming AI requests
│   │   ├── websocket_handler.py    # WebSocket server for AI
│   │   ├── event_handler.py        # Handle real-time events
│   │   └── message_queue.py        # Real-time message queue
│   │
│   ├── server/                     # FastAPI app (entry point)
│   │   ├── __init__.py
│   │   ├── main.py                 # REST & WebSocket routes
│   │   │
│   │   ├── routes/                 # API route handlers
│   │   │   ├── __init__.py
│   │   │   ├── inference.py        # Inference endpoints
│   │   │   ├── models.py           # Model management endpoints
│   │   │   ├── status.py           # Status and health endpoints
│   │   │   ├── rewards.py          # Reward / proof endpoints
│   │   │   ├── admin.py            # Admin endpoints
│   │   │   ├── smart_replies.py    # Smart replies API
│   │   │   ├── summarization.py    # Summarization API
│   │   │   ├── translation.py      # Translation API
│   │   │   ├── search.py           # Search enhancement API
│   │   │   ├── websocket.py        # WebSocket endpoint
│   │   │   └── features.py         # Feature management
│   │   │
│   │   ├── middlewares/            # Middleware components
│   │   │   ├── __init__.py
│   │   │   ├── auth_middleware.py  # Authentication middleware
│   │   │   ├── encryption_middleware.py # Encryption middleware
│   │   │   ├── logging_middleware.py    # Logging middleware
│   │   │   ├── rate_limit_middleware.py # Rate limiting
│   │   │   └── validation_middleware.py # Request validation
│   │   │
│   │   └── dependencies.py         # Dependency injection
│   │
│   └── utils/                      # General utilities
│       ├── __init__.py
│       ├── logger.py               # Logging configuration
│       ├── config_loader.py        # Configuration loading utilities
│       ├── error_handler.py        # Error handling utilities
│       ├── telemetry.py            # Telemetry and metrics
│       ├── reward_utils.py         # CHAIN token calculation helpers
│       ├── crypto_utils.py         # Cryptographic utilities
│       ├── file_utils.py           # File handling utilities
│       └── network_utils.py        # Network utilities
│
├── tests/                          # Full test suite
│   ├── __init__.py
│   │
│   ├── unit/                       # Unit tests
│   │   ├── __init__.py
│   │   ├── test_auth.py
│   │   ├── test_cache.py
│   │   ├── test_encryption.py
│   │   ├── test_features.py
│   │   ├── test_gpu.py
│   │   ├── test_models.py
│   │   ├── test_orchestrator.py
│   │   ├── test_privacy.py
│   │   └── test_utils.py
│   │
│   ├── integration/                # Integration tests
│   │   ├── __init__.py
│   │   ├── test_mesh_integration.py      # Test mesh storage integration
│   │   ├── test_relay_communication.py   # Test relay communication
│   │   ├── test_api_bridge.py            # Test API bridge
│   │   ├── test_websocket_relay.py       # Test WebSocket relay
│   │   ├── test_end_to_end.py            # End-to-end tests
│   │   └── test_distributed_gpu.py       # Test distributed GPU
│   │
│   ├── performance/                # Performance tests
│   │   ├── __init__.py
│   │   ├── test_inference_speed.py
│   │   ├── test_gpu_utilization.py
│   │   ├── test_cache_performance.py
│   │   └── test_load_balancing.py
│   │
│   └── fixtures/                   # Test fixtures
│       ├── __init__.py
│       ├── mock_data.py
│       └── test_configs.py
│
├── data/                           # Optional local cache for models
│   ├── checkpoints/                # Model checkpoints
│   ├── temp/                       # Temporary files
│   ├── encrypted_cache/            # Store encrypted intermediate results
│   └── logs/                       # Log files
│
├── .env.example                    # Environment variables example
├── .gitignore                      # Git ignore file
├── .dockerignore                   # Docker ignore file
├── Dockerfile                      # Docker configuration
├── docker-compose.yml              # Docker Compose configuration
├── ARCHITECTURE.md                 # Docs for AI integration with network
├── CHANGELOG.md                    # Change log
├── CONTRIBUTING.md                 # Contribution guidelines
├── LICENSE                         # License file
├── config.example.yaml             # Example configuration
├── README.md                       # Project readme
├── requirements.txt                # Python dependencies
├── requirements-dev.txt            # Development dependencies
├── setup.py                        # Setup script
└── pyproject.toml                  # Python project configuration
```
