## Signed integers
### Sign and magnitude method
**Most significant bit - sign bit: 0 - positive, 1 - negative**

**Flaws**
- Two zeros (00000000 == 10000000)
- Need to complicate the structure of the computer

### Ones' complement
**if n > 0: n = 0${bin(n)}** \
**else: n = 1${inv(bin(n))}**

**Flaws**
- Two zeros (00000000 == 11111111)

### Two’s complement
**if n > 0: n = 0${bin(n)}** \
**else: n = 1${inv(bin(n)) + 1}**
