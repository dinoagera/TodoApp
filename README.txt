microservices-project/
│── api-service/          # API сервис (принимает запросы, общается с БД-сервисом, отправляет события в Kafka)
│   ├── cmd/              # Точка входа в приложение (main.go)
│   ├── internal/         
│   │   ├── handlers/     # HTTP-хендлеры (Gin/Fiber)
│   │   ├── services/     # Логика работы API
│   │   ├── kafka/        # Kafka продюсер
│   │   └── config/       # Настройки
│   ├── Dockerfile        # Docker-образ API-сервиса
│   ├── go.mod           
│   ├── go.sum           
│   └── README.md        
│
│── db-service/           # БД-сервис (работает с PostgreSQL и Redis, предоставляет API/gRPC)
│   ├── cmd/              
│   ├── internal/         
│   │   ├── repository/   # Работа с БД (PostgreSQL)
│   │   ├── cache/        # Работа с Redis
│   │   ├── grpc/         # gRPC-сервер
│   │   ├── models/       # Модели данных
│   │   ├── config/       # Настройки
│   ├── proto/            # gRPC-протокол
│   ├── Dockerfile        
│   ├── go.mod           
│   ├── go.sum           
│   └── README.md        
│
│── kafka-service/        # Kafka-сервис (обработчик событий из Kafka)
│   ├── cmd/              
│   ├── internal/         
│   │   ├── consumer/     # Kafka консьюмер
│   │   ├── handlers/     # Логика обработки сообщений
│   ├── Dockerfile        
│   ├── go.mod           
│   ├── go.sum           
│   └── README.md        
│
│── config/               # Файлы конфигурации
│   ├── config.yaml       
│   ├── .env             
│   ├── migrations/       # SQL-скрипты для миграций PostgreSQL
│   └── README.md        
│
│── deployments/          # Файлы для развертывания (Docker, Kubernetes)
│   ├── docker-compose.yml
│   ├── k8s/             # Манифесты Kubernetes (если потребуется)
│   └── README.md        
│
│── docs/                 # Документация проекта
│   ├── API_spec.md      
│   ├── Architecture.md  
│   └── README.md        
│
│── tests/                # Интеграционные и нагрузочные тесты
│   ├── api-tests/       
│   ├── db-tests/        
│   └── README.md        
│
│── .gitignore            # Исключения для Git
│── README.md             # Документация проекта


zaebalsy protoc --proto_path=. --go_out=gen/go --go-grpc_out=gen/go myservice/service.proto

