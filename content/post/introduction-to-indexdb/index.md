---
title: Introduction to IndexDB
summary: IndexedDB is a low-level API for storing significant amounts of structured data in the browser. It's particularly useful for web applications that need to work offline or cache data locally.
authors:
  - admin
date: '2024-02-01'
lastmod: '2024-02-01'
draft: false
featured: false
image:
  caption: 'IndexDB'
  focal_point: ''
  preview_only: false
projects: []
---

# Beginner's Guide to IndexedDB in React

IndexedDB is a low-level API for storing significant amounts of structured data in the browser. It's particularly useful for web applications that need to work offline or cache data locally. In this guide, we'll explore how to use IndexedDB in a React application with an example.

## What is IndexedDB?

IndexedDB is a client-side storage solution that allows developers to store data as key-value pairs. It supports advanced features such as:

- Transactions.
- Queries using indexes.
- Large data storage.
- Offline data persistence.

However, IndexedDB's API can be a bit verbose and asynchronous, so using a wrapper library like [idb](https://www.npmjs.com/package/idb) can simplify working with it.

## Why Use IndexedDB?

- **Offline Support**: Store data locally for offline access.
- **High Capacity**: Handle large datasets compared to localStorage.
- **Structured Data**: Store and query structured data efficiently.

## Setting Up IndexedDB in a React App

### Step 1: Install the `idb` Library

To simplify the use of IndexedDB, we'll use the `idb` library. Install it with:

```bash
npm install idb
```

### Step 2: Create a Utility for IndexedDB

Let's create a helper file to manage our IndexedDB interactions.

#### `indexedDBUtils.js`

```javascript
import { openDB } from 'idb';

const DATABASE_NAME = 'my-react-db';
const STORE_NAME = 'my-store';

// Initialize the database
export async function initializeDB() {
  return openDB(DATABASE_NAME, 1, {
    upgrade(db) {
      if (!db.objectStoreNames.contains(STORE_NAME)) {
        db.createObjectStore(STORE_NAME, { keyPath: 'id', autoIncrement: true });
      }
    },
  });
}

// Add data to the store
export async function addData(db, value) {
  const tx = db.transaction(STORE_NAME, 'readwrite');
  const store = tx.objectStore(STORE_NAME);
  await store.add(value);
  await tx.done;
}

// Get all data from the store
export async function getAllData(db) {
  const tx = db.transaction(STORE_NAME, 'readonly');
  const store = tx.objectStore(STORE_NAME);
  return store.getAll();
}

// Delete data by ID
export async function deleteData(db, id) {
  const tx = db.transaction(STORE_NAME, 'readwrite');
  const store = tx.objectStore(STORE_NAME);
  await store.delete(id);
  await tx.done;
}
```

### Step 3: Use IndexedDB in React

Now, we'll create a React component to interact with our IndexedDB.

#### `App.js`

```javascript
import React, { useEffect, useState } from 'react';
import { initializeDB, addData, getAllData, deleteData } from './indexedDBUtils';

const App = () => {
  const [db, setDb] = useState(null);
  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState('');

  useEffect(() => {
    // Initialize the database
    const setupDB = async () => {
      const dbInstance = await initializeDB();
      setDb(dbInstance);
      const storedItems = await getAllData(dbInstance);
      setItems(storedItems);
    };
    setupDB();
  }, []);

  const handleAddItem = async () => {
    if (!db || !newItem) return;
    await addData(db, { value: newItem });
    const updatedItems = await getAllData(db);
    setItems(updatedItems);
    setNewItem('');
  };

  const handleDeleteItem = async (id) => {
    if (!db) return;
    await deleteData(db, id);
    const updatedItems = await getAllData(db);
    setItems(updatedItems);
  };

  return (
    <div style={{ padding: '20px' }}>
      <h1>React + IndexedDB Example</h1>
      <input
        type="text"
        value={newItem}
        onChange={(e) => setNewItem(e.target.value)}
        placeholder="Enter item"
      />
      <button onClick={handleAddItem}>Add Item</button>
      <ul>
        {items.map((item) => (
          <li key={item.id}>
            {item.value}
            <button onClick={() => handleDeleteItem(item.id)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default App;
```

### Step 4: Run the Application

Start your React app:

```bash
npm start
```

Now, you can:

- Add new items to IndexedDB.
- View all stored items.
- Delete items by their ID.

## Key Takeaways

- **Async Nature**: IndexedDB operations are asynchronous.
- **Persistence**: Data stored in IndexedDB remains even after the browser is closed.
- **Structured Storage**: Use object stores for organizing data.

By using IndexedDB and the `idb` library, you can efficiently manage offline data storage in your React applications. Experiment with this example and expand it to fit your needs!