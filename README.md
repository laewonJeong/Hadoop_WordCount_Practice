# 🐘 **Hadoop WordCount Practice**
Hadoop MapReduce를 이용한 wordcount 실습 레포지토리

<br></br>
# 환경
<table>
	<tr><th rowspan="1">OS</th><td>Ubuntu20.04</td></tr>
	<tr><th rowspan="1">Java</th><td>openjdk-11-jdk</td></tr>
  	<tr><th rowspan="1">Hadoop</th><td>hadoop-3.4.0</td></tr>
</table>
<br></br>

# 😊 실습 준비
### `git clone`을 통해 본 레포지토리를 받기
```bash
git clone https://github.com/laewonJeong/Hadoop_WordCount_Practice.git
```
<br></br>

### `Let_it_go.txt` 파일 HDFS에 저장 (다른 파일 넣어도 됨)
```bash
hdfs dfs -put Let_it_go.txt <저장할 HDFS 경로> (ex. /wordcount_example)
```

<br></br>

# 🫡 jar 파일 생성

### `maven`을 통해 컴파일
```bash
mvn clean compile package
```
<br></br>

### 컴파일된 `jar` 파일 확인
```bash
ls target
```
![image](https://github.com/user-attachments/assets/cbc236dc-d56f-467c-b081-672a5756dc42)

<br></br>

# 🏃🏻‍♂️‍➡️ 실행
```bash
hadoop jar target/wordcount-1.0-SNAPSHOT.jar com.example.WordCountDriver <HDFS Input data 경로> <결과를 저장할 HDFS 경로>
```
### example
```bash
hadoop jar target/wordcount-1.0-SNAPSHOT.jar com.example.WordCountDriver /wordcount_example/Let_it_go.txt /wordcount_example/output
```
![image](https://github.com/user-attachments/assets/22745248-84c2-4a73-89a2-68a16746bda8)

<br></br>

# ✅ 결과 확인
```bash
hdfs dfs -cat <결과를 저장한 HDFS 경로>/part-r-00000
```
### example
```bash
hdfs dfs -cat /wordcount_example/output/part-r-00000
```
