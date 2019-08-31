# chi-logger
===
`chi-logger` is a simple logging middleware for [Chi](https://github.com/go-chi/chi) with support for `Zap` and `Logrus`

This fork by Tektite Software supports Go Modules.

Installation
---

    go get github.com/tektite-software/chi-logger

Usage with Logrus
---

    import "gitub.com/tektite-software/chi-logger/chilogger"

    logger := logrus.New()

    r := chi.NewRouter()
    r.Use(middleware.RequestID)
    r.Use(middleware.RealIP)
    r.Use(chilogger.NewLogrusMiddleware("router", logger))
    ...

Usage with Zap
---

    import "gitub.com/tektite-software/chi-logger/chilogger"

    logger, _ := zap.NewProduction()

    r := chi.NewRouter()
    r.Use(middleware.RequestID)
    r.Use(middleware.RealIP)
    r.Use(chilogger.NewZapMiddleware("router", logger))
    ...
