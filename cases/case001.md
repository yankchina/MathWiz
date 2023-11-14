## Math Case 001

### Problem

A pile of Go pieces has two colors: black and white. After taking away 15 white pieces, the ratio of the number of black pieces to white pieces is 2:1. After taking away 45 more black pieces, the ratio of the number of black pieces to white pieces is 1: 5. How many black chess pieces and white chess pieces are there?

To solve this problem, we'll first identify the key knowledge points, then outline the solution strategy, and finally provide the reference Python and Swift code.

### Knowledge Points of the Topic

1. **Ratio and Proportion**: Understanding the relationship between different groups in terms of ratios.
2. **System of Equations**: Formulating and solving a system of linear equations to find the quantities of each type of piece.

### Ideas for Solving the Problem
1. Let the initial number of black pieces be \( B \) and the initial number of white pieces be \( W \).
2. After removing 15 white pieces, the number of white pieces becomes \( W - 15 \). The ratio of black to white pieces is now 2:1, so \( B : (W - 15) = 2 : 1 \).
3. After removing 45 more black pieces, the number of black pieces becomes \( B - 45 \). The new ratio of black to white pieces is 1:5, so \( (B - 45) : (W - 15) = 1 : 5 \).
4. Solve these equations simultaneously to find the values of \( B \) and \( W \).

### Reference Python Program Code
```python
from sympy import symbols, Eq, solve

# Define the symbols for the number of black and white pieces
B, W = symbols('B W')

# Equation 1: After taking away 15 white pieces, the ratio B:W is 2:1
eq1 = Eq(B / (W - 15), 2/1)

# Equation 2: After taking away 45 more black pieces, the ratio B:W is 1:5
eq2 = Eq((B - 45) / (W - 15), 1/5)

# Solve the equations
solution = solve((eq1,eq2), (B, W))

print(f"Number of black pieces: {solution[B]}")
print(f"Number of white pieces: {solution[W]}")
```

### Reference Swift Program Code (Playground mode)
```swift
import Foundation

// Function to solve the system of equations
func solveSystem() -> (Int, Int) {
    for B in 1...1000 { // Assuming a reasonable upper limit for number of pieces
        for W in 1...1000 {
            if B * (W - 15) == 2 * (W - 15) * 2 && (B - 45) * 5 == W - 15 {
                return (B, W)
            }
        }
    }
    return (0, 0) // No solution found
}

// Solve the equations
let (blackPieces, whitePieces) = solveSystem()

print("Number of black pieces: \(blackPieces)")
print("Number of white pieces: \(whitePieces)")
```

These codes will calculate the number of black and white Go pieces based on the given conditions and ratios. Note that the Swift code uses a brute-force approach due to the limitations of Swift Playgrounds in solving algebraic equations.