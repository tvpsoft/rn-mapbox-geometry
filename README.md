<!-- omit in toc -->
# rn-mapbox-geometry

### Minor general issues

- There are some temporary changes to [`tsconfig.json`](tsconfig.json) to work around TypeScript errors in `@rnmapbox/maps`
  (see https://github.com/rnmapbox/maps/issues/2333).
- In some client applications, while running in development mode, the library will emit the following warning:
  `"[mobx] Derivation observer_StoreProvider is created/updated without reading any observable value"`
  Refer to the comments in `src/state/StoreProvider.tsx` for details.
- There are inconsistent performance issues with React Native Paper-based dialogs.
  Presently these issues seem to be observed only on iOS, and only with dialogs
  that need to manage some local state.
  A possibly related issue may be https://github.com/callstack/react-native-paper/issues/2157
- Enumeration and boolean-typed geometry metadata fields are always given values during metadata creation or editing operations, even if the client application marks the fields as `'yup.optional'` (optional) fields, or marks the fields as non-creatable or non-editable.
  This is not necessarily a problem, since these fields will therefore always be given valid values.
  The library is still able to handle enumeration and boolean-typed fields that have missing or invalid values, however, such as when rendering metadata created outside the library.

