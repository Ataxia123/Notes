

Use React in your plugin

In this guide, you'll configure your plugin to use [React](https://reactjs.org/). It assumes that you already have a plugin with a [custom view](https://docs.obsidian.md/Plugins/User+interface/Views) that you want to convert to use React.

While you don't need to use a separate framework to build a plugin, there are a few reasons why you'd want to use React:

- You have existing experience of React and want to use a familiar technology.
- You have existing React components that you want to reuse in your plugin.
- Your plugin requires complex state management or other features that can be cumbersome to implement with regular [HTML elements](https://docs.obsidian.md/Plugins/User+interface/HTML+elements).

## 

Configure your plugin

1. Add React to your plugin dependencies:
    
    ```bash
    npm install react react-dom
    ```
    
2. Add type definitions for React:
    
    ```bash
    npm install --save-dev @types/react @types/react-dom
    ```
    
3. In `tsconfig.json`, enable JSX support on the `compilerOptions` object:
    
    ```ts
    {
      "compilerOptions": {
        "jsx": "react"
      }
    }
    ```
    

## 

Create a React component

Create a new file called `ReactView.tsx` in the plugin root directory, with the following content:

```tsx
import * as React from "react";

export const ReactView = () => {
  return <h4>Hello, React!</h4>;
};
```

## 

Mount the React component

To use the React component, it needs to be mounted on a [HTML elements](https://docs.obsidian.md/Plugins/User+interface/HTML+elements). The following example mounts the `ReactView` component on the `this.containerEl.children[1]` element:

```tsx
import { ItemView, WorkspaceLeaf } from "obsidian";
import * as React from "react";
import * as ReactDOM from "react-dom";
import { ReactView } from "./ReactView";
import { createRoot } from "react-dom/client";

const VIEW_TYPE_EXAMPLE = "example-view";

class ExampleView extends ItemView {
  constructor(leaf: WorkspaceLeaf) {
    super(leaf);
  }

  getViewType() {
    return VIEW_TYPE_EXAMPLE;
  }

  getDisplayText() {
    return "Example view";
  }

  async onOpen() {
    const root = createRoot(this.containerEl.children[1]);
    root.render(
      <React.StrictMode>
        <ReactView />,
      </React.StrictMode>
    );
  }

  async onClose() {
    ReactDOM.unmountComponentAtNode(this.containerEl.children[1]);
  }
}
```

For more information on `ReactDOM.render()` and `ReactDOM.unmountComponentAtNode()`, refer to the documentation on [ReactDOM](https://reactjs.org/docs/react-dom.html).

You can mount your React component on any `HTMLElement`, for example [status bar items](https://docs.obsidian.md/Plugins/User+interface/Status+bar). Just make sure to clean up properly by calling `ReactDOM.unmountComponentAtNode()` when you're done.

## 

Create an App context

If you want to access the [App](https://docs.obsidian.md/Reference/TypeScript+API/App/App) object from one of your React components, you need to pass it as a dependency. As your plugin grows, even though you're only using the `App` object in a few places, you start passing it through the whole component tree.

Another alternative is to create a React context for the app to make it globally available to all components inside your React view.

1. Use `React.createContext()` to create a new app context.
    
    ```tsx
    import * as React from "react";
    import { App } from 'obsidian';
    
    export const AppContext = React.createContext<App | undefined>(undefined);
    ```
    
2. Wrap the `ReactView` with a context provider and pass the app as the value.
    
    ```tsx
    const root = createRoot(this.containerEl.children[1]);
    root.render(
      <AppContext.Provider value={this.app}>
        <ReactView />
      </AppContext.Provider>,
      this.containerEl.children[1]
    );
    ```
    
3. Create a custom hook to make it easier to use the context in your components.
    
    ```tsx
    import { AppContext } from "./context";
    
    export const useApp = (): App | undefined => {
      return React.useContext(AppContext);
    };
    ```
    
4. Use the hook in any React component within `ReactView` to access the app.
    
    ```tsx
    import * as React from "react";
    import { useApp } from "./hooks";
    
    export const ReactView = () => {
      const { vault } = useApp();
    
      return <h4>{vault.getName()}</h4>;
    };
    ```
    

