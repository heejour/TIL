# AWS S3 ListObjectsV2Request

ListObjectsV2Request 이란?

- S3에서 객체 목록을 가져옴 <br>

- .withBucketName(bucketName) : 버킷이름으로 검색 
- .withPrefix(prefix) : 접미사로 검색

확장자로 검색하고 싶었는데 기본으로 지원을 안해주는 듯 해서(아마 끝까지 다 읽어야해서..) objectKey를 읽어온 후 'endsWith(확장자)'로 필터링했다.


```java
import java.io.IOException;

import com.amazonaws.AmazonServiceException;
import com.amazonaws.SdkClientException;
import com.amazonaws.auth.profile.ProfileCredentialsProvider;
import com.amazonaws.services.s3.AmazonS3;
import com.amazonaws.services.s3.AmazonS3ClientBuilder;
import com.amazonaws.services.s3.model.ListObjectsV2Request;
import com.amazonaws.services.s3.model.ListObjectsV2Result;
import com.amazonaws.services.s3.model.S3ObjectSummary;

public class ListKeys {

    public static void main(String[] args) throws IOException {
        String clientRegion = "*** Client region ***";
        String bucketName = "*** Bucket name ***";
        
        try {    
            AmazonS3 s3Client = AmazonS3ClientBuilder.standard()
                    .withCredentials(new ProfileCredentialsProvider())
                    .withRegion(clientRegion)
                    .build();
    
            System.out.println("Listing objects");
    
            // maxKeys is set to 2 to demonstrate the use of
            // ListObjectsV2Result.getNextContinuationToken()
            ListObjectsV2Request req = new ListObjectsV2Request().withBucketName(bucketName).withMaxKeys(2);
            ListObjectsV2Result result;

            do {
                result = s3Client.listObjectsV2(req);
    
                for (S3ObjectSummary objectSummary : result.getObjectSummaries()) {
                    System.out.printf(" - %s (size: %d)\n", objectSummary.getKey(), objectSummary.getSize());
                }
                // If there are more than maxKeys keys in the bucket, get a continuation token
                // and list the next objects.
                String token = result.getNextContinuationToken();
                System.out.println("Next Continuation Token: " + token);
                req.setContinuationToken(token);
            } while (result.isTruncated());
        }
        catch(AmazonServiceException e) {
            // The call was transmitted successfully, but Amazon S3 couldn't process 
            // it, so it returned an error response.
            e.printStackTrace();
        }
        catch(SdkClientException e) {
            // Amazon S3 couldn't be contacted for a response, or the client
            // couldn't parse the response from Amazon S3.
            e.printStackTrace();
        }
    }
}
```


```java
		ListObjectsV2Request request = new ListObjectsV2Request().withBucketName(bucketName).withPrefix(prefix);
		ListObjectsV2Result result = s3Client.listObjectsV2(request);
	
		String objectKey = null;
		for(S3ObjectSummary objectSummary : result.getObjectSummaries()) {
			objectKey = objectSummary.getKey();
			// do something .. 
		}
```

### resource

- https://docs.aws.amazon.com/ko_kr/AmazonS3/latest/dev/ListingKeysHierarchy.html