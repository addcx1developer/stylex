---
sidebar_position: 2
---

# Disallowing style properties

There are cases where allowing arbitrary styles may be too permissive for your custom component and you want to ensure that certain style properties are never overridden.

For example, you may want to disallow overriding layout properties while allowing other styles that won't break the layout.

For these use cases, you can use the `XStyleWithout<>` type.

```tsx
type XStyleWithoutLayout = XStyleWithout<{
  postion: unknown,
  display: unknown,
  top: unknown,
  start: unknown,
  end: unknown,
  bottom: unknown,
  border: unknown,
  borderWidth: unknown,
  borderBottomWidth: unknown,
  borderEndWidth: unknown,
  borderStartWidth: unknown,
  borderTopWidth: unknown,
  margin: unknown,
  marginBottom: unknown,
  marginEnd: unknown,
  marginStart: unknown,
  marginTop: unknown,
  padding: unknown,
  paddingBottom: unknown,
  paddingEnd: unknown,
  paddingStart: unknown,
  paddingTop: unknown,
  width: unknown,
  height: unknown,
  flexBasis: unknown,
  overflow: unknown,
  overflowX: unknown,
  overflowY: unknown,
}>;

type Props = {
  // ...
  xstyle?: XStyleWithoutLayout,
};

function MyComponent({xstyle, ...}: Props) {
  return (
    <div
      className={stylex(localStyles.foo, localStyles.bar, xstyle)}
    >
      {/* ... */}
    </div>
  );
}
```