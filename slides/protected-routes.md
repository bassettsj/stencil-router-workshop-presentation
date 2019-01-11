## Protected Routes

```js
const auth = {
  isAuthenticated: false,
  authenticate: function() {
    this.isAuthenticated = true;
  },
  logout: function() {
    this.isAuthenticated = false;
  }
}

const PrivateRoute = ({ component, ...props}) => {
  const Component = component;
  return (
    <stencil-route {...props} routeRender={(props) => {
      if (auth.isAuthenticated) {
        return <Component {...props} {...props.componentProps} />;
      }
      return <stencil-router-redirect url='/'></stencil-router-redirect>;
    }}/>
  );
}
```

---

### Adding The Protected Route

```html
<stencil-router id="root" >
    <stencil-route-switch scrollTopOffset={0}>
        <stencil-route url='/' component='app-home' exact={true} />
        <stencil-route url='/profile/:name' component='app-profile' />
        <stencil-route url='/login' component='app-login' />
        <stencil-route url='/logout' component='app-logout' />
        <PrivateRoute url="/protected" component='app-protected' />
    </stencil-route-switch>
</stencil-router>
```
