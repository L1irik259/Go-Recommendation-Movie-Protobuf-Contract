# Go Recommendation Movie Protobuf Contract

Контракт gRPC/Protobuf для сервиса рекомендаций фильмов. Исходный протокол описан в [proto/ml/v1/predict.proto](proto/ml/v1/predict.proto), а Go-артефакты сгенерированы в [genetation/go/ml/v1/predict.pb.go](genetation/go/ml/v1/predict.pb.go) и [genetation/go/ml/v1/predict_grpc.pb.go](genetation/go/ml/v1/predict_grpc.pb.go).

## Содержимое
- gRPC сервис: [`recommendationService.RecommendationService`](proto/ml/v1/predict.proto)
- Запрос: [`recommendationService.RecommendationsRequest`](proto/ml/v1/predict.proto)
- Ответ: [`recommendationService.RecommendationsResponse`](proto/ml/v1/predict.proto)
- Вложенная структура рейтинга: [`recommendationService.ServeyReting`](proto/ml/v1/predict.proto)
- Go-клиент/сервер: [`mlv1.RecommendationServiceClient`](genetation/go/ml/v1/predict_grpc.pb.go), [`mlv1.RecommendationServiceServer`](genetation/go/ml/v1/predict_grpc.pb.go)

## RPC методы
### GetRecommendations
`rpc GetRecommendations(RecommendationsRequest) returns (RecommendationsResponse);`

**Request** — [`recommendationService.RecommendationsRequest`](proto/ml/v1/predict.proto)
- `user_id`: string
- `servey_reting`: repeated [`recommendationService.ServeyReting`](proto/ml/v1/predict.proto)

**ServeyReting** — [`recommendationService.ServeyReting`](proto/ml/v1/predict.proto)
- `movie_id`: int32
- `rating`: optional int32
- `flag_watched`: bool

**Response** — [`recommendationService.RecommendationsResponse`](proto/ml/v1/predict.proto)
- `user_id`: string
- `arr_movie_id`: repeated int32

## Генерация
Протокол описан в [proto/ml/v1/predict.proto](proto/ml/v1/predict.proto). Go-код находится в:
- [genetation/go/ml/v1/predict.pb.go](genetation/go/ml/v1/predict.pb.go)
- [genetation/go/ml/v1/predict_grpc.pb.go](genetation/go/ml/v1/predict_grpc.pb.go)

> Файлы в папке `genetation/` являются сгенерированными и не должны редактироваться вручную.