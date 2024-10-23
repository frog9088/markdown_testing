# RecommendTripService Documentation

## 1. Overall Structure

### Purpose
The `RecommendTripService` manages trip recommendations for users, handling operations related to creating and managing recommended trips for members.

### High-Level Overview
```mermaid
classDiagram
    class RecommendTripService {
        -TripFilterStrategyProvider tripFilterStrategyProvider
        -RecommendTripRepository recommendTripRepository
        -MemberRepository memberRepository
        -TripRepository tripRepository
        -TripKeywordRepository tripKeywordRepository
        +saveByRank(Trip, Member, long)
        +createRecommendTrip(long, RecommendTripCreateRequest)
    }
    
    class TripFilterStrategyProvider {
        +findTripsByFilterStrategy(String)
    }
    
    class RecommendTripRepository {
        +save(RecommendTrip)
    }
    
    class MemberRepository {
        +findById(Long)
    }
    
    class TripRepository {
        +findById(Long)
    }

    RecommendTripService --> TripFilterStrategyProvider
    RecommendTripService --> RecommendTripRepository
    RecommendTripService --> MemberRepository
    RecommendTripService --> TripRepository
    RecommendTripService --> TripKeywordRepository
```

## 2. Strategy Pattern Implementation

```mermaid
classDiagram
    class TripFilterStrategy {
        <<interface>>
        +isMatch(String)
        +execute(FilterStandardInfo)
    }
    
    class TripFilterStrategyProvider {
        -List~TripFilterStrategy~ strategies
        +findTripsByFilterStrategy(String)
    }
    
    class FilterStandardInfo {
        <<interface>>
        +getInfo()
    }
    
    class PreferredLocationsFilterInfo {
        -Long memberId
        +getInfo()
    }

    TripFilterStrategyProvider --> TripFilterStrategy
    PreferredLocationsFilterInfo ..|> FilterStandardInfo
```

## 3. Detailed Component Documentation

### Classes

#### RecommendTripService
- **Purpose**: Manages trip recommendations and related operations
- **Scope**: `@Service`, `@Transactional(readOnly = true)`
- **Dependencies**:
  - TripFilterStrategyProvider
  - RecommendTripRepository
  - MemberRepository
  - TripRepository
  - TripKeywordRepository

### Methods

#### saveByRank
```java
@Transactional
public void saveByRank(Trip trip, Member member, long rank)
```
- **Purpose**: Saves a recommended trip with specific ranking
- **Parameters**:
  - `trip`: Trip entity to recommend
  - `member`: Member entity for whom the recommendation is made
  - `rank`: Ranking position of the recommendation
- **Behavior**: Creates and saves new RecommendTrip entity

#### createRecommendTrip
```java
@Transactional
public void createRecommendTrip(long memberId, RecommendTripCreateRequest request)
```
- **Purpose**: Creates a new trip recommendation
- **Parameters**:
  - `memberId`: ID of the member
  - `request`: DTO containing trip ID
- **Behavior**: 
  - Validates member and trip existence
  - Creates and saves new recommendation
- **Exceptions**:
  - `NoExistMemberException`
  - `NoExistTripException`

## 4. Implementation Flow

```mermaid
sequenceDiagram
    participant Client
    participant RecommendTripService
    participant MemberRepository
    participant TripRepository
    participant RecommendTripRepository

    Client->>RecommendTripService: createRecommendTrip(memberId, request)
    RecommendTripService->>MemberRepository: findById(memberId)
    MemberRepository-->>RecommendTripService: Member
    RecommendTripService->>TripRepository: findById(tripId)
    TripRepository-->>RecommendTripService: Trip
    RecommendTripService->>RecommendTripRepository: save(new RecommendTrip)
    RecommendTripRepository-->>RecommendTripService: void
    RecommendTripService-->>Client: void
```
