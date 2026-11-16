# Beginner Project 06 - Backup and Recovery

## Subject

Protect the containerized application, simulate data loss and restore a working service.

## Learning Goals

- Understand backups, restores, retention and recovery testing.
- Distinguish application files from database data.
- Automate safe backups and verify their integrity.
- Explain Recovery Point Objective and Recovery Time Objective.

## Mandatory Work

- Reuse the Docker Compose application from Project 05.
- Create a database backup using the database's supported dump tool.
- Back up required application data and configuration without copying live database files directly.
- Add timestamps and checksums to backup artifacts.
- Compress backups and save them outside the application volumes.
- Schedule automatic backups.
- Keep a documented number of recent backups and remove older ones safely.
- Simulate accidental deletion or corruption.
- Restore the database and application data from a known backup.
- Measure and report the achieved recovery time and possible data loss window.

## Deliverables

- Backup, restore and retention scripts.
- A backup manifest or checksum file.
- A recovery runbook with exact commands.
- Evidence of one successful destructive recovery test.

## Validation

- A backup can be created twice without overwriting the wrong file.
- Corrupted backup files are detected by checksum verification.
- The evaluator deletes the selected data.
- The student restores it and proves the application works.

## Estimated Time

One week.

<p align="center">
  <img src="../images/next-level.png" alt="Hit the next level" width="600">
</p>
