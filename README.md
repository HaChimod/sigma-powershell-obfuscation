# PowerShell Obfuscation Detection (Sigma Rules)

A collection of Sigma rules designed to detect various advanced PowerShell obfuscation techniques. These rules monitor for suspicious script block execution and command-line anomalies often utilized by threat actors for defense evasion (MITRE ATT&CK T1027).

## 🛡️ Detections Included

This repository includes rules for detecting:

- **Variable Renaming**: Unusually long hexadecimal or repeated-character variable names.
- **Boolean Obfuscation**: Unusual Boolean type casting, alternative Boolean representations, and repeated negation.
- **Command and String Breaking**: Use of quote or caret characters to split strings and commands.
- **Execution via Get-Command Wildcards**: Execution using `Get-Command` or `gcm` combined with wildcards.
- **Junk Code & Parameter Insertion**: Excessive parameter insertion, repeated filler commands like `Out-Null`, or micro-sleeps.
- **String Manipulation**: String reversal, byte-to-char casting, and excessive concatenation.
- **Randomized Character Case**: Frequent uppercase and lowercase transitions within words.

## 📋 Prerequisites

To effectively use these rules in your SIEM/Log Management system, ensure the following Windows event logs are enabled:

- **Event ID 4104**: PowerShell Script Block Logging (Required for most script-level detections).

## ⚙️ Usage

Integrate these YAML rule files into your preferred SIEM platform (e.g., Splunk, Elastic, Microsoft Sentinel) using a Sigma compiler (like `sigma-cli`) to translate them into your target query language.
