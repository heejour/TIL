# Converting File to MultiPartFile

객체형을 바꿔야 할 때가 있다.

- MockMultiPartFile 을 사용 <br>

```java 
import org.springframework.mock.web.MockMultipartFile; 

MultipartFile multipartFile = new MockMultipartFile("test.xlsx", new FileInputStream(new File("/home/admin/test.csv"))); 
```

### resource

- https://stackoverflow.com/questions/16648549/converting-file-to-multipartfile