classDiagram
    Food -- Singleroom : contains
    Singleroom <|-- Doubleroom
    Exception <|-- NotAvailable
    holder -- Doubleroom : contains
    holder -- Singleroom : contains
    Hotel -- holder : uses
    Admin -- holder : manages
    write -- holder : writes

    class Food{
        +int itemno
        +int quantity
        +float price
        +Food(int, int)
    }

    class Singleroom{
        +String name
        +String contact
        +String gender
        +ArrayList food
        +Singleroom()
        +Singleroom(String, String, String)
    }

    class Doubleroom{
        +String name2
        +String contact2
        +String gender2
        +Doubleroom()
        +Doubleroom(String, String, String, String, String, String)
    }

    class holder{
        +Doubleroom[] luxury_doublerrom
        +Doubleroom[] deluxe_doublerrom
        +Singleroom[] luxury_singleerrom
        +Singleroom[] deluxe_singleerrom
    }

    class Hotel{
        +holder hotel_ob
        +Scanner sc
        +isValidName(String) boolean
        +isValidContact(String) boolean
        +isValidGender(String) boolean
        +getValidInput(String, String) String
        +CustDetails(int, int) void
        +bookroom(int) void
    }

    class Admin{
        +login(String, String) boolean
        +displayAdminPanel(holder) void
        +viewAllRoomsStatus(holder) void
        +viewBookedRoomsDetails(holder) void
        +displayRoomDetails(int, Singleroom) void
        +viewAvailableRooms(holder) void
        +searchCustomer(holder) void
    }

    class write{
        +holder hotel_ob
        +write(holder)
        +run() void
    }
