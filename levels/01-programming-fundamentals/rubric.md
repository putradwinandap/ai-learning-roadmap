# Level 01 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

Track add-on criteria are in `tracks/<language>/rubric-addon.md` and count toward the average.

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L01-R1 | **Correctness** | All Must features work as specified. All acceptance scenarios 1–7 pass. Totals are correct to the cent. | Should items S1–S2 also work. Behaviour is consistent and predictable everywhere. | Wrong totals, broken delete, duplicate or reused IDs, features missing. |
| L01-R2 | **Input handling & errors** | Every invalid input is rejected with a helpful message, and the program never crashes. Exceptions are caught specifically and narrowly. | Re-prompts instead of restarting the flow. A corrupt data file is handled (S3). Messages tell the user how to fix the problem. | Crashes on `abc`, broad catch-all handlers hiding bugs, unhelpful messages. |
| L01-R3 | **Persistence** | Saves after every change, loads on start, and the first run works. The data format is documented. | File path is independent of the working directory, or this is clearly documented. Safe against data loss (no silent overwrite on read errors). | Data lost on restart, crash when the file is missing, file written in an odd place. |
| L01-R4 | **Program structure** | Clear separation of interface, logic and storage. Small single-purpose functions. Logic functions are pure. There's a `main` entry point. No mutable globals changed from functions. | `main` reads like a summary. Menu dispatch uses a table or match. Split into modules where it helps. | One giant function, printing inside calculations, global state everywhere, copy-pasted blocks. |
| L01-R5 | **Readability** | Descriptive names following the language's convention, constants instead of magic values, consistent formatting, no dead code. | Code reads almost like prose. The few comments explain *why*. | Unclear names, magic strings and numbers, commented-out code, inconsistent style. |
| L01-R6 | **Documentation & Git** | README covers everything in L01-M8, and the run instructions work as written. Incremental commits with clear messages. | README includes example usage output. Commit history tells the story of the build (S4). | Missing or wrong run instructions, one big commit, unclear messages. |
