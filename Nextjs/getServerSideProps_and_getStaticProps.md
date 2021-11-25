# getServerSideProps() & getStaticProps()

Next.js의 data fetching functions
모두 pre-render가 필요한 경우에만 사용하는 것이 좋다.

## getStaticProps

- **빌드 시에 딱 한 번** 만 호출되고, 바로 static file로 빌드. 따라서, 이후 수정이 불가능

- **SSG (Static Site Generation)** 개념

- 앱 빌드 후에 웬만하면 바뀌지 않는 내용 (고정된 내용)이 있는 page가 있는 경우에만 사용하는 것이 좋음

- 장점은 호출 시 마다 매번 data fetch를 하지 않으니 getServerSideProps보다 성능면에서 좋다.

## getServerSideProps

- **page가 요청받을 때마다** 호출되어 pre-rendering
- **SSR (Server Side Rendering)** 개념

- pre-render가 꼭 필요한 동적 데이터가 있는 page에 사용하면됨
- 매 요청마다 호출되므로 성능은 getStaticProps에 뒤지지만, 내용을 언제든 동적으로 수정이 가능

```javascript
export async function getServerSideProps(context: any) {
  const { db } = await connectToDatabase();

  const data = await db.collection("properties").find({}).limit(20).toArray();
  const properties = JSON.parse(JSON.stringify(data));

  const filtered = properties.map((property: any) => {
    const price = JSON.parse(JSON.stringify(property.price));
    return {
      //props
      _id: property._id,
      title: property.title,
      description: property.description,
      seller: property.seller,
      price: price.$numberDecimal,
    };
  });
  console.log(filtered);

  return {
    props: { properties: filtered },
  };
}
```

### resource

- https://beside-lab.tistory.com/entry/Nextjs-getStaticProps-vs-getServerSideProps-%EC%B0%A8%EC%9D%B4%EC%99%80-%ED%99%9C%EC%9A%A9
