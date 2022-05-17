# SELECT
## 모두 조회하기
### SELECT *
- 모든 정보 조회
```sql
SELECT *
FROM ANIMAL_INS
```

## 역순 정렬하기
### ORDER BY A desc
- ANIMAL_ID 역순(내림차순)으로 정렬
```sql
SELECT NAME, DATETIME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID desc
```

## 특정 조건 찾기
### WHERE A = B
- 아픈 동물의 아이디와 이름을 조회
```sql
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION="Sick"
```

### WHERE A != B
- 어린 동물의 아이디와 이름을 조회
```sql
SELECT ANIMAL_ID, NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION!="Aged"
```

### ORDER BY A, B
- 이름 순으로, 같다면 보호를 나중에 시작한 순으로 정렬
```sql
SELECT ANIMAL_ID, NAME, DATETIME
FROM ANIMAL_INS
ORDER BY NAME, DATETIME desc
```

### LIMIT 숫자
- 가장 먼저 들어온 동물의 이름 조회
```sql
SELECT NAME
FROM ANIMAL_INS
ORDER BY DATETIME
LIMIT 1
```
