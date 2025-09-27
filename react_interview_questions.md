# React Frontend Interview Questions & Answers

This document provides a complete set of **React Frontend Interview Questions & Answers** structured from beginner to advanced.

---

## 🟢 Beginner Level (Core React)

### 1. What is React?

**Answer (Interview style):**
React is a JavaScript library created by Facebook for building user interfaces. It’s component-based, declarative, and efficient, using a virtual DOM for better performance.

---

### 2. What are the main features of React?

**Answer:**

* Component-based architecture
* Virtual DOM for faster updates
* JSX syntax
* One-way data binding
* Support for hooks and functional components

---

### 3. What are components in React?

**Answer:**
Components are reusable building blocks of React apps. They can be **class components** or **functional components**. Each component manages its own logic and UI.

---

### 4. What are props in React?

**Answer:**
Props are inputs passed into components. They are immutable and make components reusable. For example:

```jsx
<Button label="Click me" />
```

---

### 5. What is state in React?

**Answer:**
State is a built-in object that stores dynamic data inside a component. Changing state triggers a re-render of the component.

---

### 6. Difference between props and state?

**Answer:**

* **Props**: Passed from parent, read-only.
* **State**: Managed inside the component, can change.

---

### 7. What is JSX?

**Answer:**
JSX is a syntax extension of JavaScript that looks like HTML but compiles to `React.createElement`. Example:

```jsx
const element = <h1>Hello World</h1>;
```

---

### 8. What is the Virtual DOM?

**Answer:**
Virtual DOM is a lightweight representation of the real DOM. React updates the virtual DOM first, then applies only the necessary changes to the real DOM (diffing).

---

### 9. What are keys in React and why are they important?

**Answer:**
Keys help React identify which items in a list changed, added, or removed. They improve rendering efficiency.

---

### 10. What are fragments in React?

**Answer:**
Fragments (`<> </>`) allow grouping multiple elements without adding extra DOM nodes.

---

## 🟡 Intermediate Level (Hooks, Context, Routing)

### 11. What are React Hooks?

**Answer:**
Hooks let you use state and lifecycle features in functional components. Common ones: `useState`, `useEffect`, `useContext`.

---

### 12. Explain useState hook.

**Answer:**
`useState` lets you add state to a functional component. Example:

```jsx
const [count, setCount] = useState(0);
```

---

### 13. Explain useEffect hook.

**Answer:**
`useEffect` handles side effects (API calls, subscriptions, timers). Example:

```jsx
useEffect(() => {
  console.log("Component mounted");
}, []);
```

---

### 14. Difference between useEffect and useLayoutEffect?

**Answer:**

* `useEffect`: Runs after rendering (async).
* `useLayoutEffect`: Runs synchronously before painting.

---

### 15. What is Context API?

**Answer:**
Context provides a way to pass data without prop drilling. Used for themes, authentication, etc.

---

### 16. How does React Router work?

**Answer:**
It enables client-side routing. Components like `<BrowserRouter>`, `<Route>`, and `<Link>` handle navigation without refreshing the page.

---

### 17. What is lazy loading in React?

**Answer:**
Lazy loading loads components only when needed using `React.lazy` and `Suspense`.

---

### 18. What is code splitting?

**Answer:**
Code splitting breaks bundles into smaller chunks so only required code loads, improving performance.

---

### 19. What is the difference between controlled and uncontrolled components?

**Answer:**

* Controlled: Input values controlled by React state.
* Uncontrolled: Managed by the DOM via refs.

---

### 20. How do you handle forms in React?

**Answer:**
Using controlled components with `useState`, or uncontrolled components with `useRef`.

---

## 🔴 Advanced Level (Optimization, Redux, Next.js, Testing)

### 21. What is Redux?

**Answer:**
Redux is a state management library that provides a global store, reducers, and actions to manage application state predictably.

---

### 22. Explain Redux data flow.

**Answer:**

1. Dispatch action
2. Reducer updates state
3. Store saves state
4. Components subscribe and re-render

---

### 23. Difference between Context API and Redux?

**Answer:**
Context API is simpler, good for small apps. Redux is better for large apps with complex state logic, middlewares, and debugging tools.

---

### 24. What are Redux middleware?

**Answer:**
Middleware sits between dispatching an action and the reducer. Examples: `redux-thunk` (async), `redux-saga` (side effects).

---

### 25. What is useReducer hook?

**Answer:**
An alternative to `useState` for complex state logic. Works like a local Redux reducer.

---

### 26. What is memoization in React?

**Answer:**
Caching results to avoid re-computation. Tools: `React.memo`, `useMemo`, `useCallback`.

---

### 27. Difference between useMemo and useCallback?

**Answer:**

* `useMemo`: Memoizes a value.
* `useCallback`: Memoizes a function.

---

### 28. How do you optimize React app performance?

**Answer:**

* Use React.memo
* Virtualize lists
* Use lazy loading
* Minimize re-renders
* Optimize bundle size

---

### 29. What is SSR (Server-Side Rendering)?

**Answer:**
SSR renders React on the server and sends HTML to the client. Improves SEO and performance. Example: Next.js.

---

### 30. What is SSG (Static Site Generation)?

**Answer:**
SSG pre-renders pages at build time. Example: blogs built with Next.js.

---

### 31. What is Next.js?

**Answer:**
A React framework with SSR, SSG, API routes, image optimization, and built-in routing.

---

### 32. What is hydration in React?

**Answer:**
Hydration is attaching React event handlers to pre-rendered HTML from SSR.

---

### 33. What is React Suspense?

**Answer:**
Suspense lets React wait for async operations (like lazy loading) before rendering fallback UI.

---

### 34. What are error boundaries?

**Answer:**
Special components that catch JavaScript errors in child components and display fallback UI.

---

### 35. How do you test React apps?

**Answer:**

* Jest for unit tests
* React Testing Library for components
* Cypress or Playwright for end-to-end tests

---

### 36. What is snapshot testing?

**Answer:**
Snapshot testing saves a rendered component’s output and compares future renders against it.

---

### 37. What are higher-order components (HOCs)?

**Answer:**
Functions that take a component and return a new component with added functionality.

---

### 38. What are render props?

**Answer:**
A pattern where a component’s child is a function. Example:

```jsx
<DataProvider render={(data) => <List data={data} />} />
```

---

### 39. What is reconciliation in React?

**Answer:**
The process where React compares the new virtual DOM with the old one and updates only what changed.

---

### 40. What are React Portals?

**Answer:**
Portals allow rendering children into a DOM node outside the parent component hierarchy.

---

## 🟣 System Design & Practical Frontend

### 41. How do you handle authentication in React apps?

**Answer:**

* Use JWT or OAuth2
* Store tokens in HttpOnly cookies
* Protect routes with guards in React Router

---

### 42. How do you secure React applications?

**Answer:**

* Escape input to prevent XSS
* Use CSRF tokens
* Use HTTPS
* Avoid storing tokens in localStorage

---

### 43. What are Progressive Web Apps (PWAs)?

**Answer:**
PWAs are web apps that behave like native apps. They support offline mode, push notifications, and installability.

---

### 44. How do you implement i18n (internationalization)?

**Answer:**
Using libraries like `react-i18next` or `react-intl` to handle translations and locales.

---

### 45. How do you implement dark mode in React?

**Answer:**
Maintain theme state in Context/Redux and switch CSS variables dynamically.

---

### 46. How do you handle API calls in React?

**Answer:**

* Use `fetch` or `axios` inside `useEffect`
* Manage loading/error states
* Use React Query for caching and retries

---

### 47. What is React Query?

**Answer:**
A library for data fetching and caching. Handles retries, background updates, and simplifies async state.

---

### 48. How do you handle file uploads?

**Answer:**
Use `<input type="file" />`, capture with `onChange`, and send via `FormData`.

---

### 49. How do you handle large lists?

**Answer:**
Use list virtualization libraries like `react-window` or `react-virtualized`.

---

### 50. What are best practices for scalable React apps?

**Answer:**

* Organize folders by features
* Reusable components
* TypeScript for type safety
* Performance optimization
* Unit & integration testing
* Use linting and CI/CD
