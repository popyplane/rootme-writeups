# Root-Me Challenge Write-Up

## 1. Challenge Information


| **Challenge Name** | `` |
| :--- | :--- |
| **Category** | `[]` |
| **Difficulty** | `[]` |
| **Link** | `` |

---

## 2. Objective

> **1–2 Sentence Summary:** `[State the primary goal of the challenge, e.g., "The objective is to find the correct key that decrypts the flag from a provided file using a custom algorithm."]`

---

## 3. Provided Files

List all files provided by Root-Me. **Do NOT include the binary files themselves in your repository.**

* `[File 1 Name, e.g., file_to_analyse.bin]`
* `[File 2 Name, e.g., custom_script.py]`
* `[Add more as needed]`

---

## 4. Initial Reconnaissance (Recon)

Run basic command-line tools to understand the file's nature and security.

### ⚙️ Tools & Output

* **`file [filename]`**
    * **Result:** `[Insert output (e.g., ELF 64-bit LSB executable, x86-64)]`
* **`strings [filename]`**
    * **Suspicious Strings:** `[List any potentially interesting or plaintext strings found, e.g., "Wrong password", "Enter key", or parts of the flag]`
* **`checksec [filename]`**
    * **Mitigations:** `[List key mitigations, e.g., RELRO: Full, Stack: Canary found, PIE: No PIE]`

---

## 5. Static Analysis (Reverse Engineering)

This section focuses on understanding the challenge logic **without** running the program.

1.  **Open in Decompiler:** Open `[filename]` in Ghidra/IDA Pro.
2.  **Locate Main Logic:** Identify the key function responsible for input validation or transformation (often `main()` or a function called by it).
3.  **Validation/Transformation Logic:**
    * Describe the **core logic** you identified (e.g., an XOR loop, a custom substitution cipher, a comparison function).
    * What **data** is the input compared against or transformed? `[Identify key variables or hardcoded values]`
    * *Self-Note:* `[Optional: Include a brief summary of the pseudo-code logic.]`

> 

---

## 6. Dynamic Analysis (Optional)

Only include this if you needed to run the program and observe its behavior (e.g., debugging a segmentation fault, tracing library calls).

1.  **Tool Used:** `[e.g., gdb, ltrace, strace]`
2.  **Observation:** `[Describe what you were looking for and what you found (e.g., "Used 'ltrace' to see the program calling 'strcmp' and the hardcoded correct string in memory.")]`
3.  **Input Used:** `[e.g., Input: "AAAA", Observed crash address: 0x... ]`

---

## 7. Solution Analysis (The Core)

Provide a step-by-step breakdown of how you used your analysis to derive the final answer.

### Step-by-Step Reasoning

1.  **Initial Insight:** Based on static analysis, the challenge compares our input against the hardcoded array `[Hardcoded Array Name/Value]`.
2.  **Derivation Method:** `[Explain the steps taken. For example: "The program performs a byte-by-byte XOR operation with a known key ('K3Y') and the hardcoded cipher text. The inverse operation is $plaintext = ciphertext \oplus key$."]`
3.  **Script/Tool:** `[If you wrote a solver script, briefly describe it or include the key logic/functionality.]`
4.  **Final Calculation/Result:** `[Show the process that leads directly to the flag/password.]`

---

## 8. Final Answer

| Field | Value to Fill |
| :--- | :--- |
| **Flag/Answer** | `[Insert the final required answer/flag here]` |

---

## 9. Notes / Lessons Learned

* **Learned:** `[e.g., Always check the difference between $strlen()$ and $sizeof()$ when looking for buffer overflows.]`
* **Technique to Remember:** `[e.g., How to use the 'Find Cryptographic Constants' feature in Ghidra.]`

---

## 10. Screenshots

* ``
* ``