Content Link: http://hi-next/#/view/298

## Introduction to ESTE

ESTE stands for Enterprise Series Transaction Engine, the core system responsible for processing all lottery-related transactions. It determines whether to accept or reject transactions like wagers, cancellations, and validations, which originate from Point of Sale (POS) terminals.

Study Questions

- What programming languages and technologies are used to build ESTE?

- Is ESTE proprietary software, or is it built on open standards?

- How does ESTE handle transaction failures or retries?

## Components of the Lottery System

Key components include: POS Terminals (where transactions originate), Management Workstations (used to manage games, draws, and winning numbers), Central System (ESTE), and Communication Network (connects all components).

Study Questions

- What protocols are used in the communication network?

- What operating systems run on the POS terminals and management PCs?

- Is ESTE a physical server or a software module?

OLTP System Characteristics

ESTE is an Online Transaction Processing (OLTP) system. It processes transactions in real-time, ensuring they are complete, permanent, and authoritative. It handles up to 500 million transactions per day, with response times under 5 seconds.

Study Questions

- What database system underlies ESTE?

- How is concurrency handled in such a high-volume system?

- What mechanisms ensure data integrity and consistency?

## Draws and Winning Numbers

Draws are scheduled events that determine winners. Management PCs input winning numbers into ESTE, which then validates tickets against stored data.

Study Questions

- How is randomness ensured in draw number generation?

- What security measures prevent tampering with draw results?

- Is there an audit trail for draw inputs?

## Product Architecture

ESTE is modular, with three product types: Critical Products (e.g., GTMS), Gaming Products (e.g., Powerball), and Non-Gaming Products (e.g., Accounting, TMIR). Each product operates independently, except for dependencies on critical products.

Study Questions

- What is the lifecycle of a product within ESTE?

- How are new products integrated into the system?

- What happens if a non-critical product fails?

## Backup and Redundancy

ESTE uses hot backup, cold backup, and spare systems to ensure 24/7 uptime. Transactions are N-Plexed across systems to maintain data integrity.

Study Questions

- How is failover managed between primary and backup systems?

- What triggers a cold backup switch?

- How is synchronization ensured across systems?

## File Systems and Logging

Key files include: MJF (Master Journal File), PTM (Product Transaction Master), BJF (Backup Journal File). Files are stored on physically separate disks to prevent data loss.

Study Questions

- What file formats are used (e.g., binary, text)?

- How are these files indexed and queried?

- What is the retention policy for transaction logs?

## Transaction Flow

Transactions flow from POS → Communication Network → GTMS → Product → GTMS → POS. Management PCs interact via RPCs for commands and inquiries.

Study Questions

- What is the role of MXServe in the transaction flow?

- How are RPCs secured and authenticated?

- Is there a retry mechanism for failed transactions?

## Products and Tasks

Each product includes tasks like: GamePro (handles POS transactions), PM Serve (reporting), IO Serve (file I/O). Products are categorized as service, infrastructure, or gaming.

Study Questions

- How are tasks scheduled and managed?

- Are tasks multithreaded or single-threaded?

- What happens if a task crashes?

## System Messages and Error Logging

Messages are hexadecimal byte streams. Errors are logged with severity levels: Informational, Warning, Error, Fatal.

Study Questions

- How are hexadecimal messages parsed and validated?

- Is there a centralized logging system?

- How are fatal errors handled in real-time?

## Versions and Evolution

ESTE evolved from Fortran-based V1/V2 to C-based V6/V7, and now V8 on Linux. GEMS database was replaced by internal accounting products.

Study Questions

- What were the challenges in migrating from VMS to UNIX/Linux?

- How is backward compatibility maintained?

- What are the benefits of the Player Direct framework?

## Management GUI

Management GUI includes modules for game services, promotions, retailer services, reporting, system administration, and communications.

Study Questions

- What technologies are used to build the GUI?

- Is the GUI web-based or desktop-based?

- How is access control managed across modules?