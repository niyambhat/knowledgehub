---
sidebar_position: 5
---

# Fetching Data

Fetch is javascript function that allos us to make asynchronous javascript requests.

Its syntax is:

```javascript
fetch(url)
    .then(response => {
        // handle the response
    })
    .catch(error => {
        // handle the error
    });
    
```


#### 1. How to fetch Data in a React component?{#Controller}

Being a side-effect, you need to use the useEffect hook to deal with using the Fetch API calls in React.

```jsx
import { useState, useEffect } from "react"; 
 
export default function App() { 
  const [btcData, setBtcData] = useState({}); 
 
  const fetchData = () => { 
    fetch(`https://api.coindesk.com/v1/bpi/currentprice.json`) 
      .then((response) => response.json()) 
      .then((jsonData) => setBtcData(jsonData.bpi.USD)) 
      .catch((error) => console.log(error)); 
  }; 
 
  useEffect(() => { 
    fetchData(); 
  }, []); 

return (
  <>
    <h1>Current BTC/USD data</h1>
    {Object.keys(btcData).length > 0 ? (
      <>
        <p>Code: {btcData.code}</p>
        <p>Symbol: {btcData.symbol}</p>
        <p>Rate: {btcData.rate}</p>
        <p>Description: {btcData.description}</p>
        <p>Rate Float: {btcData.rate_float}</p>
      </>
    ) : (
      <p>Loading...</p>
    )}
  </>
);
```