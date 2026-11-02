# 🥔 potatoSalad CTF kit

A single-file, menu-driven CTF toolkit covering Cryptography, Web, Pwn, Forensics, Reverse Engineering, OSINT/Misc, and HTB/THM-style machine workflows — **67 tools, zero third-party dependencies.**

```
  ════════════════════════════════════════════════════════════════════
  ████   ███  █████  ███  █████  ███   ████  ███  █      ███  ████
  █   █ █   █   █   █   █   █   █   █ █     █   █ █     █   █ █   █
  ████  █   █   █   █████   █   █   █  ███  █████ █     █████ █   █
  █     █   █   █   █   █   █   █   █     █ █   █ █     █   █ █   █
  █      ███    █   █   █   █    ███  ████  █   █ █████ █   █ ████
                       C T F   K I T
        Crypto · Web · Pwn · Forensics · RE · OSINT · Machines
  ════════════════════════════════════════════════════════════════════
```

## Why

Most CTF players end up with a scattered pile of one-off scripts, CyberChef tabs, and half-remembered `openssl`/`python -c` one-liners. potatoSalad CTF kit puts the stuff you reach for constantly, encodings, classic ciphers, cheatsheets, exploit templates, recon references — behind one numbered menu, in one dependency-free file you can drop onto any box (including a CTF VM with no internet access).

## Features

Colorized output throughout. Every "encode/decode" tool offers to save its result to a file. Pure Python standard library — nothing to `pip install` for the core tool.

### Cryptography
| # | Tool | # | Tool |
|---|------|---|------|
| 1 | Base64 | 11 | RSA Helper |
| 2 | Base32 | 30 | ROT47 |
| 3 | Base58 | 31 | Atbash |
| 4 | Hex | 32 | Rail Fence Cipher |
| 5 | Binary | 33 | Bacon Cipher |
| 6 | ROT13 | 34 | Base85 / Ascii85 |
| 7 | Caesar Brute Force | 35 | Affine Cipher |
| 8 | Vigenère | 36 | Columnar Transposition |
| 9 | XOR | 37 | Hash Cracker (wordlist) |
| 10 | Frequency Analysis | 38 | Polybius Square |

### Web
| # | Tool | # | Tool |
|---|------|---|------|
| 12 | URL Encode/Decode | 39 | LFI / Path Traversal |
| 13 | HTML Entity | 40 | SSTI Cheatsheet |
| 14 | JWT Decoder | 41 | Command Injection |
| 15 | SQLi Cheatsheet | 42 | XXE Cheatsheet |
| 16 | XSS Cheatsheet | | |

### Pwn
| # | Tool | # | Tool |
|---|------|---|------|
| 17 | Cyclic Pattern | 43 | Ret2Libc / ROP |
| 18 | Format String | 44 | Heap Exploitation |
| 19 | Shellcode / Pwntools | | |

### Forensics
| # | Tool | # | Tool |
|---|------|---|------|
| 20 | File Magic Bytes | 45 | PNG Chunk Inspector |
| 21 | Strings Extractor | 46 | PCAP / Network Forensics |
| 22 | Stego Checklist | 47 | Volatility Memory Forensics |
| | | 48 | Archive / ZIP Analysis |

### Reverse Engineering
| # | Tool | # | Tool |
|---|------|---|------|
| 23 | RE Tools & GDB | 49 | Android / APK RE |
| | | 50 | .NET / Java / Python RE |

### Misc / OSINT
| # | Tool | # | Tool |
|---|------|---|------|
| 24 | Morse Code | 51 | Tap Code |
| 25 | Hash Generator | 52 | NATO Phonetic Alphabet |
| 26 | Flag Scanner | 53 | Braille Encoder/Decoder |
| 27 | Hash Identifier | 54 | Whitespace Steganography |
| 28 | Base Converter | | |
| 29 | OSINT Reference | | |

### Machines (HTB / THM)
| # | Tool |
|---|------|
| 55 | Nmap Command Builder |
| 56 | Reverse Shell Generator |
| 57 | Web Enumeration Reference |
| 58 | Privilege Escalation Reference |
| 59 | SMB Enumeration Reference |
| 60 | Password Attacks Reference |
| 61 | Programming Challenges |
| 62 | CTF Methodology Checklist |

### Tool Extensions
| # | Tool |
|---|------|
| 63 | RSA Factorization (find p, q from n) |
| 64 | Vigenère Key Recovery (no key needed) |
| 65 | JWT HMAC Secret Brute Force |
| 66 | **Magic Auto-Decoder** — chains Base64/32/58/85, hex, binary, URL, HTML-entity, ROT13, and Atbash up to 3 layers deep, ranks candidates by printable-ASCII density, flags likely `flag{...}` hits |
| 67 | Hash Length Extension Attack reference (`hashpump` / `hlextend`) |

## Requirements

- Python **3.8+**
- Core toolkit: **zero third-party dependencies**
- A few individual tools print reference snippets that assume you separately have `pwntools`, `PIL`/Pillow, `sympy`, or `nmap` installed on the system — the toolkit itself never imports them unless you're in that specific tool

## Install & Run

```bash
git clone https://github.com/<your-username>/potatosalad-ctf-kit.git
cd potatosalad-ctf-kit
python3 potatosalad_ctf_kit.py
```

No build step, no virtualenv required for core use. Pick a number from the menu, follow the prompts.

## Example

```
$ python3 potatosalad_ctf_kit.py

  Select option: 66
  Enter mystery text: c3ludHthcmZncnFfc2hhfQ==

  Candidates (best first):
  [Base64 → ROT13]  (100% printable)  ★ possible flag
    flag{nested_fun}
```

## Project structure

```
potatosalad-ctf-kit/
├── potatosalad_ctf_kit.py   # the whole toolkit — single file, no package install needed
├── README.md
└── LICENSE
```

## Disclaimer

This toolkit includes offensive-security references (reverse shell one-liners, privilege-escalation checklists, password-attack commands, etc.) for use during CTF competitions and authorized penetration testing. **Only use these against systems and challenges you own or are explicitly authorized to test.**

## Contributing

Issues and PRs welcome — new ciphers, new cheatsheets, bug reports. Keep additions dependency-free where possible so the toolkit stays drop-in portable.

## License

Add the license you want this released under (MIT is a common choice for tools like this) and include a `LICENSE` file — not included here since you didn't specify one.

---

Built by **potatoSalad420 & (Claude pro max i paid for)**.
