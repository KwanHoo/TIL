# _MERGE INTO_

## MERGE INTO

- 테이블에 데이터가 이미 있으면 업데이트를 실행하고, 없을 경우 값을 넣어줘야 하는 경우 사용

1. 값이 있는지 확인
2. 있으면 UPDATE
3. 없으면 INSERT

## 구문

```SQL
    MERGE INTO [TABLE / VIEW] /* update 또는 insert 할 테이블 혹은 뷰 */
        USING  [TABLE / VIEW / DUAL] /* 비교할 대상 테이블 혹은 뷰 ( 위 테이블과 동일한 경우 DUAL을 사용*/
        ON [조건] /* UPDATE와 INSERT 처리할 조건문(조건이 일치하면 UPDATE / 불일치 시 INSERT) */
        WHEN MATCHED THEN
            UPDATE SET
            [COLUMN1] = [VALUE1],
            [COLUMN2] = [VALUE2],
            ...
            (DELETE [TABLE] WHERE [COLUMN1] = [VALUE1] AND ...) /* UPDATE 뿐만 아니라 DELETE 구문도 사용 가능 */
        WHEN NOT MATCHED THEN
            INSERT (COLUMN1, COLUMN2, ...)
            VALUES (VALUE1, VALUE2, ...)
```
