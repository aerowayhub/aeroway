# aeroway
Chip-agnostic vRAN

## Prerequisites
...

## Project Structure
Aeroway(가칭)
├── docs
│    ├── aeroway_introduction (사용을 위한 가이드)
│    └── aeroway_impl_details (유지보수, 구현 추가를 위한 가이드)
├── awy
│    ├── aeroway.h
│    ├── intrinsics
│    │    ├── x86.h
│    │    ├── arm.h
│    │    └── shared.h
│    └── test
│          ├── APIs
│          │    ├── TestCommon.h (공통으로 사용되는 Test 용 API 정의, ex )Rand<int64>() 등 )
│          │    ├── Abs.cpp (API Name 단위로 파일 분리, highway style 인 arithmetic 등과 같은 type 분류는 선정과 관리, 협업에 있어 어려움이 예상됨)
│          │    ├── Add.cpp (구현 상에서는 operator + 로 구현되나, 파일명은 Add 로 원형을 따름)
│          │    ├── Adds.cpp (해당하는 API Name 에서 L1 에서 사용되는 모든 type 에 대해 test code 를 구현)
│          │    ├── And.cpp (file name 이 곧 test func name 이 되어, gtest_filter 를 사용할 수 있도록..)
│          │    └── xxx.cpp
│          ├── testmain.cpp (x86, arm test 용, output data 생성)
│          └── diffmain.py (x86, arm diff 비교)
├── CMakeLists.txt (L1 nPhy 의 CMake 와 독립적으로 동작, 상위 CMake 에서 정의한 Option/Flag 가 있어도/없어도 동작 가능하도록)
└── README.md

## How to Build
'''sh
$ cd aeroway/
$ ...
'''

## Contribution

