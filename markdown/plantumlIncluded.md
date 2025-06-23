# System Architecture Overview

This document provides an overview of the system's high-level architecture.

## UML Diagram

The following PlantUML diagram illustrates the key components of the architecture.

```plantuml
@startuml
title High-Level System Architecture

actor User
rectangle "Web App" {
  User --> WebApp : HTTP Request
  WebApp --> "Auth Service" : Auth Request
  WebApp --> "Backend API" : REST Call
}
rectangle "Backend API" {
  "Backend API" --> "Database" : SQL Query
  "Backend API" --> "External API" : HTTPS Request
}

@enduml
