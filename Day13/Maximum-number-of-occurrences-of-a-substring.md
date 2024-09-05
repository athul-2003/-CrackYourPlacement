- Question : https://leetcode.com/problems/maximum-number-of-occurrences-of-a-substring/submissions/1379357905/

  ```python
  def maxFreq(s: str, maxLetters: int, minSize: int, maxSize: int) -> int:
    substring_count = {}  # Dictionary to count occurrences of substrings
    max_occurrences = 0   # To store the highest count

    # Slide a window of size minSize over the string
    for i in range(len(s) - minSize + 1):
        # Extract the substring of length minSize
        substring = s[i:i + minSize]

        # Count unique characters in the substring
        unique_chars = len(set(substring))

        # If it has <= maxLetters unique characters, count it
        if unique_chars <= maxLetters:
            # If the substring is already counted, increment its count
            if substring in substring_count:
                substring_count[substring] += 1
            else:
                # If it's the first time seeing this substring, start counting from 1
                substring_count[substring] = 1
            
            # Update max_occurrences with the maximum count seen so far
            max_occurrences = max(max_occurrences, substring_count[substring])

    return max_occurrences ```
