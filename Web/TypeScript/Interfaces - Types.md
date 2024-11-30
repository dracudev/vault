- Always use `interface` for public API's definition when authoring a library or 3rd party ambient type definitions, as this allows a consumer to extend them via _declaration merging_ if some definitions are missing.
    
- Consider using `type` for your React Component Props and State, for consistency and because it is more constrained.