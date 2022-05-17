# String
## 루시와 엘라 찾기
### WHERE A = String
- 동물 중 이름이 Lucy, Elia, Pickle, Rogan, Sabrina, Mitty인 동물의 아디와 이름, 성별 및 중성화를 조회
```sql
SELECT ANIMAL_ID, NAME, SEX_UPON_INTAKE
FROM ANIMAL_INS
WHERE NAME = "Lucy" or NAME = "Ella" or NAME = "Pickle" or NAME = "Rogan" or NAME = "Sabrina" or NAME = "Mitty"
ORDER BY ANIMAL_ID
```

## 이름에 el이 들어가는 동물 찾기
### A like '%el%'
- 동물 이름이 EL이 들어가는 개의 아이디와 이름을 조회
```sql
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE ANIMAL_TYPE="Dog" AND NAME like '%el%' 
ORDER BY NAME
```

## 중성화 여부 파악하기
### IF(조건, 참일 떄 값, 거짓일 떄 값)
- 중성화 되었는지 아닌지 파악
```sql
SELECT ANIMAL_ID, NAME, IF(SEX_UPON_INTAKE like '%Neutered%' or SEX_UPON_INTAKE like '%Spayed%', 'O', 'X') AS 중성화
FROM ANIMAL_INS
ORDER BY ANIMAL_ID
```

## 오랜 기간 보호한 동물2
###


# Date
## DATETIME에서 DATE로 형 변환
###
- 각 동물의 아이디와 이름, 들어온 날짜를 조회
```
SELECT ANIMAL_ID, NAME, DATE_FORMAT(DATETIME, '%Y-%m-%d') AS 날짜
FROM ANIMAL_INS
ORDER BY ANIMAL_ID
```
