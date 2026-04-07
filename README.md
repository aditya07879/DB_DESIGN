###DAY 2

# Online Fitness Coaching Platform — Database Design

Database design for an online fitness coaching platform where trainers manage clients, sell coaching plans, schedule sessions, track progress, and handle subscriptions.

## Entities

### Users

Stores both trainers and clients.

* role → `trainer` or `client`

### Plans

Coaching programs created by trainers.

* Includes price and duration
* One trainer can create many plans

### Subscriptions

Represents client enrollment in a plan.

* Tracks start and end date
* A client can purchase multiple plans over time

### Sessions

Scheduled consultations or live coaching calls.

* One trainer ↔ one client
* type → consultation | live_session

### Check-ins

Weekly or periodic updates submitted by clients.

* Used for progress tracking
* Trainer reviews these

### Progress

Body measurements linked to check-ins.

* weight
* body fat
* chest
* waist
* hips

### Trainer Notes

Feedback provided by trainer on check-ins.

### Payments

Payment records for subscriptions.

* Stores method and payment status

## Relationships

* One trainer → many plans
* One client → many subscriptions
* One plan → many subscriptions
* One trainer → many clients
* One subscription → one payment (can be extended to many)
* One trainer → many sessions
* One client → many sessions
* One client → many check-ins
* One check-in → one progress record
* One check-in → trainer feedback

## Business Rules

* Users table stores both trainers and clients
* Clients can buy multiple plans over time
* Plans can be purchased by multiple clients
* Sessions are separate from check-ins
* Progress is tracked through check-ins
* Trainer feedback stored separately
* Payments linked to subscriptions
* Trainers manage multiple clients simultaneously

## Flow

Client → buys plan → subscription created
Subscription → payment recorded
Trainer → schedules sessions
Client → submits check-in
Check-in → progress stored
Trainer → adds notes
