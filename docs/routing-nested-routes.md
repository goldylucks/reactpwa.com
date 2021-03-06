---
id: nested-routes
title: Nested routes
sidebar_label: Nested routes
---

## Add Nested Routes
**Benefits of Nested Routing:** Rewrite sections of a page rather than loading entire new pages.  
You can add **nested routes** as follows:

```javascript
// ... other imports
import Blog from "./components/blog";
import NestedRouteDemo from "./components/nested-route-demo"
  // ... code
  // ... other routes
  {
    path: "/blog",
    abstract: true,
    component: Blog,
    routes: [
      {
        path: "/blog/nested-route-demo",
        exact: true,
        component: NestedRouteDemo
      }
    ]
  }
  // ... code
```

In `blog.js` add following code:
```javascript
import React, {Component} from "react";
import { renderRoutes } from "react-router-config";
export default class Blog extends Component {
  render() {
    return (
      <div>
        <!-- display common content in all sub-routes -->
        <h1>Blog</h1>
        <!--To render Sub-Routes -->
        <div>{renderRoutes(this.props.route.routes)}</div>
      </div>
    );
  }
}
```



<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-7586505628408924"
     data-ad-slot="5652642939"
     data-ad-format="auto"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>
