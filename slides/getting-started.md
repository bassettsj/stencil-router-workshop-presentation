## Getting Started

```
npm create stencil
```

* select the app

---

### Setting Up The Router Instance

```js
<stencil-router id="root" >
    <stencil-route-switch scrollTopOffset={0}>
        <stencil-route url='/' component='app-home' exact={true} />
        <stencil-route url='/profile/:name' component='app-profile' />
    </stencil-router-switch>
</stencil-router>
```

