# React Hook for Paginating Firebase Collection in Realtime

This is a React hook for Paginating your Firebase Collections in Realtime using a lot of snapshots. 

## How it works

Basically, It reads the amount of documents you need per page, then it creates a snapshot listener for that particular page. Thus when any document updates, it will update your page as well.

> Used on [Speer Education](https://www.speeredu.com)