#---random password generator---
import random
import string

def generate_strong_password(length=8):

    all_characters = string.ascii_letters 
    all_characters += string.digits        
    all_characters += string.punctuation   
    uppercase = string.ascii_uppercase
    lowercase = string.ascii_lowercase
    digits = string.digits
    symbols = string.punctuation

    if length < 4:
        print("Error: Password length must be at least 4 to meet strong criteria.")
        return None

    password_list = [
        random.choice(uppercase),
        random.choice(lowercase),
        random.choice(digits),
        random.choice(symbols)
    ]
    remaining_length = length - len(password_list) 
    password_list += random.choices(all_characters, k=remaining_length)
    random.shuffle(password_list)
    return "".join(password_list)

# --- Main Execution Block ---
if __name__ == "__main__":
    length = 8
    new_password = generate_strong_password(length)
    if new_password:
        print(f"Generating a password of length: **{length}**")
        print(f"\nGenerated Password: **{new_password}**")
        
