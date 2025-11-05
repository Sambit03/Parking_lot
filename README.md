# Parking Lot System - Source Code

This directory contains the TypeScript implementation of the Smart Parking Lot System based on Low-Level System Design principles.

## File Structure

```
src/
├── types.ts              # Type definitions (ID)
├── VehicleType.ts        # Enum for vehicle types
├── ParkingSpotType.ts    # Enum for parking spot types
├── Vehicle.ts            # Vehicle class
├── ParkingSpot.ts        # ParkingSpot class
├── ParkingFloor.ts       # ParkingFloor class
├── ParkingTicket.ts      # ParkingTicket class
├── PaymentProcessor.ts   # PaymentProcessor class
├── EntryPanel.ts         # EntryPanel class
├── ExitPanel.ts          # ExitPanel class
├── DisplayPanel.ts       # DisplayPanel class
├── ParkingLot.ts         # ParkingLot class (main coordinator)
├── Main.ts               # Demo/Test file
└── index.ts              # Export file
```

### Core Entities

- **Vehicle**: Represents a vehicle with ID and type
- **ParkingSpot**: Individual parking spot with occupancy tracking
- **ParkingFloor**: Manages multiple parking spots on a floor
- **ParkingTicket**: Ticket issued when vehicle enters

### System Components

- **EntryPanel**: Handles vehicle check-in and ticket generation
- **ExitPanel**: Handles vehicle check-out and payment processing
- **PaymentProcessor**: Processes parking fee payments
- **DisplayPanel**: Shows real-time parking availability
- **ParkingLot**: Main coordinator that ties everything together

### Enums & Types

- **VehicleType**: CAR, TRUCK, BUS, MOTORCYCLE, BICYCLE
- **ParkingSpotType**: REGULAR, HANDICAPPED, ELECTRIC
- **ID**: String type alias for identifiers

## Running the Demo

To compile and run the TypeScript files:

```bash
# Install TypeScript if not installed
npm install -g typescript

# Compile TypeScript files
tsc src/Main.ts --outDir dist --module commonjs --target ES2020 --esModuleInterop

# Run the compiled JavaScript
node dist/Main.js
```

Or use ts-node for direct execution:

```bash
# Install ts-node if not installed
npm install -g ts-node

# Run directly
ts-node src/Main.ts
```

## Key Features Implemented

1. ✅ **Multi-floor Support**: System handles multiple parking floors
2. ✅ **Multiple Vehicle Types**: CAR, TRUCK, BUS, MOTORCYCLE, BICYCLE
3. ✅ **Multiple Spot Types**: REGULAR, HANDICAPPED, ELECTRIC
4. ✅ **Automatic Spot Allocation**: Simple first-available algorithm
5. ✅ **Dynamic Fee Calculation**: Based on vehicle type and duration
6. ✅ **Maintenance Mode**: Floors and spots can be marked under maintenance
7. ✅ **Real-time Availability**: Display panel shows current status
8. ✅ **Payment Processing**: Simulated payment gateway integration

## Pricing Structure

| Vehicle Type | Rate per Hour |
| ------------ | ------------- |
| Bicycle      | 10.00         |
| Motorcycle   | 20.00         |
| Car          | 50.00         |
| Truck        | 200.00        |
| Bus          | 200.00        |

**Rules:**

- Minimum charge: 1 hour
- Maximum charge: 24 hours (daily cap)

## System Flow

### Vehicle Entry

1. Vehicle arrives at entry panel
2. System checks for available spots
3. Spot is allocated based on vehicle type
4. Parking ticket is generated
5. Vehicle parks in assigned spot

### Vehicle Exit

1. Vehicle arrives at exit panel with ticket
2. Exit time is recorded
3. Parking fee is calculated
4. Payment is processed
5. Parking spot is released
6. Vehicle exits

## Design Patterns Used

- **Factory Pattern**: Spot type generation based on vehicle type
- **Strategy Pattern**: Fee calculation based on vehicle type
- **Observer Pattern**: Display panel observes parking lot state
- **Facade Pattern**: ParkingLot class provides simplified interface

## Extensibility

The system can be extended with:

- Database integration for persistence
- WebSocket for real-time updates
- REST API for external access
- Mobile app integration
- Advanced allocation algorithms (closest to entrance, load balancing)
- Reservation system
- User management and loyalty programs
- Multiple payment methods
- Analytics and reporting

## Notes

- All console.log statements are for demonstration purposes
- In production, replace with proper logging framework
- Payment processing is simulated; integrate with real gateway
- Error handling can be enhanced with custom error classes
- Add unit tests for each class

UML_diagram mermaidchart.png
