# 1. 테이블
***
### **1-1. 직원 테이블 (`Employees`)**

| 컬럼명                   | 데이터 타입        | 설명                      |
| --------------------- | ------------- | ----------------------- |
| **Employee_ID**       | INT (PK)      | 직원 고유 식별자 (Primary Key) |
| **First_Name**        | VARCHAR(50)   | 이름                      |
| **Last_Name**         | VARCHAR(50)   | 성                       |
| **Full_Name**         | VARCHAR(100)  | 전체 이름                   |
| **Date_of_Birth**     | DATE          | 생년월일                    |
| **Gender**            | VARCHAR(10)   | 성별                      |
| **National_ID**       | VARCHAR(20)   | 주민등록번호 또는 여권번호          |
| **Address**           | VARCHAR(200)  | 주소                      |
| **Phone_Number**      | VARCHAR(20)   | 연락처                     |
| **Email**             | VARCHAR(100)  | 이메일                     |
| **Department_ID**     | INT (FK)      | 부서 식별자 (Foreign Key)    |
| **Position_ID**       | INT (FK)      | 직급 식별자 (Foreign Key)    |
| **Hire_Date**         | DATE          | 입사일                     |
| **Employment_Status** | VARCHAR(20)   | 재직 상태 (예: 재직, 휴직 등)     |
| **Salary**            | DECIMAL(15,2) | 급여                      |
| **Notes**             | TEXT          | 비고 또는 기타 메모             |


### **1-2. 부서 테이블 (`Departments`)**

| 컬럼명                 | 데이터 타입       | 설명                     |
| ------------------- | ------------ | ---------------------- |
| **Department_ID**   | INT (PK)     | 부서 고유 식별자              |
| **Department_Name** | VARCHAR(100) | 부서명                    |
| **Manager_ID**      | INT (FK)     | 부서 관리자 (`Employee_ID`) |
| **Location**        | VARCHAR(100) | 부서 위치                  |

### **1-3. 직급 테이블 (`Positions`)**

| 컬럼명                | 데이터 타입       | 설명        |
| ------------------ | ------------ | --------- |
| **Position_ID**    | INT (PK)     | 직급 고유 식별자 |
| **Position_Title** | VARCHAR(100) | 직급명       |

## 2. 관계 설정
***

- **`Employees` 테이블**의 `Department_ID`는 **`Departments` 테이블**의 `Department_ID`를 참조하는 **외래 키**.
- **`Employees` 테이블**의 `Position_ID`는 **`Positions` 테이블**의 `Position_ID`를 참조하는 **외래 키**.
- **`Departments` 테이블**의 `Manager_ID`는 **`Employees` 테이블**의 `Employee_ID`를 참조.


> [!TODO] TODO 데이터 보안 및 개인정보 보호
> - **민감한 정보 보호**: 주민등록번호, 급여 등 민감한 정보는 **암호화**하거나 **접근 권한을 엄격하게**해야 함.
> - **접근 제어**: 사용자 역할에 따라 데이터 접근 권한을 설정하여 불필요한 정보 노출을 방지시켜야됨.


