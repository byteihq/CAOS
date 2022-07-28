## Signed integers
### Sign and magnitude method
**Most significant bit - sign bit: 0 - positive, 1 - negative**

![image](https://user-images.githubusercontent.com/72094319/181582640-bc0df490-f9ab-49d2-8052-50ad1a95a402.png)

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

![image](https://user-images.githubusercontent.com/72094319/181582864-7a5ce042-c3c5-4413-9dcd-59b773e081bb.png)

## Floating point (IEEE 754)
![image](https://user-images.githubusercontent.com/72094319/181583351-dce1571a-32b2-4505-b33d-086f4f01a291.png)
![image](https://user-images.githubusercontent.com/72094319/181595479-667f0258-0be0-466a-adaf-f3f7006f3476.png)
![image](https://user-images.githubusercontent.com/72094319/181595510-63341469-399e-455d-81bf-49b1e3f468d2.png)

```cpp
#include <iostream>
#include <bitset>

int main() {
	union {
		float f;
		uint32_t i;
	} uf;
	std::cout << "f> ";
	std::cin >> uf.f;
	uint32_t s = uf.i >> 31;
	uint32_t e = (uf.i << 1) >> 24;
	uint32_t m = (uf.i << 9) >> 9;
	std::cout << "Representation in memory: " << std::bitset<1>(s) << '\'' << std::bitset<8>(e) << '\'' << std::bitset<23>(m) << std::endl;
	std::cout << "Value: " << std::pow(-1, s) * std::pow(2, e - 127) * (1 + m / (std::pow(2, 23) - 1.));
	return 0;
}
```
