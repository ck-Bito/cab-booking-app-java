# Injected Bugs Report

## AuthService.java
File: src/main/java/com/uberclone/service/AuthService.java
Line Number: 45
Bug Type: Return-Type Drift
Description: Changed return type of register method to return Optional<AuthResponse> instead of AuthResponse, breaking type consistency with callers.

File: src/main/java/com/uberclone/service/AuthService.java
Line Number: 65
Bug Type: Exception-Flow Corruption
Description: Removed exception handling in login method, allowing authentication exceptions to propagate unexpectedly.

File: src/main/java/com/uberclone/service/AuthService.java
Line Number: 75
Bug Type: Sensitive Data Logging
Description: Added plaintext password logging in forgotPassword method.

## UserService.java
File: src/main/java/com/uberclone/service/UserService.java
Line Number: 30
Bug Type: Hidden State Mutation
Description: Introduced global state mutation in user profile update method.

## DriverService.java
File: src/main/java/com/uberclone/service/DriverService.java
Line Number: 25
Bug Type: Async/Sync Mismatch
Description: Changed async method to sync without updating callers.

## BookingService.java
File: src/main/java/com/uberclone/service/BookingService.java
Line Number: 40
Bug Type: Memory Leak
Description: Opened database connection without proper closure.

## PaymentService.java
File: src/main/java/com/uberclone/service/PaymentService.java
Line Number: 35
Bug Type: SQL Injection
Description: Replaced parameterized query with string concatenation.

## NotificationService.java
File: src/main/java/com/uberclone/service/NotificationService.java
Line Number: 20
Bug Type: Circular Dependencies
Description: Added circular import with EmailService.

## Cab.java
File: src/main/java/com/uberclone/model/Cab.java
Line Number: 15
Bug Type: Schema Deviation
Description: Changed field type from int to String for cabId.

## Ride.java
File: src/main/java/com/uberclone/model/Ride.java
Line Number: 25
Bug Type: Misleading Type Annotations
Description: Replaced specific type with Any for rideStatus.

## User.java
File: src/main/java/com/uberclone/model/User.java
Line Number: 30
Bug Type: Shadowing Imports
Description: Shadowed built-in List type with custom implementation.

## Driver.java
File: src/main/java/com/uberclone/model/Driver.java
Line Number: 20
Bug Type: Interface Satisfaction Through Embedding Chain
Description: Broke interface contract by changing method signature. 