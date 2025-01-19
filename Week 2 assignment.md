# Refactoring Payroll Function

## Original Code

```python
# Calculate employee payroll

def payroll(hours, rate):
    if hours <= 40:
        return hours * rate
    else:
        return (40 * rate) + ((hours - 40) * (rate * 1.5))

print("Payroll:", payroll(45, 20))
```

## Issues Identified

- **Unclear Function Name**: `payroll` does not clearly indicate that it calculates wages.
- **Missing Type Hints**: The function lacks type hints for clarity.
- **No Error Handling**: Negative hours or rates could lead to incorrect calculations.
- **Lack of Documentation**: No docstring explaining function behavior.
- **Magic Numbers**: `40` and `1.5` should be constants for better readability.

## AI-Suggested Refactored Code

```python
def calculate_payroll(hours: float, rate: float) -> float:
    """
    Calculate the total payroll amount based on hours worked and hourly rate.
    
    Overtime (above 40 hours) is paid at 1.5x the regular rate.
    
    :param hours: Number of hours worked (must be non-negative)
    :param rate: Hourly wage rate (must be non-negative)
    :return: Total payroll amount
    """
    REGULAR_HOURS = 40
    OVERTIME_MULTIPLIER = 1.5
    
    if hours < 0 or rate < 0:
        raise ValueError("Hours and rate must be non-negative.")
    
    if hours <= REGULAR_HOURS:
        return hours * rate
    else:
        overtime_hours = hours - REGULAR_HOURS
        return (REGULAR_HOURS * rate) + (overtime_hours * rate * OVERTIME_MULTIPLIER)

# Example usage
try:
    print("Payroll:", calculate_payroll(45, 20))
except ValueError as e:
    print("Error:", e)
```

## Reflection on AI Contributions

Using AI to refactor the payroll function significantly improved its clarity, robustness, and maintainability. The AI suggested renaming `payroll` to `calculate_payroll`, making the function's purpose clearer. Adding type hints made the function's expected inputs and outputs explicit, enhancing readability. The AI also recommended including a docstring, which provides essential documentation for users and future developers.

One of the most valuable improvements was adding error handling. The original function did not account for negative values, but the AI-suggested version raises a `ValueError` for invalid input. Additionally, replacing magic numbers with named constants (`REGULAR_HOURS` and `OVERTIME_MULTIPLIER`) improves readability and maintainability.

I agreed with most AI suggestions but modified the docstring slightly to ensure clarity. This exercise reinforced my understanding of refactoring best practices, such as improving function naming, using constants, and implementing error handling. AI proved useful in identifying and applying these enhancements, demonstrating its potential as a valuable coding assistant.
