# Columnar_Transposition_Cipher
The transposition cipher is a simple yet effective way of encrypting a text in a way that becomes unreadable to anyone who doesn’t possess the key to decryption. It relies on scrambling the words in plaintext by rearranging its characters.

## Step 1
A constructor function that accepts the cipher's key as an argument

## Step 2: Encrypt a Message
- **Split the Message into Characters**
  Break the message into individual characters and create a list where each element is one character.
  Optionally, convert all characters to lowercase or uppercase for consistency.
- **Calculate Message Length**
  Find the total number of characters in the message and store it in a variable (message_length).
- **Set Up an Empty Encrypted Message**
  Initialize an empty string to store the encrypted message as you process it.
- **Identify the Encryption Pattern**
  i   f e e l
    l i k e
  a   h a c k
  e r - - - -

  Visualize the message split into rows and columns using the key as the number of columns.
  Determine how many rows are needed using the formula:
  rows=⌈message_length/key⌉
  (The ceiling function ensures you round up to account for leftover characters.)
- Use Nested Loops to Encrypt
  Loop through each column (from 0 to key - 1).
  Inside this, loop through each row (from 0 to rows - 1).
  Calculate the index in the message using:
          index=(row×key)+column
  Add the character at this index to the encrypted message if it’s within bounds (i.e., less than message_length).

## Step 3:
- **Calculate the Number of Rows and Columns**
  Use the length of the encrypted message (encrypted_length) and the key to determine:
        rows=⌈encrypted_length/key⌉
  columns=key
  Identify the number of shaded cells (empty spaces in the grid) as:
  shaded_cells=(rows×key)−encrypted_length
- **Initialize the Decryption Grid**
  Create a 2D list (grid) with rows and columns.
  Fill the grid column by column with characters from the encrypted message, skipping shaded cells in the last row.
- **Extract the Original Message**
  Use a nested loop to iterate row by row through the grid.
  For each cell, add the character to the decrypted message string if it’s not a shaded cell.
- **Return the Decrypted Message**
  Combine the characters from the grid to reconstruct the original message and return it.

