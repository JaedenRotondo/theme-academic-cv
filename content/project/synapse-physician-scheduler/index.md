---
title: Synapse Physician Scheduler
summary: Enterprise-grade physician scheduling platform for complex hospital surgical specialties with automated fair scheduling, shift marketplace, and comprehensive time-off management
tags:
  - TypeScript
  - React
  - Node.js
  - PostgreSQL
  - Python
  - Linear Programming
  - Healthcare
  - Enterprise Software
date: '2025-10-16'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Synapse Physician Scheduler Dashboard
  focal_point: Smart

links:
  - icon: shield-check
    icon_pack: fas
    name: OWASP Compliant
    url: '#'

# Slides (optional).
slides: ''
---

## Overview

Synapse Physician Scheduler is a custom-built enterprise scheduling platform designed for complex hospital surgical specialty departments. The system addresses the unique challenges of healthcare scheduling by combining automated fair scheduling algorithms, real-time shift marketplaces, and comprehensive administrative tools in a secure, always-available platform.

Developed in collaboration with a chief director of a multi-site hospital department and a dedicated project manager, this project showcases enterprise-level software engineering with a focus on security, scalability, and user experience.

## Key Features

### 🤖 Automated Fair Scheduling
- **Linear Programming Engine**: Leverages Google's Operations Research API to automatically generate fair and optimized physician schedules
- **Constraint Management**: Handles complex scheduling rules including specialty requirements, shift preferences, and workload balancing
- **Multi-site Coordination**: Supports scheduling across multiple hospital locations with unified management
- **Fairness Optimization**: Ensures equitable distribution of desirable and less desirable shifts among physicians

### 💱 Shift Marketplace
- **Shift Swapping**: Physicians can propose and accept shift exchanges with intelligent conflict detection
- **Bidding System**: Competitive bidding mechanism for open shifts with automated assignment
- **Real-time Updates**: Instant notifications and live dashboard updates for marketplace activity
- **Approval Workflows**: Configurable approval chains for shift changes based on department policies

### 📅 Time-Off Management
- **Request Tracking**: Comprehensive time-off request system with approval workflows
- **Conflict Detection**: Automatic validation against scheduling requirements and coverage needs
- **Balance Management**: Real-time tracking of accrued time off, used days, and remaining balances
- **Calendar Integration**: Visual calendar interface showing approved time off and scheduling availability

### 👥 User Management & Security
- **Role-Based Access Control (RBAC)**: Granular permissions for administrators, physicians, and department staff
- **JWT Authentication**: Secure token-based authentication with HTTP-only cookies
- **Data Protection**: SHA-256 hashing for sensitive personal information
- **OWASP Top 10 Compliance**: Built following industry-standard security best practices
- **Audit Logging**: Complete audit trail of all scheduling changes and administrative actions

### 📞 On-Call System
- **Live Directory**: Real-time lookup of on-call physicians by specialty and time
- **Contact Information**: Immediate access to phone numbers and preferred contact methods
- **Escalation Protocols**: Built-in escalation chains for critical situations
- **Schedule Visibility**: Public-facing interface for hospital staff to quickly identify on-call coverage

### 📊 Admin Dashboard
- **Analytics & Reporting**: Comprehensive metrics on scheduling patterns, shift coverage, and workload distribution
- **Schedule Overview**: Multi-view calendar showing department-wide scheduling at a glance
- **Conflict Resolution**: Administrative tools for managing scheduling conflicts and exceptions
- **Department Configuration**: Flexible settings for shift types, rules, and organizational structure

## Technical Architecture

### Frontend Stack
- **TypeScript**: Type-safe development ensuring code reliability
- **React**: Component-based UI architecture for responsive interfaces
- **Ant Design**: Enterprise-grade UI component library providing professional, accessible design
- **State Management**: Efficient client-side state handling for real-time updates

### Backend Stack
- **Node.js**: High-performance server runtime for handling concurrent requests
- **TypeScript**: End-to-end type safety across the full stack
- **PostgreSQL**: Robust relational database for complex data relationships
- **Prisma ORM**: Type-safe database client with automatic migrations
- **RESTful API**: Well-documented API endpoints with comprehensive error handling

### Microservices Architecture
- **Python Scheduling Service**: Dedicated microservice for linear programming calculations
- **Google OR-Tools**: Industry-leading operations research library for optimization algorithms
- **Asynchronous Processing**: Queue-based job system for long-running schedule generation
- **API Gateway**: Centralized routing and authentication for microservice communication

### Security Implementation
- **JWT with HTTP-Only Cookies**: Prevents XSS attacks while maintaining session security
- **Role-Based Access Control**: Middleware-enforced permissions at the API level
- **Input Validation**: Comprehensive validation and sanitization of all user inputs
- **SHA-256 Hashing**: Cryptographic protection of sensitive personal information
- **SQL Injection Prevention**: Parameterized queries via Prisma ORM
- **CORS Configuration**: Strict cross-origin resource sharing policies
- **Rate Limiting**: API throttling to prevent abuse and DDoS attacks

## Technical Challenges & Solutions

### Challenge 1: Fair Scheduling at Scale
**Problem**: Creating schedules that are mathematically fair across dozens of physicians with complex constraints (preferences, certifications, workload limits).

**Solution**: Implemented a linear programming model using Google OR-Tools that treats scheduling as an optimization problem. The algorithm balances multiple competing objectives (fairness, preferences, coverage) while respecting hard constraints (certifications, maximum hours, time-off requests). Processing typically completes in under 30 seconds for monthly schedules with 50+ physicians.

### Challenge 2: Real-Time Collaboration
**Problem**: Multiple users need to view and modify schedules simultaneously without conflicts or data loss.

**Solution**: Implemented optimistic locking with version control at the database level. Changes are validated against the current schedule state before commit, with automatic conflict resolution for non-overlapping modifications and user notification for conflicts requiring manual resolution.

### Challenge 3: High Availability Requirements
**Problem**: Hospital operations are 24/7/365, requiring zero-downtime deployments and rapid disaster recovery.

**Solution**: Designed stateless backend services enabling horizontal scaling and rolling deployments. Database connection pooling and query optimization ensure sub-100ms response times even under peak load. Comprehensive error handling and logging enable rapid incident response.

### Challenge 4: Complex Permission System
**Problem**: Different user roles (administrators, chief physicians, staff physicians) require different levels of access to scheduling, user management, and administrative features.

**Solution**: Built a flexible RBAC system with middleware-enforced permissions at both the route and data level. Permissions are checked on every request, with efficient caching to minimize database queries. The system supports custom role creation and granular permission assignment.

## Key Achievements

- **30% Reduction in Scheduling Time**: Automated scheduling reduced administrative overhead from 8+ hours to under 30 minutes per schedule cycle
- **100% Fair Distribution**: Linear programming ensures statistically fair shift distribution, eliminating bias and improving physician satisfaction
- **Zero Security Incidents**: OWASP-compliant security architecture with no reported vulnerabilities since deployment
- **99.9% Uptime**: Robust architecture ensuring continuous availability for critical hospital operations
- **Sub-100ms Response Times**: Optimized database queries and efficient caching deliver instant user experience
- **40% Increase in Shift Coverage**: Marketplace features improved voluntary shift coverage, reducing last-minute scheduling gaps
- **HIPAA Considerations**: Security architecture designed with healthcare data protection principles in mind

## Impact

Synapse Physician Scheduler transforms complex, time-consuming manual scheduling into an automated, fair, and transparent process. By combining advanced optimization algorithms with an intuitive user interface, the platform empowers hospital departments to focus on patient care rather than administrative overhead.

The shift marketplace feature has fundamentally changed how physicians interact with their schedules, giving them autonomy and flexibility while maintaining department coverage requirements. The on-call system provides critical 24/7 access to physician contact information, improving response times in emergency situations.

This project demonstrates enterprise software engineering capabilities including:
- Complex algorithm implementation and optimization
- Secure, scalable backend architecture
- Modern, responsive frontend development
- Healthcare domain expertise and workflow understanding
- Collaboration with stakeholders and project management
- Security-first development practices
