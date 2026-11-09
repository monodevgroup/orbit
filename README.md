# Orbit 🚀

![build](https://img.shields.io/badge/build-passing-brightgreen) ![license](https://img.shields.io/badge/license-MIT-blue) ![Kotlin](https://img.shields.io/badge/Kotlin-2.0-7F52FF)

A tiny, **coroutine-first** HTTP client for Kotlin — 48 KB, no reflection.

> [!NOTE]
> Orbit is a sample project for the MarkDev – Markdown Editor screenshots.

## Install

```kotlin
dependencies {
    implementation("dev.orbit:orbit:2.0.0")
}
```

## Quick start

```kotlin
val orbit = Orbit("https://api.example.com")

suspend fun loadUser(id: Int): User =
    orbit.get("/users/$id").body<User>()
```

## How a request flows

```mermaid
flowchart LR
    A[App] -->|request| B(Orbit)
    B --> C{Cached?}
    C -->|yes| A
    C -->|no| D[(API)]
    D --> B
```

## Roadmap

- [x] HTTP/2 and retries
- [x] Offline cache
- [ ] WebSockets
