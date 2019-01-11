## Setting Up Nested Routes

```js
import { Component } from '@stencil/core';

@Component({
  tag: 'app-messages',
  styleUrl: 'app-messages.css',
  shadow: true
})
export class AppMessages {
  render() {
    return (
      <div class="app-messages">
        <h2>Messages</h2>
        <stencil-router-switch>
            <stencil-route url="/:id" component="message-details" />
            <stencil-route component="message-list" />
        </stencil-router-switch>
      </div>
    );
  }
}
```
