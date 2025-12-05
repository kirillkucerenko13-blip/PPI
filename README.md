# DRIPCHIK — Архітектура

Архітектура проєкту складається з Frontend-частини (HTML/CSS/JS), базового бекенду (майбутня фаза) та файлового сховища для медіа.  
Мета архітектури — забезпечити просту, зрозумілу та розширювану структуру для MVP-версії онлайн-каталогу.

##  Короткий огляд архітектури
- **Frontend** — головна частина MVP: рендер сторінок Men/Women/New/Sale.  
- **Backend (майбутній)** — REST API для даних товарів.  
- **Storage** — зберігання фото та статичних даних.  
- **External Services** — опціонально (аналітика, платежі).  

graph TD
    User((Користувач)) -- HTTPS (Browser) --> Frontend[Store Frontend App]
    
    subgraph "Internal System"
        Frontend -- REST API / JSON --> Backend[Core Backend API]
        Backend -- SQL Query --> DB[(PostgreSQL DB)]
        Backend -- Put/Get Image --> Storage[(Image Storage / S3)]
    end
    
    subgraph "External Services"
        Backend -- Payment Request --> Stripe[Payment Gateway]
        Backend -- Get Branches --> NovaPoshta[Delivery API]
    end
