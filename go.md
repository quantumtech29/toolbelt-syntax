🛡️ Go Cheat Sheet for DevSecOps & Security Researchers
📌 Purpose
Built for secure systems programming, concurrent tooling, and reproducible artifact generation in CI/CD, threat modeling, and supply chain security.

🔧 Go Script Anatomy
Component
Example
Notes
Package
package main
Entry point for executables
Imports
import "fmt"
Standard library or external
Entry Point
func main() {}
Required for execution
Comments
// single, /* multi-line */
Use for annotation & teachback


📦 Variables & Types
var x int        // Explicit declaration
y := 42          // Short declaration with type inference
const Pi = 3.14  // Constant

Built-in types: int, float64, string, bool, rune, byte, complex128
Composite types: array, slice, map, struct, interface

🔐 Security Hygiene
import "os"
file, err := os.Open("config.yaml")
if err != nil {
    log.Fatal(err) // Fail fast
}
defer file.Close() // Ensure cleanup

Use case: Secure file handling, audit trail, and deferred teardown.

🔄 Control Structures
if x > 10 {
    fmt.Println("High")
} else {
    fmt.Println("Low")
}

for i := 0; i < 3; i++ {
    fmt.Println(i)
}

switch status {
case 200: fmt.Println("OK")
case 403: fmt.Println("Forbidden")
default: fmt.Println("Unknown")
}


🧪 Functions & Return Values
func add(x, y int) int {
    return x + y
}

func split(sum int) (x, y int) {
    x = sum * 4 / 9
    y = sum - x
    return
}

Named returns simplify multi-value output and forensic traceability.

📤 Logging & Error Handling
import "log"
log.Println("Scan started")
if err != nil {
    log.Fatalf("Error: %v", err)
}

Use case: Artifact logging, error traceability, and audit compliance.

🧰 Built-ins & Memory Safety
new(int)         // Allocates memory
make([]int, 10)  // Initializes slice
&x               // Pointer to x

Go is garbage collected but still allows pointer-based control.

🔄 Concurrency & Channels
c := make(chan int)
go func() { c <- 42 }()
fmt.Println(<-c)

Use case: Parallel scans, async artifact generation, and secure goroutines.

🌐 Web & API Ops
import "net/http"

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprint(w, "Secure endpoint reached")
}

http.ListenAndServe(":8080", http.HandlerFunc(handler))

Use case: Lightweight API for threat modeling, telemetry, or outreach.

🧠 Annotated Rituals
Daily Ops: go fmt, go vet, go test ./...
Outreach Artifact: fmt.Printf("Scan complete: %s\n", time.Now())
Teachback Loop: go doc fmt.Println

✅ Formatting Tips
Use code blocks for clarity.
Use tables for quick comparisons.
Use emoji headers to segment rituals and modules.
Annotate with intent and use case to make it reproducible.
