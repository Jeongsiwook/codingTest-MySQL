# IS NULL
## 이름이 없는 동물의 아이디
### A IS NULL
- 이름이 없는 채로 들어온 동물의 ID를 조회
```sql
SELECT ANIMAL_ID
FROM ANIMAL_INS
WHERE NAME IS NULL
```

## 이름이 있는 동물의 아이디
### A IS NOT NULL
- 이름이 있는 채로 들어온 동물의 ID를 조회
```sql
SELECT ANIMAL_ID
FROM ANIMAL_INS
WHERE NAME IS NOT NULL
ORDER BY ANIMAL_ID
```

## NULL 처리하기
###
- 동물의 생물 종, 이름, 성별 및 중성화 여부를 아이디 순으로 조회
```sql
SELECT ANIMAL_TYPE, IFNULL(NAME, "No name") AS NAME, SEX_UPON_INTAKE
FROM ANIMAL_INS
ORDER BY ANIMAL_ID
```
