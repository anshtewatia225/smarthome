# Smart Home Automation System

A Java-based Smart Home Automation System that demonstrates core OOP principles including inheritance, polymorphism, abstraction, interfaces, and multithreading. The system simulates a smart home environment with device management, user authentication, automation rules, and security features.

## 🗂 Project Structure

```text
com/smarthome/
├── SmartHomeSystem.java          # Main system controller & CLI entry point
├── devices/
│   ├── Device.java               # Abstract base class for all devices
│   ├── EnergyMonitored.java      # Interface for energy tracking
│   ├── LightDevice.java          # Smart light with brightness control
│   ├── ThermostatDevice.java     # Smart thermostat with temperature control
│   └── SecurityDevice.java       # Security camera/sensor/alarm
├── automation/
│   ├── AutomationRule.java       # Interface for automation rules
│   ├── TimeBasedRule.java        # Rules triggered at specific times
│   ├── EventBasedRule.java       # Rules triggered by device events
│   └── ScheduledRule.java        # Rules triggered on specific days/times
├── users/
│   ├── User.java                 # Abstract base class for users
│   ├── AdminUser.java            # Admin with full permissions
│   └── RegularUser.java          # Regular user with limited permissions
├── security/
│   ├── SecurityManager.java      # Token-based access management
│   ├── SecurityLogger.java       # Security event logging
│   └── PermissionManager.java    # User & device permission management
├── utils/
│   └── Logger.java               # System-wide logging utility
└── ui/    
    └── SmartHomeGUI.java         # Swing-based graphical interface
```

## ✨ Key Features

- **Device Management**: Add, remove, and control smart home devices (lights, thermostats, security cameras)
- **User Authentication**: Login system with role-based access control (Admin/Regular users)
- **Automation Rules**: Time-based, event-based, and scheduled automation
- **Energy Monitoring**: Track energy consumption per device
- **Security Module**: Access token management, permission control, and security event logging
- **Dual Interface**: Both CLI and Swing GUI available
- **Multithreading**: Background device monitoring with daemon threads
- **Persistence**: Configuration save/load via Java serialization

## 🧠 OOP Concepts Demonstrated

| Concept | Implementation |
|---|---|
| **Abstraction** | `Device` (abstract class), `User` (abstract class) |
| **Interfaces** | `AutomationRule`, `EnergyMonitored` |
| **Inheritance** | `LightDevice`, `ThermostatDevice`, `SecurityDevice` extend `Device`; `AdminUser`, `RegularUser` extend `User` |
| **Polymorphism** | Method overriding (`turnOn()`, `turnOff()`, `getDeviceType()`, `hasPermission()`); Method overloading (`addDevice()`, `addUser()` with varargs) |
| **Encapsulation** | Private fields with public getters/setters across all classes |
| **Inner Classes** | `DeviceMonitor` (inner class in `SmartHomeSystem`), `Encryptor` (static nested class in `SecurityManager`) |
| **Enums** | `SecurityDevice.Type`, `Logger.LogLevel`, `SecurityLogger.LogLevel` |
| **Serialization** | `Device`, `User`, `AutomationRule` implement `Serializable` |
| **Multithreading** | `DeviceMonitor` implements `Runnable` for background monitoring |
| **Lambda Expressions** | Used in automation rule actions and Swing event listeners |

## 🚀 How to Run

### Prerequisites
- Java JDK 8 or higher

### Compile

```bash
# From the project root directory
javac com/smarthome/SmartHomeSystem.java
```

### Run CLI Mode

```bash
java com.smarthome.SmartHomeSystem
```

### Run GUI Mode

```bash
java com.smarthome.ui.SmartHomeGUI
```

### Default Login Credentials

| Username | Password | Role |
|---|---|---|
| `admin` | `admin123` | Administrator |

## 🛠️ Technologies Used
- **Language**: Java
- **GUI**: Java Swing
- **Concurrency**: Java Threads
- **I/O**: Java Serialization, File I/O
- **Date/Time**: Java `java.time` API
