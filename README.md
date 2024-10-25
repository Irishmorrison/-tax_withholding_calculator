# -tax_withholding_calculator
def get_ferrari_value(year):
    # Define the value ranges for the Ferrari 250 GTO
    value_mapping = {
        (1962, 1964): 18500,
        (1965, 1968): 6000,
        (1969, 1971): 12000,
        (1972, 1975): 48000,
        (1976, 1980): 200000,
        (1981, 1985): 650000,
        (1986, 2012): 35000000,
        (2013, 2014): 52000000
    }
    
    # Check the year against the defined ranges
    for year_range, value in value_mapping.items():
        if year_range[0] <= year <= year_range[1]:
            return f"The approximate value of a Ferrari 250 GTO in {year} is ${value:,}."
    
    return "Year out of range. Please enter a year between 1962 and 2014."

# Input from the user
try:
    year_input = int(input("Enter a year (1962-2014): "))
    result = get_ferrari_value(year_input)
    print(result)
except ValueError:
    print("Invalid input. Please enter a valid year.")
