# MAX
## 최댓값 구하기
### MAX(A)
- 가장 최근에 들어온 동물 조회
```sql
SELECT MAX(DATETIME) AS 시간
FROM ANIMAL_INS
```

# MIN
## 최솟값 구하기
### MIN(A)
- 가장 먼저 들어온 동물 조회
```sql
SELECT MIN(DATETIME) AS 시간
FROM ANIMAL_INS
```

# SUM
## 합계 구하기
### SUM(A)
- 동물이 몇 마리 들어왔는 지 조회
```sql
SELECT SUM(DATETIME) AS count
FROM ANIMAL_INS
```

## 중복 제거하기
### DISTINCT A
- 동물의 이름 몇 개인지 조회
```sql
SELECT SUM(DISTINCT NAME) AS count
FROM ANIMAL_INS
```
