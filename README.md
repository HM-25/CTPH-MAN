# CTPH-MAN

Notes and reading material on **fuzzy hashing**, also called Context Triggered Piecewise Hashing (CTPH).

## What is CTPH?

Regular hashes (MD5, SHA-256) change completely when a single byte changes. **CTPH** produces hashes that can be compared for *similarity*, so files that share sequences of identical bytes in the same order still match, even if the content between them differs in content and length.

This makes fuzzy hashing useful for:

- Finding near-duplicate files during forensic investigations
- Grouping malware variants that come from the same family
- Detecting modified documents and partial file matches

## ssdeep

[ssdeep](https://ssdeep-project.github.io/ssdeep/) is the reference tool for computing CTPH. It also provides a library, `libfuzzy`, to generate and compare fuzzy hashes.

```bash
# Hash files
ssdeep file1.bin file2.bin

# Compare files against each other and show matches
ssdeep -pb *
```

## Further reading

The method is described in *"Identifying almost identical files using context triggered piecewise hashing"* (Jesse Kornblum, Digital Investigation, 2006, DFRWS proceedings). This repo also collects other papers from the same DFRWS 2006 issue on digital forensics.

All papers remain the property of their authors and publisher.

## About

Personal study notes on digital forensics. See also: [Hashing](https://github.com/HM-25/Hashing).
