---
sidebar_position: 3
---

# Simple Search & Filtering
This UI Component allows us to create a Filterable Product list. 

### SearchApp
```JSX
import React from 'react'
import FilterableProductTable from './FilterableProductTable'

function SearchApp() {
  return (
    <div>
    <FilterableProductTable/>
    </div>
  )
}

export default SearchApp
```

### SearchApp



```JSX
import React from 'react'
import FilterableProductTable from './FilterableProductTable'

function SearchApp() {
  return (
    <div>
    <FilterableProductTable/>
    </div>
  )
}

export default SearchApp
```

The Searchbar is responsible for filtering and displaying the elements in the UI. It s only function is to set the Search string and checkbox. 

```JSX
import React from "react";
export function SearchBar({
    filterText,
    inStockOnly,
    onFilterTextChange,
    onInStockOnlyChange
  }){
    return (
        <form>
        <input 
          type="text" 
          value={filterText} placeholder="Search..." 
          onChange={(e) => onFilterTextChange(e.target.value)} />
        <label>
          <input 
            type="checkbox" 
            checked={inStockOnly} 
            onChange={(e) => onInStockOnlyChange(e.target.checked)} />
          {' '}
          Only show products in stock
        </label>
      </form>
    );
  }
```

The following components present the Data grid.
Product Row, ProductCategory Row & The product table. It is upon us to modify this to suit our filtering.
Some of the features we can add are drop down. This UI concept is modular and can be expand across for an optimised app.

```JSX
import React from 'react'

function ProductRow({product}) {
const name = product.stocked ? product.name :
<span style={{ color: 'red' }}>
    {product.name}
</span>;
  return (
    <tr>
    <td>{name}</td>
    <td>{product.price}</td>
  </tr>
    )
}

export default ProductRow
```

```JSX
import React from 'react'

function ProductCategoryRow({category}) {
  return (
    <tr>
    <th colSpan="2">
      {category}
    </th>
  </tr> 
   )
}

export default ProductCategoryRow
```

```JSX
import React, { useEffect } from 'react'
import ProductCategoryRow from './ProductCategoryRow';
import ProductRow from './ProductRow';

function ProductTable({products,filterText, inStockOnly}) {

const rows = [];
let lastCategory = null;

products.forEach((product) => {
  let checker =  product.name.toLowerCase().indexOf(filterText.toLowerCase())
   if(checker === -1)
   {
    return;
  }
  if (inStockOnly && !product.stocked) {
    return;
  }
  if (product.category !== lastCategory) {
    rows.push(
      <ProductCategoryRow
        category={product.category}
        key={product.category} />
    );
  }
  rows.push(
    <ProductRow
      product={product}
      key={product.name} />
  );
  lastCategory = product.category;
});

  return (
    <table>
    <thead>
      <tr>
        <th>Name</th>
        <th>Price</th>
      </tr>
    </thead>
    <tbody>
    {rows}    
    </tbody>
  </table>  )
}


export default ProductTable
```


## Main App
```JSX
import React,{useState} from 'react'
import { SearchBar } from './SearchBar'
import ProductTable from './ProductTable';
const products = [
    {category: "Fruits", price: "$1", stocked: true, name: "Apple"},
    {category: "Fruits", price: "$1", stocked: true, name: "Dragonfruit"},
    {category: "Fruits", price: "$2", stocked: false, name: "Passionfruit"},
    {category: "Vegetables", price: "$2", stocked: true, name: "Spinach"},
    {category: "Vegetables", price: "$4", stocked: false, name: "Pumpkin"},
    {category: "Vegetables", price: "$1", stocked: true, name: "Peas"}
  ];

function FilterableProductTable() {
    const [filterText, setFilterText] = useState('');
    const [inStockOnly, setInStockOnly] = useState(false);
   return (
    <div>
  <SearchBar 
        filterText={filterText} 
        inStockOnly={inStockOnly} 
        onFilterTextChange={setFilterText} 
        onInStockOnlyChange={setInStockOnly} />
    <ProductTable products={products} 
        filterText={filterText}
        inStockOnly={inStockOnly} />
  </div>
  )
}
export default FilterableProductTable
```
