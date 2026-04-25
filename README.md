# Djd



def ThreeNumbers(strParam):
    # Split the string into individual words
    words = strParam.split()
    
    for word in words:
        # Extract all digits in the current word
        digits = [char for char in word if char.isdigit()]
        
        # Rule 1 & 2: Must have exactly 3 digits AND they must be unique
        if len(digits) != 3 or len(set(digits)) != 3:
            return "false"
            
        # Rule 3: Digits cannot be all adjacent to each other
        # Find the index positions of all digits in the word
        digit_indices = [i for i, char in enumerate(word) if char.isdigit()]
        
        # If the difference between indices is 1, they are side-by-side
        if digit_indices[2] - digit_indices[1] == 1 and digit_indices[1] - digit_indices[0] == 1:
            return "false"
            
    return "true"

# Keep this function call here
print(ThreeNumbers(input()))
