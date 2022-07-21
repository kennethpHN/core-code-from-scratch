## Wednesday 20/07/22

**Your date of birth in the matrix?**

i was born in 2002

To convert your year of birth to binary do the following:

| $2^{10}$ | $2^9$ | $2^8$ | $2^7$ | $2^6$ | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
|----------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| 1024     | 512   | 256   | 128   | 64    | 32    | 16    | 8     | 4     | 2     | 1     |

if 2002 >= 1024 then mark a 1

now do 2002 - 1024 = 978

if 978  >= 512 then mark a 1

now do 978 - 512 = 466

if 466 >= 256 then mark a 1

now do 466 - 256 = 210

if 210 >= 128 then mark a 1

now do 210 - 128 = 82

if 82 >= 64 then mark a 1

now do 82 - 64 = 18

if 18 >= 32 then mark a 1, else mark a 0

if 18 >= 16 then mark a 1

now do 18 - 16 = 2

if 2 >= 8 then mark a 1, else mark a 0

if 2 >= 4 then mark a 1, else mark a 0

if 2 >= 2 then mark a 1

now dow 2 - 2 = 0

after reaching 0 check the results of the table:

| $2^{10}$ | $2^9$ | $2^8$ | $2^7$ | $2^6$ | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
|----------|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| 1024     | 512   | 256   | 128   | 64    | 32    | 16    | 8     | 4     | 2     | 1     |
| 1        | 1     | 1     | 1     | 1     | 0     | 1     | 0     | 0     | 1     | 0     |

your age in binary is **11111010010**!
