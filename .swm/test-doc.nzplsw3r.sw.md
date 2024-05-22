---
title: Test doc
---
<SwmSnippet path="/examples/blog-react-dnd/src/contexts/index.tsx" line="17">

---

Test sippet

```tsx

export const ColorModeContextProvider: React.FC<PropsWithChildren> = ({
  children,
}) => {
  const colorModeFromLocalStorage = localStorage.getItem("colorMode");
  const isSystemPreferenceDark = window?.matchMedia(
    "(prefers-color-scheme: dark)",
  ).matches;

  const systemPreference = isSystemPreferenceDark ? "dark" : "light";
  const [mode, setMode] = useState(
    colorModeFromLocalStorage || systemPreference,
  );

  useEffect(() => {
    window.localStorage.setItem("colorMode", mode);
  }, [mode]);

  const setColorMode = () => {
    if (mode === "light") {
      setMode("dark");
    } else {
      setMode("light");
    }
  };

  const { darkAlgorithm, defaultAlgorithm } = theme;

  return (
    <ConfigProvider
      theme={{
        algorithm: mode === "light" ? defaultAlgorithm : darkAlgorithm,
      }}
    >
      {children}
    </ConfigProvider>
  );
};

```

---

</SwmSnippet>

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBcmVmaW5lJTNBJTNBcmFqYW5hbmQwMg==" repo-name="refine"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
