# GROUP_BY
## 각각 몇 마리인지 조회
### COUNT(A)
- 동물 중 고양이와 개가 각각 몇 마리인지 조회
```sql
SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE)
FROM ANIMAL_INS
GROUP BY ANIMAL_TYPE
ORDER BY ANIMAL_TYPE
```

## 동명 동물 수 찾기
### GROUP BY A HAVING B
- 두 번 이상 쓰인 이름과 해당 이름이 쓰인 횟수를 조회
```sql
SELECT NAME, COUNT(NAME) AS COUNT
FROM ANIMAL_INS
WHERE NAME is NOT NULL
GROUP BY NAME
HAVING COUNT(NAME) > 1
ORDER BY NAME
```

## 입양 시각 구하기1
### GROUP BY A HAVING B
- 9시부터 19시 59분까지 각 시간대 입양이 몇 건 발생했는지
```sql
SELECT HOUR(DATETIME) AS HOUR, COUNT(DATETIME) AS COUNT
FROM ANIMAL_OUTS
GROUP BY HOUR(DATETIME)
HAVING HOUR >= 0 AND HOUR < 20
ORDER BY HOUR
```

## 입양 시각 구하기2
### SET @변수이름 := 값;
- 0시부터 23시까지, 각 시간대별로 입양이 몇 건 발생했는지
```sql
SET @hour := -1;
SELECT (@hour := @hour + 1) AS HOUR,
(SELECT COUNT(*)
 FROM ANIMAL_OUTS
 WHERE HOUR(DATETIME) = @hour) AS COUNT
FROM ANIMAL_OUTS
WHERE #hour < 23
```
