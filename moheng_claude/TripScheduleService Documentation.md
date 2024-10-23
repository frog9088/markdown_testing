# TripScheduleService Documentation

## 1. Overall Structure

### Purpose
The `TripScheduleService` manages trip schedules and their associated trips in a travel planning system. It handles operations like creating schedules, adding trips to schedules, and managing trip orders within schedules.

### Component Relationships

```mermaid
classDiagram
    class TripScheduleService {
        -MemberRepository memberRepository
        -TripScheduleRepository tripScheduleRepository
        -TripRepository tripRepository
        -TripScheduleRegistryRepository tripScheduleRegistryRepository
        +createTripSchedule()
        +addCurrentTripOnPlannerSchedule()
        +findTripsOnSchedule()
        +updateTripOrdersOnSchedule()
        +deleteTripOnSchedule()
    }
    
    class TripSchedule {
        -Long id
        -String name
        -LocalDate startDate
        -LocalDate endDate
        -Member member
    }
    
    class TripScheduleRegistry {
        -Long id
        -Trip trip
        -TripSchedule tripSchedule
    }
    
    class Trip {
        -Long id
        -String name
        -String placeName
        -String description
    }
    
    TripScheduleService --> TripSchedule : manages
    TripScheduleService --> TripScheduleRegistry : manages
    TripSchedule --> Member : belongs to
    TripScheduleRegistry --> Trip : contains
    TripScheduleRegistry --> TripSchedule : references
```

## 2. Detailed Component Documentation

### Classes

#### TripScheduleService
Main service class handling trip schedule operations.

**Dependencies:**
- `MemberRepository`
- `TripScheduleRepository`
- `TripRepository`
- `TripScheduleRegistryRepository`

### Methods

#### createTripSchedule
```java
@Transactional
public void createTripSchedule(long memberId, CreateTripScheduleRequest request)
```
Creates a new trip schedule for a member.

**Parameters:**
- `memberId`: ID of the member creating the schedule
- `request`: Contains schedule details (name, dates)

#### addCurrentTripOnPlannerSchedule
```java
@Transactional
public void addCurrentTripOnPlannerSchedule(long tripId, AddTripOnScheduleRequests requests)
```
Adds a trip to multiple schedules.

**Parameters:**
- `tripId`: ID of the trip to add
- `requests`: Contains list of schedule IDs

#### findTripsOnSchedule
```java
public FindTripsOnSchedule findTripsOnSchedule(long scheduleId)
```
Retrieves all trips associated with a schedule.

**Parameters:**
- `scheduleId`: ID of the schedule to query

## 3. Implementation Flow

```mermaid
sequenceDiagram
    participant Client
    participant TripScheduleService
    participant Repositories
    participant Entities

    Client->>TripScheduleService: createTripSchedule(memberId, request)
    TripScheduleService->>Repositories: findById(memberId)
    Repositories-->>TripScheduleService: Member
    TripScheduleService->>Repositories: existsByMemberAndName(member, name)
    Repositories-->>TripScheduleService: boolean
    TripScheduleService->>Entities: new TripSchedule(...)
    TripScheduleService->>Repositories: save(tripSchedule)
    TripScheduleService-->>Client: void
```

## 4. Transaction Management
- Service is annotated with `@Transactional(readOnly = true)`
- Write operations are explicitly marked with `@Transactional`
- Ensures data consistency across operations

## 5. Error Handling
Throws various exceptions:
- `NoExistMemberException`
- `AlreadyExistTripScheduleException`
- `NoExistTripScheduleException`
- `NoExistTripException`
- `NoExistTripScheduleRegistryException`
