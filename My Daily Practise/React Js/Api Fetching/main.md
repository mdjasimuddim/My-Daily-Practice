### We can fetch api using 4 ways

## Using Build in Fetch

```javascript
import React, { useEffect, useState } from 'react'

const Fetch = () => {
    const [api, setApi] = useState(null);
    useEffect(()=>{
        const fetchApi = async () => {
            const res = await fetch('http://api.quotable.io/random');
            const data = await res.json(); 
            setApi(data); 
        }
        fetchApi();
    },[])
  return (
    <div>
        {
            api?.content
        }
    </div>
  )
}

export default Fetch
```
## Using axios
```javascript
import axios from "axios";
import { useEffect, useState } from "react";
const Axios = () => {
    const [api, setApi] = useState(null);
    useEffect(()=>{
        let fetchApi = async() =>{
            let res = await axios.get("http://api.quotable.io/random");
            setApi(res.data);
        }
        fetchApi();
    },[])
  return (
    <div>
        {
            api?.content
        }
    </div>
  )
}

export default Axios
```
## Axios swr - state-while-revalidate
```javascript
import React from 'react'
import useSWR from 'swr'

const Axios = () => {
    const fetcher = async(...args) => {
        const res = await fetch(...args);
        const data = await res.json();
        return data;
    }
    const {data} = useSWR("http://api.quotable.io/random", fetcher);
    console.log(data);
  return (
    <div>
        {
            data?.content
        }
    </div>
  )
}

export default Axios

```

## Fetching api using React Query
```javascript

import {QueryClient, QueryClientProvider} from "react-query";
import ReactQuery from './Components/ReactQuery'

const App = () => {
  const client = new QueryClient();
  return (
    <div>
      {/* <LayoutComponentOne /> */}
      <QueryClientProvider client={client}>
        <ReactQuery />
        <ReactQuery />
      </QueryClientProvider>
    </div>
  )
}

export default App
```
```javascript
import React from 'react'
import { useQuery } from 'react-query'
import getQuateApi from './getQuateApi'

const ReactQuery = ({quote}) => {
    const {data} = useQuery("quote", () => getQuateApi());
  return (
    <div>
        {data?.content}
    </div>
  )
}

export default ReactQuery

```
```javascript
import React from 'react'

const getQuateApi = async() => {
    const res = await fetch("http://api.quotable.io/random");
    const data = await res.json();
    return data;
}

export default getQuateApi
```
