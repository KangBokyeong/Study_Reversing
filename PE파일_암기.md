# PE파일 암기!
<!-- RVA와 VA -->
## 1. RVA(Relative Virual Address) + Image Base = VA(Virtual Address)
### RVA(Relative Virual Address)
- PE파일 구조에서 흔히 말하는 offset 값.
- 위 문장에 대한 이유는 구조의 재배치 때문임. [Ex) dll 로딩]
### VA(Virtual Address)
- 실제 나타나는 가상 메모리 주소
- Ollydbg에 나타나는 메모리 주소
### 예를 들어서
- RVA가 1000이고 Image Base가 0400000 일 때 VA는 0401000가 된다.
- RVA(1000) + Image Base(0400000) = VA(0401000)

<!-- 크기 -->
## 2. WORD와 DWORD의 크기
- **1byte** = **8bit**
### WORD
- 16bit = 2byte
### DWORD
- 32bit = 4byte
### 또 다른 정보
- 헥스에디터의 (두 개의 숫자가 붙은) 한 칸: 1byte
- ASCII 문자의 크기: (Approximitly) 1byte (≒ 7byte)

<!-- SectionAlignment -->
## 3. SectionAlignment
- Sectiond의 크기에 대한 단위
### Ex1
- SectionAlignment가 4096byte일 때 Section의 크기가 **100byte** 라면, 해당 Section은 **4096byte**의 크기를 가짐.
### Ex2
- SectionAlignment가 4096byte일 때 Section의 크기가 **5000byte** 라면, 해당 Section은 **8192byte**만큼의 크기를 가짐.

<!-- Endian Notation -->
## 4. 빅 & 리틀 엔디언의 차이
만약 "00 10 01 00" 이라는 데이터가 있을 때,

### 리틀 엔디언
- "00 01 10 00" 순으로 읽음
- 오른쪽에서 왼쪽으로
### 빅 엔디언
- "00 10 01 00" 순으로 읽음
- 왼쪽에서 오른쪽으로

<!-- 8byte register -->
## 5. 8바이트 레지스터
- AL, AH, BL, BH, CL, CH, DL, DH로 이루어져 있음.
- 여기서 L은 low byte, H는 high byte를 의미 함
- 사실, AX와 DX는 각각 AL,AH와 DL,DH의 조합임.
