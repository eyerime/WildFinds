# WildFinds: CIT-U Lost & Found System

This is an Information Management (IM) project developed for the BSCS program at Cebu Institute of Technology – University (CIT-U)[cite: 2]. 

WildFinds is a vanilla PHP/MySQL web application built to systematically manage lost and found items on campus[cite: 2]. As an IM project, the primary focus is on robust database design, data integrity, relational mapping, and secure data handling using MVP (Model-View-Presenter) principles and vertical slicing architecture[cite: 2].

## How It Works (Digital + Physical Workflow)

WildFinds is a public-facing website, but the actual storing, logging, and collecting of items relies on a hybrid digital and physical process. Here is how the system is utilized in a real-world campus scenario:

1. **Surrendering an Item:** Regular users cannot post items directly to the public board. If a student finds a lost item on campus, they must physically surrender it to a faculty member or authorized staff.
2. **Logging the Item:** The faculty member logs into the Admin Dashboard and registers the item into the database[cite: 2], safely storing the physical item in their office. 
3. **Public Viewing:** Students who have lost something can browse the public dashboard to view a categorized list of found items[cite: 2].
4. **Submitting a Claim:** If a student spots their item on the site, they submit a claim digitally[cite: 2]. For unidentifiable items, they are required to provide specific proof of ownership in their claim submission to prevent theft[cite: 2].
5. **Physical Collection:** The student visits the faculty office to physically collect the item. The staff verifies their identity and proof, hands over the item, and logs the physical handoff in the system to maintain an accurate history[cite: 2].

## Information Management Focus

This project demonstrates several core Information Management concepts:

* **Entity Subtyping / Inheritance:** The database implements a supertype/subtype relationship for items[cite: 2]. The main Item table holds common attributes, while Identifiable_Item and Unidentifiable_Item tables store specific traits, ensuring strict data normalization[cite: 2].
* **Relational Integrity:** Extensive use of foreign keys with ON DELETE CASCADE ensures that related records (like claims and handoff histories) maintain referential integrity when parent records are modified[cite: 2].
* **Data Security & Privacy:** Faculty passwords are securely hashed (password_hash)[cite: 2]. Sensitive item details ("hidden descriptions" for unidentifiable items) are strictly shielded from the public view, only accessible to authorized personnel to verify claims[cite: 2].
* **Transaction Management:** Database transactions (beginTransaction, commit, rollBack) are utilized during complex inserts (like logging an item and its subtype simultaneously or processing a claim/handoff) to prevent partial data commits and maintain atomicity[cite: 2].

## Tech Stack
* Backend: PHP (Vanilla)[cite: 2]
* Database: MySQL (PDO for secure, parameterized queries)[cite: 2]
* Architecture: MVP, Vertical Slicing[cite: 2]
* Frontend: HTML5, CSS3, Vanilla JavaScript[cite: 2]

## Installation & Setup

1. Move Files: Extract or copy the repository folder into your XAMPP web directory (C:\xampp\htdocs\)[cite: 2].
2. Start Local Server: Open the XAMPP Control Panel and start Apache and MySQL[cite: 2].
3. Database Setup:
   - Navigate to http://localhost/phpmyadmin in your browser[cite: 2].
   - Create a new database named exactly `lostfound_db`[cite: 2].
   - Import the `schema.sql` file (located in the project root) to build the tables[cite: 2].
   - Import the `seed.sql` file to populate the system with initial sample data and accounts[cite: 2].
4. Run the Application: Visit http://localhost/lostfound in your web browser[cite: 2].

## Access Credentials

Admin / Faculty Login:
* Employee ID: EMP001 (or EMP002)[cite: 2]
* Password: password123[cite: 2]

Troubleshooting Login: If you experience login issues due to PHP version hash mismatches, navigate to http://localhost/lostfound/fix.php in your browser[cite: 2]. This script will automatically resync the password123 hash to match your local environment's PHP configuration[cite: 2].
