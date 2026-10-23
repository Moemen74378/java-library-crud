# Library Desk

A small Java CRUD application for the Git and GitHub pair assignment. Add books, read the catalogue, edit book details and availability, and delete records. Data is stored in a local H2 database and survives a restart.

## Run

Install a JDK (Java 17 or later). Git and an internet connection are needed for the first build. Maven is downloaded automatically by the included official Maven Wrapper.

Windows PowerShell, inside this folder:

```powershell
.\mvnw.cmd spring-boot:run
```

macOS / Linux:

```sh
chmod +x mvnw
./mvnw spring-boot:run
```

Open **http://localhost:8080/books**. Stop the application with **Ctrl+C** in its terminal. If Java is not on PATH, set `JAVA_HOME` to your JDK folder (the folder containing `bin/java`) and add its `bin` directory to PATH, or run the application from IntelliJ IDEA using its configured JDK. In PowerShell, the PATH command is `$env:PATH = "$env:JAVA_HOME\bin;$env:PATH"`.

The application binds to this computer only. It is a classroom application for local use.

## Build and test

```powershell
.\mvnw.cmd clean verify
java -jar target/library-desk-1.0.0.jar
```

On macOS/Linux replace `.\mvnw.cmd` with `./mvnw`. Run from the project folder so the database stays in the same `data/` directory. Each student uses their own database. Never commit `data/` or `target/`.

## Try the CRUD operations

1. **Create:** click **Add book**, enter a title, author, publication year, and status, and save.
2. **Read:** the catalogue shows the saved book and updated summary counts.
3. **Update:** click **Edit**, change the status to Borrowed or update a detail, and save.
4. **Delete:** click **Delete** and confirm. The row disappears and the counts change.

Try an empty title or a year outside 1–2100 to see validation. Missing record URLs return HTTP 404.

<img width="1280" height="718" alt="photo_2026-10-23_15-17-46" src="https://github.com/user-attachments/assets/f53d7728-0fa2-4135-8976-9d192f6b556c" />
<img width="1791" height="1078" alt="Screenshot 2026-10-19 204658" src="https://github.com/user-attachments/assets/024ae66d-8c76-4600-9962-31f763ac2eba" />
