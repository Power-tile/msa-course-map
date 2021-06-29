# MSA Course Map

## Data Input for Frontend

### Courses

Every course should be a JSON object:

| Name         | Value Type           | Description                                                  | Example                            |
| ------------ | -------------------- | ------------------------------------------------------------ | ---------------------------------- |
| ```id```     | ```Integer```        | Primary key in SQL database, unique identifier for each course | ```1```                            |
| ```cname```  | ```String```         | Chinese name of course                                       | ```"算法与数据结构"```             |
| ```ename```  | ```String```         | English name of course                                       | ```"Algorithm & Data Structure"``` |
| ```code```   | ```String```         | Course code                                                  | ```"COMP5002"```                   |
| ```prereq``` | ```Array<Integer>``` | All course ```id``` of prerequisite courses*                 | ```[3, 5, 6]```                    |
| ```subseq``` | ```Array<Integer>``` | All course ```id``` for subsequent courses*                  | ```[4]```                          |

*Remember to update both the ```subseq``` and ```prereq``` of two courses when a dependency relationship is added.

### Fields

Every field should be a JSON object:

| Name        | Value Type    | Description                                                  | Example                  |
| ----------- | ------------- | ------------------------------------------------------------ | ------------------------ |
| ```id```    | ```Integer``` | Primary key in SQL database, unique identifier for each field | ```1```                  |
| ```cname``` | ```String```  | Chinese name of field                                        | ```"计算机科学"```       |
| ```ename``` | ```String```  | English name of course                                       | ```"Computer Science"``` |

### Relationships

Every relationship between a field and a suggested course in that field should be a JSON object:

| Name            | Value Type                                | Description                                                  | Example |
| --------------- | ----------------------------------------- | ------------------------------------------------------------ | ------- |
| ```id```        | ```Integer```                             | Primary key in SQL database, unique identifier for each relationship | ```1``` |
| ```field_id```  | ```Integer```                             | ```id``` of field                                            | ```1``` |
| ```course_id``` | ```Integer```                             | ```id``` of suggested course in this field                   | ```5``` |
| ```grade```     | ```Integer``` between ```1``` and ```8``` | Suggested grade of this course **if learning in this field**. ```1``` and ```8``` refers to Grade 9 Fall semester and Grade 12 Autumn semester, respectively. | ```3``` |
