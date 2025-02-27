see [[Atomic ops]]
### **ACID Databases (Traditional SQL Databases)**

ACID stands for **Atomicity, Consistency, Isolation, and Durability**. These databases focus on keeping data **accurate, reliable, and consistent**.

1. **Atomicity:** All parts of a transaction succeed or fail together (like "all or nothing").  
    _Example:_ If you transfer money, both the debit and credit must happen, or neither does.
    
2. **Consistency:** Data always remains valid according to predefined rules (e.g., no invalid states).  
    _Example:_ If a bank balance can’t go negative, the database ensures this rule is followed.
    
3. **Isolation:** Multiple transactions don’t interfere with each other.  
    _Example:_ Two people updating the same account won’t corrupt the data.
    
4. **Durability:** Once a transaction is done, it’s saved forever, even if the system crashes.  
    _Example:_ After you make a payment, the record won’t disappear due to a server crash.
    

**Use Cases:** Banking systems, e-commerce platforms, healthcare systems—anything needing **strong consistency** and reliability.

### Key Difference:

- **ACID:** Guarantees correctness (always accurate, even if slower).
- **BASE:** Guarantees availability and scalability (faster, but might temporarily show slightly outdated or inconsistent data).

**Analogy:**

- ACID is like a **strict teacher** who ensures everything is perfect before letting it pass.
- BASE is like a **lenient coach** who prioritizes getting things moving and fixes any issues later. 