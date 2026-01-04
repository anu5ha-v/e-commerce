E-commerce – Final Project

Objective

The objective of this project is to gain hands-on experience in designing and developing an end-to-end Java Spring Boot application using microservices architecture.

This project aims to:

Apply concepts learned during the bootcamp in a real-world scenario

Understand system design, API design, and service-to-service communication

Build secure, scalable, and maintainable backend services

Simulate real-world software engineering practices

Constraints

Individual project

Backend-only project (API development only)

Usage of AI-assisted tools (e.g., Cursor, Copilot, etc.) is allowed, but the developer must fully understand the generated code

Business Requirement

Build an Online Marketplace Platform that supports:

Customer registration and authentication

Product browsing and search

Shopping cart management

Secure logout functionality

Use Case APIs
1. Customer Registration & Login

Customers can register and login

Password must be hashed using Spring’s built-in password hashing utilities

Password validation must use Spring Security standards

Authentication must use JWT (JWS) with either symmetric or asymmetric keys

2. Product Search & Browsing

Customers can:

Search products

View product list

View product details

Product list and search results must be paginated

Search must support wildcard queries

3. Shopping Cart Management

Customers can add products to cart

User must be authenticated

Inventory stock can be assumed as unlimited

Customers can view and remove products from the cart

Authentication required

JWT validation via cookie-based or header-based authentication

4. Logout

Customers can logout by:

Invalidating JWT cookie, or

Discarding JWT token (stateless logout)

Technical Requirements
Microservices Architecture

The system must consist of at least 4 microservices:

API Gateway

Member Service

Product Service

Cart Service

Development Scope

API development only

No frontend or client-side application required

Authentication & Authorization

Authentication and authorization must be handled at the API Gateway

JWT validation must occur only at the gateway

Backend services should trust user identity forwarded by the gateway

Search Implementation

Product search can be implemented using:

PostgreSQL or MongoDB

Elasticsearch is optional and can be used for advanced search capabilities

Technology Stack

Java, Spring Boot

PostgreSQL for relational data

MongoDB for document-based data

Redis for caching

Database choice should be based on the domain model suitability

Testing

Implement:

Unit tests

Integration tests

Data Size Requirements

Member Service: minimum 5,000 users

Product Service: minimum 50,000 products

Architecture Overview
Deployment Architecture

API Gateway acts as the single entry point

Backend services:

Member Service

Product Service

Cart Service

All client requests flow through the API Gateway

Authentication & Authorization Flow

Registration handled by Member Service

Login validated by Member Service

JWT creation and validation handled by API Gateway

JWT can be passed via:

HttpOnly cookies

Authorization header (Bearer token)

Gateway forwards validated user_id to downstream services

Stateless authentication (no server-side sessions)

Process & Timeline
Repository & Git Flow

Fork the base repository

Follow standard Git flow:

Feature branches

Release branch

Create a pull request from the release branch to the main repository

Timeline

Design and development duration: 5 days

Extra Challenges (Optional)

Dockerize all microservices

Deploy services on Kubernetes

Implement search using Elasticsearch or Solr

Use gRPC instead of REST APIs

Apply suitable Design Patterns where applicable
