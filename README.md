# React Hook for Paginating Firebase Collection in Realtime

This is a React hook for Paginating your Firebase Collections in Realtime using a lot of snapshots. 

## How it works

Basically, It reads the amount of documents you need per page, then it creates a snapshot listener for that particular page. Thus when any document updates, it will update your page as well.

## Basic Usage
```ts
const [blogPosts, loadMore, loading, finished] = usePaginateCollection<PostDocument>(collectionRef, {
      orderKey: 'postedDate',
      direction: 'desc',
      pageLimit: DOCUMENTS_PER_PAGE
  })

useEffect(() => {
  if(atBottom) loadMore()
}, [atBottom])

return <div>
  {blogPosts.map(blog => <BlogViewer blog={blog} />)
</div>

```

## API Reference
```ts
const usePaginateCollection = <DocType extends DocumentData = DocumentData>(colRef: CollectionReference<DocType>, {
    orderKey: string,
    pageLimit: number,
    direction: 'asc' | 'desc',
    queryConstraints?: QueryConstraint[],
    sortFunc?: (a: DocType, b: DocType) => number
}) => [DocType[], () => void, boolean, boolean]
```

## Issues
If there are any issues, feel free to open an issue and i'll fix it ASAP.


> Used on [Speer Education](https://www.speeredu.com)
