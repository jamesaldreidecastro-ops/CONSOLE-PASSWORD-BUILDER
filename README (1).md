
# SECURI-VAULT

***PROGRAM STRUCTURED***

### SecuriVaultSystem (Main Class)
- **Purpose:** Console interface managing application flow.
 **Responsibilities:** 
  - Handles user input and menu operations (Create, View, Update, Delete, Exit)
  - Interacts with `VaultManager` and `ComplexGenerator` via polymorphism

### AbstractPasswordGenerator (Abstract Class)
- **Purpose:** Blueprint for password generators
 **Responsibilities:** 
  - Declares `generate()` method
  - Provides helper methods: `getCharacterPool()`, `getRandomChar()`

### ComplexGenerator (Concrete Class)
- **Purpose:** Generates passwords with custom rules
**Responsibilities:** 
  - Implements `generate()` 
  - Ensures randomness and shuffling for strong passwords

### VaultEntry (Encapsulation)
- **Purpose:** Represents a single account password entry
 **Responsibilities:** 
  - Stores account info privately
  - Provides getters/setters with validation
  - Includes utility methods: `parityCheck()`, `primalityCheck()`

### VaultManager (Encapsulation & Composition)
- **Purpose:** Manages vault entries
 **Responsibilities:** 
  - Performs CRUD operations
  - Provides utility methods: `isEmpty()`, `size()`, `containsAccount()`, `clearVault()`
  - Contains multiple `VaultEntry` objects











## List of Relationship
## Table 1: OOP Pillars


| OOP Pillar                  | Demonstration                                                                                                      |
|------------------------------|------------------------------------------------------------------------------------------------------------------|
| Inheritance                  | ComplexGenerator inherits from AbstractPasswordGenerator                                                         |
| Encapsulation                | VaultEntry hides account name and password fields with private access; VaultManager encapsulates the vault map and provides controlled CRUD operations |
| Composition                  | VaultManager contains VaultEntry objects (1-to-many relationship)                                                |
| Polymorphism / Abstraction   | SecuriVaultSystem uses AbstractPasswordGenerator type, allowing flexible implementation via ComplexGenerator    |

## Table 2: Class Relationships

| Class / Component        | Relationship           | Class / Component / Details                  |
|--------------------------|----------------------|---------------------------------------------|
| ComplexGenerator         | inherits from        | AbstractPasswordGenerator                   |
| VaultEntry               | encapsulates fields  | accountName, password                        |
| VaultManager             | manages / contains   | VaultEntry objects (1-to-many)             |
| SecuriVaultSystem        | uses / polymorphism  | AbstractPasswordGenerator (via ComplexGenerator) |

## A text-based Diagram
<img width="696" height="751" alt="Image" src="https://github.com/user-attachments/assets/88338f29-0604-4002-911d-0a228c1d2bf6" />
**Legend:*

- *`^`* :Inheritance 
- *`contains`* : Composition — VaultManager contains VaultEntry  
- *`uses`* :   SecuriVaultSystem uses VaultManager & Generator  
- *`(Encapsulation)`* : Classes hiding internal data  
- *`(Polymorphism)`* : Implied in SecuriVaultSystem’s use of `AbstractPasswordGenerator`
