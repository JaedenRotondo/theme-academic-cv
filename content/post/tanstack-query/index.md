---
title: Introduction to Tanstack Query
summary: TanStack Query (formerly React Query) is a powerful library that simplifies data fetching, caching, synchronization, and state management in React applications.
authors:
  - admin
date: '2024-01-01'
lastmod: '2024-01-01'
draft: false
featured: false
image:
  caption: ''
  focal_point: ''
  preview_only: false
projects: []
---

# Mastering TanStack Query for API Requests in TypeScript

TanStack Query (formerly React Query) is a powerful library that simplifies data fetching, caching, synchronization, and state management in React applications. Its seamless integration with TypeScript makes it an essential tool for building robust and type-safe applications.

In this article, we'll explore how to use TanStack Query to fetch data from an API in TypeScript, ensuring type safety and optimal performance.

## Why Use TanStack Query?

Traditional data fetching in React often involves manually managing `useState`, `useEffect`, and loading states. TanStack Query abstracts these complexities, providing:

- **Automatic Caching**: Minimize redundant API calls.
- **Background Updates**: Keep data fresh without reloading.
- **Error Handling**: Centralized and consistent error management.
- **TypeScript Support**: Ensure type safety throughout the data lifecycle.

## Installation

To get started, install the required dependencies:

```bash
npm install @tanstack/react-query
npm install @tanstack/react-query-devtools
```

## Setting Up TanStack Query

First, wrap your application in the `QueryClientProvider` to provide a `QueryClient` instance:

```typescript
import React from "react";
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

const queryClient = new QueryClient();

const App = () => (
  <QueryClientProvider client={queryClient}>
    {/* Your App Components */}
  </QueryClientProvider>
);

export default App;
```

You can also include the React Query Devtools for debugging:

```typescript
import { ReactQueryDevtools } from "@tanstack/react-query-devtools";

<QueryClientProvider client={queryClient}>
  {/* Your App Components */}
  <ReactQueryDevtools initialIsOpen={false} />
</QueryClientProvider>;
```

## Fetching Data with TypeScript

### Step 1: Define the API Response Type

Assume you're fetching data from a user API. Define the expected response type:

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}
```

### Step 2: Create a Fetch Function

Write a function to fetch data from the API:

```typescript
const fetchUsers = async (): Promise<User[]> => {
  const response = await fetch("https://api.example.com/users");
  if (!response.ok) {
    throw new Error("Failed to fetch users");
  }
  return response.json();
};
```

### Step 3: Use `useQuery` to Fetch Data

Now, use the `useQuery` hook to fetch and cache the data:

```typescript
import { useQuery } from "@tanstack/react-query";

const UsersList = () => {
  const { data, isLoading, error } = useQuery<User[]>({
    queryKey: ["users"],
    queryFn: fetchUsers,
  });

  if (isLoading) return <p>Loading...</p>;
  if (error instanceof Error) return <p>Error: {error.message}</p>;

  return (
    <ul>
      {data?.map((user) => (
        <li key={user.id}>
          {user.name} ({user.email})
        </li>
      ))}
    </ul>
  );
};

export default UsersList;
```

### Explanation

1. **`queryKey`**: Uniquely identifies the query. Use it to cache and retrieve data.
2. **`queryFn`**: The function that fetches data.
3. **`isLoading`**: Indicates the loading state.
4. **`error`**: Handles errors gracefully.

## Mutations with TanStack Query

For operations like creating or updating data, use `useMutation`. Here's an example of creating a new user:

```typescript
import { useMutation, useQueryClient } from "@tanstack/react-query";

const createUser = async (newUser: Omit<User, "id">): Promise<User> => {
  const response = await fetch("https://api.example.com/users", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify(newUser),
  });
  if (!response.ok) {
    throw new Error("Failed to create user");
  }
  return response.json();
};

const AddUser = () => {
  const queryClient = useQueryClient();
  const mutation = useMutation(createUser, {
    onSuccess: () => {
      queryClient.invalidateQueries(["users"]); // Refresh user list
    },
  });

  const handleAddUser = () => {
    mutation.mutate({ name: "John Doe", email: "john@example.com" });
  };

  return (
    <button onClick={handleAddUser} disabled={mutation.isLoading}>
      Add User
    </button>
  );
};
```

## Conclusion

TanStack Query simplifies API data management in TypeScript with robust features like caching, error handling, and background updates. Its strong TypeScript support ensures type safety, making your applications more maintainable.

Integrating TanStack Query into your project will streamline your workflow, reduce boilerplate code, and enhance the user experience. Start using it today and take your React projects to the next level!