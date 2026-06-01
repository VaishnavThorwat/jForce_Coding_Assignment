## Problem Description

We are given a student marks table containing subject-wise marks. Students can attempt an exam for a specific subject as many times as they want. 

### Rules:
* The input DataFrame contains multiple entries per `Roll No` and `Subject`.
* The output must contain a unique combination of `Roll No` and `Subject`.
* We need to extract the three most recent marks for each combination:
  * **M1**: The latest mark (most recent attempt).
  * **M2**: The second latest mark.
  * **M3**: The third latest mark.
* If a student has fewer than 3 attempts for a subject, the missing attempt slots ($M2$ or $M3$) must be filled with `0`.

---

## Dataset Layout

### Input Dataframe Example

| Roll No | Subject | Marks | Date |
| :--- | :--- | :--- | :--- |
| 1 | DS | 25 | 01-01-23 |
| 1 | Java | 40 | 02-01-23 |
| 2 | DS | 30 | 01-01-23 |
| 2 | Java | 26 | 02-01-23 |
| 1 | DS | 40 | 15-01-23 |
| 2 | Java | 50 | 15-01-23 |

### Expected Output Dataframe

Based on the rules above, the resulting structured table should look like this:

| Roll No | Subject | M1 | M2 | M3 |
| :--- | :--- | :--- | :--- | :--- |
| 1 | DS | 40 | 25 | 0 |
| 1 | Java | 40 | 0 | 0 |
| 2 | DS | 30 | 0 | 0 |
| 2 | Java | 50 | 26 | 0 |

---
### Prerequisites

Make sure you have `pandas` installed:
```bash
pip install pandas
