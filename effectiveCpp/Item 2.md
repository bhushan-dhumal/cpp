# Prefer consts, enums and inlines to #defines

This item might better be called "prefer the compiler to the preprocessor"
- For simple constants, prefer const objects or enums to #defines.
- For function-like mcaros, prefer inline functions to #defines.
