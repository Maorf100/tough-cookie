<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [tough-cookie](./tough-cookie.md) &gt; [Store](./tough-cookie.store.md) &gt; [updateCookie](./tough-cookie.store.updatecookie.md)

## Store.updateCookie() method

Update an existing [Cookie](./tough-cookie.cookie.md)<!-- -->. The implementation MUST update the `value` for a cookie with the same `domain`<!-- -->, `path`<!-- -->, and `key`<!-- -->. The implementation SHOULD check that the old value in the store is equivalent to oldCookie - how the conflict is resolved is up to the store.

**Signature:**

```typescript
updateCookie(oldCookie: Cookie, newCookie: Cookie): Promise<void>;
```

## Parameters

<table><thead><tr><th>

Parameter


</th><th>

Type


</th><th>

Description


</th></tr></thead>
<tbody><tr><td>

oldCookie


</td><td>

[Cookie](./tough-cookie.cookie.md)


</td><td>

the cookie that is already present in the store.


</td></tr>
<tr><td>

newCookie


</td><td>

[Cookie](./tough-cookie.cookie.md)


</td><td>

the cookie to replace the one already present in the store.


</td></tr>
</tbody></table>
**Returns:**

Promise&lt;void&gt;

## Remarks

- The `lastAccessed` property is always different between the two objects (to the precision possible via JavaScript's clock).

- Both `creation` and `creationIndex` are guaranteed to be the same.

- Stores MAY ignore or defer the `lastAccessed` change at the cost of affecting how cookies are selected for automatic deletion.

- Stores may wish to optimize changing the `value` of the cookie in the store versus storing a new cookie.

- The `newCookie` and `oldCookie` objects MUST NOT be modified.
