# PRODIGY_CS_01
def caesar_cipher(text, shift, mode="encrypt"):
    # Adjust shift for decryption
    if mode == "decrypt":
        shift = -shift

    result = ""
    for char in text:
        # Encrypt uppercase letters
        if char.isupper():
            result += chr((ord(char) + shift - 65) % 26 + 65)
        # Encrypt lowercase letters
        elif char.islower():
            result += chr((ord(char) + shift - 97) % 26 + 97)
        else:
            # Keep non-alphabetic characters as is
            result += char
    return result

# Main program
if __name__ == "__main__":
    print("Caesar Cipher Program")
    
    # Example input
    text = "Hello, World!"
    shift = 3
    mode = "encrypt"

    # Displaying example input
    print(f"Example Input:\nMessage: '{text}'\nShift Value: {shift}\nMode: '{mode}'")

    # Perform encryption
    output = caesar_cipher(text, shift, mode)
    print(f"Encrypted Result: {output}")

    # Now demonstrating decryption
    text = output  # Use the encrypted text for decryption
    mode = "decrypt"

    # Displaying decryption example input
    print(f"\nDecryption Example Input:\nEncrypted Message: '{text}'\nShift Value: {shift}\nMode: '{mode}'")

    # Perform decryption
    decrypted_output = caesar_cipher(text, shift, mode)
    print(f"Decrypted Result: {decrypted_output}")

