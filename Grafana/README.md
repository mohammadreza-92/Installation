# Grafana: Build and Run from Source

If you've downloaded Grafana from its [GitHub repository](https://github.com/grafana/grafana), you’ll need to build and run it from the source code. Here’s how you can do that:

---

## **Step 1: Prerequisites**
Ensure you have the following installed on your system:

1. **Go**: Grafana is written in Go, so you need Go installed.
   - Install Go: [Official Go Installation Guide](https://go.dev/doc/install).
   - Verify installation:
     ```
     go version
     ```

2. **Node.js and Yarn**: Grafana’s frontend is built using Node.js and Yarn.
   - Install Node.js: [Node.js Download](https://nodejs.org/).
   - Install Yarn:
     ```
     npm install -g yarn
     ```
     Mac:
     ```
     brew install yarn
     ```

3. **Make**: Grafana uses Make for building.
   - On macOS, install Make via Xcode Command Line Tools:
     ```
     xcode-select --install
     ```

---

## **Step 2: Clone the Grafana Repository**
1. Clone the Grafana repository:
   ```
   git clone https://github.com/grafana/grafana.git
   cd grafana
   ```

2. Check out the latest stable version (optional but recommended):
   ```
   git checkout v10.2.0 # Replace with the latest stable version
   ```

---

## **Step 3: Build Grafana**
1. Install backend dependencies:
   ```
   make deps-go
   ```

2. Install frontend dependencies:
   ```
   make deps-js
   ```

3. Build the frontend:
   ```
   make build-js
   ```

4. Build the backend:
   ```
   make build-go
   ```

5. Build the entire project:
   ```
   make build
   ```

---

## **Step 4: Run Grafana**
1. Start Grafana:
   ```
   ./bin/grafana-server
   ```

2. Grafana will start running on `http://localhost:3000`.
   - Default username: `admin`
   - Default password: `admin`

---

## **Step 5: Verify Grafana**
1. Open your browser and go to:
   ```
   http://localhost:3000
   ```

2. Log in with the default credentials (`admin/admin`).

3. Follow the setup wizard to configure Grafana.

---

## **Summary**
- Clone the Grafana repository.
- Install dependencies (Go, Node.js, Yarn, Make).
- Build Grafana using `make build`.
- Run Grafana using `./bin/grafana-server`.
- Access Grafana at `http://localhost:3000`.

