# Java에서 Temp File을 만들어봅시다.

서버의 로컬이나 어느 저장소에 저장하지 않고, 임시파일로 만들어서 작업해야하는 경우가 있다.<br>
프로세스 상에서만 살아있는 파일을 만들어보는 방법 <br>

```java 
// JVM 종료와 함께 생성되었던 파일이 삭제됨
File tempfile = File.createTempFile("temp_", ".tmp");
tempfile.deleteOnExit();

```



### resource

- https://dev.umejintan.com/9