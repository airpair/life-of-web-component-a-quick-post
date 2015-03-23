The meaning of life for any object is its **significance**, **origin**, **purpose** and **ultimate fate** is a central question in philosophy, religion and even in web technology. In other words every element in this world has its own significance, origin, purpose and destiny. To acquire the complete knowledge of any element we need to focus on these key points. Keeping this in mind let’s start to understand the life of web component. This post is a quick introduction of W3C web component and can help the developers to kick start their learning on web components.

## Significance of Web Component ##
The W3C web component specification provides a better way of web application development. There are many problems present that a web developer faces while developing a web application. Some of the problems are as follows:-
- While developing web pages we can find many components with similar semantic structure. These things lead to huge amount of redundant code. This increases the complexity of managing these components.	
- While developing web page we use many 3rd party components. We use ID, CLASSES and ATTRIBUTES for differentiating among these components and sometime we need to use IFRAME to provide a private scope to the component. There are many issues in IFRAME rendering like implementing responsive width of the content.

To address these problems W3C web component specification come for rescue with different features like **template**, **shadow DOM**, **HTML Imports** and **custom elements**.
## Origin of Web Component ##
Prior to web component specification we have used plugins created using different libraries like **Jquery**, **YUI**, and **DOJO** etc. We have treated these plugins as web component. These plugins have perfectly mimicked the properties of web component. However all these plugin need an additional base javascript library to be loaded prior to their execution. The following diagram shows the way we are heading on web component development.
![Web Component image](http://i.imgur.com/gdiHOq6.png)
 
Plugins have created an additional layer of execution. In simple words Plugins are **foreign entities** and their **origin** is not from the browser. We need a web component which will be native to the browser. As we know anything developed in a **native** language has an advantage in performance. Considering these points W3C came with a new specification which suggest a web application can be developed using the features listed in it.

If we look into the frameworks that are exists for W3C web component specification have an additional layer of polyfill. For example in Google’s **Polymer** library has the **webcomponent.js** dependency script. However it is just a temporary library that will be removed in near future when the browsers will start supporting web component specification natively.
## Purpose of Web Component ##
W3C Web Component is a collection of specification and each specification has its own purpose and addresses the issues existing in the current approach of web application development. These specifications are as follows:
- **Custom Element:** This specification empowers the developer to create their own elements. The purpose of this specification is to create more readable, declarative and meaningful code.	
- **Template:** This specification empowers the developer to create a reusable fragment of HTML that can be injected dynamically using javascript. The purpose of this specification is to create a light weight DOM tree.
- **Shadow DOM:** This specification empowers the developer to create abstraction that helps in separating complexity from the markup. The purpose of this specification is to create private scope for the component.
- **HTML Imports:** This specification empowers the developer to include HTML document to another HTML document. The purpose of this specification is to create a better packaging for the component.

## Ultimate Fate of Web Component ##
At present the Web Component specification is not completely implemented. In the coming years all these browser are going to support these specification. ECMA script 6 and 7 are already in discussion in developer communities and definitely has an impact to W3C web component specification or vice versa. Keep your finger crossed.

## Conclusion ##
From this post we have learnt the life of web component. We have now understood how a web component fits in to the current state of web application development.

