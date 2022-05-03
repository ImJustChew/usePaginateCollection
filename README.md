# React Hook for Paginating Firebase Collection in Realtime

This is a React hook for Paginating your Firebase Collections in Realtime using a lot of snapshots. 

## How it works

Basically, It reads the amount of documents you need per page, then it creates a snapshot listener for that particular page. Thus when any document updates, it will update your page as well.

## Basic Usage
```js
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
TBD

> Used on [Speer Education](https://www.speeredu.com)
