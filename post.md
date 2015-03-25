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
- **Custom Element:** This specification empowers the developer to create their own elements.	
- **Template:** This specification empowers the developer to create a reusable fragment of HTML that can be injected dynamically using javascript.
- **Shadow DOM:** This specification empowers the developer to create abstraction that helps in separating complexity from the markup. 
- **HTML Imports:** This specification empowers the developer to include HTML document to another HTML document.

### Understanding Custom Element ###
 The purpose of this specification is to create more readable, declarative and meaningful code.We can create a HTML like custom element.The custom element can defined using **registerElement()** method.The syntax of creating a custom element is as follows:

    var MyComponent = document.registerElement('my-component');
After registering a custom element we can use it in the web application by including following markup.

    <my-component></my-component>
A custom element can be **inherited** from another element using **extend**  and **prototype** keyword.The syntax for inhering a element is declared as follows:

    var myComponent = document.registerElement('my-component', {
      extends: 'button',
      prototype: Object.create(HTMLButtonElement.prototype)
    });

In the previous code a custom element name **my-component** is defined using **registerElement(**) method.The **my-component** element is extended from the button HTML element.The prototype of the **my-component** is of type **HTMLButtonElement**.

### Understanding Template ###
 The purpose of this specification is to create a light weight DOM tree.The HTML markup defined inside a template are **inert** in nature.In simple word template contents are not part of **DOM** until it is **activated**.The syntax for defining a template is as follows:

    <template>
    	<!-- HTML Markup goes here -->
    </template>

### Understanding Shadow DOM ###
The purpose of this specification is to create private scope for the component.A shadow DOM can be created using createShadowRoot() method.The syntax for creating a shadow DOM is as follows:

    <div id="myElement"></div>
    <script>
    var anElement= document.getElementById("myElement");
    var root = anElement.createShadowRoot();
    </script>

The details of the previous code are as follows:
- **Host Element:** A **shadowRoot** is created for the DIV element with id **myElement**.The **myElement** is called as **Host Element**.
- **Shadow Tree:** The HTML DOM tree present inside the **shadowRoot** element is called as **shadow Tree**.
- **Shadow Root:** The **root** element of the shadow tree is called as **Shadow Root**.

### Understanding HTML Imports ###
 The purpose of this specification is to create a better packaging for the component.The syntax for including a HTML document using import is as follows:

    <link rel="import" href="fileName.html">

In the above syntax a link element is defined pointing to the **
** file.The link element has a attribute named **rel** with value **import**.The **rel** attribute with **import** value indicates the browser that it is a include of a another HTML document.

### Updated Document Tree ###
Inclusion of shadow DOM concept to the HTML DOM tree makes the document as **tree of trees**.The following diagram shows a conceptual view of the document tree with the shadow sub trees.

![DOM tree](http://i.imgur.com/gNVm0Dt.png)

## Ultimate Fate of Web Component ##
At present the Web Component specification is not completely implemented. In the coming years all these browser are going to support these specification.We can check the browser support of the web component specification using **Can I Use?** online tool.The current state of support to the web component for different browser are as follows:

- **Custom Element Support:**The following screenshot is taken from Can I Use? online tool and it clearly indicates the Firefox browsers does not support custom element specification at present.However we can enable the experimental web component flag in Firefox to use the custom elements.

![can i use custom element](http://i.imgur.com/90mXHb8.png)

- **Template Support:**The following screenshot shows the support of HTML template element in the current state of browsers.

![can i use template](http://i.imgur.com/Tlr24oW.png)

- **Shadow DOM Support:**The following screenshot shows the support of Shadow DOM in the current state of browsers.

![can i use Shadow DOM](http://i.imgur.com/8595vym.png)

- **HTML Import Support:**The following screenshot shows the support of HTML Import in the current state of browsers.

![can i use HTML Import](http://i.imgur.com/cEA58e6.png)

 ECMA script 6 and 7 are already in discussion in developer communities and definitely has an impact to W3C web component specification or vice versa. Keep your finger crossed.

## Developing Web Component ##
If you read upto this point we have learnt enough literature, Lets develop a web component for our self.I have used Chrome browser for developing a custom element named **italic-text** with a **title** attribute.The **steps** for developing **italic-text** element are as follows:

### Step 1: Defining a template for italic-text element ###
In this step we have created HTML template that will be used by **italic-text** element.The following code shows the template used by the **italic-text** element.

    <template id="italicTemplate">
	    <style>
	    	:host::shadow i {
	    		font-size:20px;
	    	}
	    </style>
	    <i>
			<!--Text Placeholder -->
		</i>
    </template>

In the above code a **italic element(i)** is used as placeholder to render the text in between.The style element contains a **font size** of **20px** for italic element.You can find 2 new keywords **:host** and **::shadow** to apply CSS style to italic element.The details of this CSS keywords are as follows:

- **:host**: It represent the custom element itself.For our example it is **italic-text** custom element.

- **::Shadow**: It represents the shadow tree of the host element.In our example the **italic element(i)** is present inside the shadow DOM tree we have used **:host::shadow i** css string to apply font size to **20px**.

### Step 2: Defining & Registering template italic-text element ###
In this step we will create script for defining object prototype and register an element to the DOM.The following code shows the detailed javascript for implementing **italic-text** element.


		(function() {
	        var selfDocument = document.currentScript.ownerDocument,
	            objectPrototype = Object.create(HTMLElement.prototype);
	        Object.defineProperty(objectPrototype, 'title', {
	            writable : true
	        });
	        objectPrototype.createdCallback = function() {
	            var shadow = this.createShadowRoot(),
	                templateContent = selfDocument.querySelector('#italicTemplate').content,
	                templateNodes = document.importNode(templateContent, true),
	                italicElement = templateNodes.querySelector("i");
	            italicElement.innerText = this.title;
	            shadow.appendChild(templateNodes);
	        };
	        var digitalClockElement = document.registerElement("italic-text", {
	            prototype: objectPrototype
	        });
    	})();

The **details** of the previous code are as follows:

- A object prototype is created using **Object.create()** method with **HTMLElement.prototype**.

- A title attribute is created using **Object.definePrototype()** method.

- In the **createdCallback()** lifecycle method template markup is activated using **importNode()** method and the value of **title** attribute is set using **innerText** attribute.

- Once the definition and declaration is ready the **italic-text** custom element is then registered using using **registerElement()** method.
 
### Step 3:Importing Using Custom Element italic-text ###
Now it is time to use **italic-text** in a web page.The following code shows the HTML markup which uses HTML import specification using **link** element and **rel** attribute with **import** value.

	<!DOCTYPE html>
	<html>
		<head lang="en">
			<meta charset="UTF-8">
			<title>Web component : Custom text Elements</title>
			<link rel="import" href="italicText.html">
		</head>
		<body>
			<italic-text title="Sandeep Kumar Patel">
			</italic-text>
		</body>
	</html>

The output of the previous code looks like following screenshot.We can see the custom element and shadow DOM of **italic-text** in the **Chrome** developer console.

![italic text element](http://i.imgur.com/3ZwnHt7.png)

The **italic-text** custom element demo can be found in the following **JSBIN** link:

[http://jsbin.com/yeheki/1/edit?html,js,output](http://jsbin.com/yeheki/1/edit?html,js,output "JSBIN demo link")

## Conclusion ##
From this post we have learnt the life of web component. We have now understood how a web component fits in to the current state of web application development.