# jQuery to Vanilla JavaScript Methods

This project provides a comprehensive comparison of jQuery methods and their equivalent vanilla JavaScript implementations. This can be useful for developers looking to migrate from jQuery to plain JavaScript or for those who want to understand the underlying JavaScript behind common jQuery methods. This covers the conversion of jQuery methods to their vanilla JavaScript equivalents, organized by functionality categories for easy reference.


## Core

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `jQuery()`          | `document.querySelectorAll()`                                        |
| `$.holdReady()`     | N/A (jQuery-specific functionality)                                  |
| `$.noConflict()`    | N/A (jQuery-specific functionality)                                  |
| `$.ready()`         | `document.addEventListener('DOMContentLoaded', callback)`            |

## Selectors

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `$()`               | `document.querySelectorAll()`                                        |
| `$.expr`            | N/A (jQuery-specific functionality)                                  |

## Attributes

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.addClass()`       | `element.classList.add()`                                            |
| `.attr()`           | `element.setAttribute()` / `element.getAttribute()`                   |
| `.hasClass()`       | `element.classList.contains()`                                       |
| `.prop()`           | `element.propertyName` / `element.propertyName = value`              |
| `.removeAttr()`     | `element.removeAttribute()`                                          |
| `.removeClass()`    | `element.classList.remove()`                                         |
| `.removeProp()`     | `delete element.propertyName`                                        |
| `.toggleClass()`    | `element.classList.toggle()`                                         |
| `.val()`            | `element.value` / `element.value = value`                            |

## Traversing

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.add()`            | `new Set([...nodeList1, ...nodeList2])` (Using `Set` to merge NodeLists) |
| `.children()`       | `element.children`                                                  |
| `.closest()`        | `element.closest()`                                                 |
| `.contents()`       | `element.childNodes`                                                |
| `.each()`           | `nodeList.forEach()`                                                |
| `.end()`            | N/A (jQuery-specific chaining functionality)                        |
| `.eq()`             | `nodeList[index]`                                                   |
| `.filter()`         | `Array.prototype.filter.call(nodeList, callback)`                   |
| `.find()`           | `element.querySelectorAll()`                                        |
| `.first()`          | `nodeList[0]`                                                      |
| `.has()`            | `Array.prototype.some.call(nodeList, callback)`                     |
| `.is()`             | `element.matches()`                                                 |
| `.last()`           | `nodeList[nodeList.length - 1]`                                     |
| `.map()`            | `Array.prototype.map.call(nodeList, callback)`                      |
| `.next()`           | `element.nextElementSibling`                                        |
| `.nextAll()`        | `Array.from(element.nextElementSibling)` and loop using `nextElementSibling` |
| `.nextUntil()`      | Custom function to loop through siblings until a selector is matched |
| `.not()`            | `Array.prototype.filter.call(nodeList, callback)`                   |
| `.offsetParent()`   | `element.offsetParent`                                              |
| `.parent()`         | `element.parentElement`                                             |
| `.parents()`        | Custom function to collect all ancestors using `parentElement`      |
| `.parentsUntil()`   | Custom function to collect ancestors until a selector is matched    |
| `.prev()`           | `element.previousElementSibling`                                    |
| `.prevAll()`        | `Array.from(element.previousElementSibling)` and loop using `previousElementSibling` |
| `.prevUntil()`      | Custom function to loop through previous siblings until a selector is matched |
| `.siblings()`       | `Array.from(element.parentElement.children).filter(child => child !== element)` |
| `.slice()`          | `Array.prototype.slice.call(nodeList, start, end)`                  |

## Manipulation

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.after()`          | `element.insertAdjacentHTML('afterend', htmlString)`                 |
| `.append()`         | `element.appendChild()`                                              |
| `.appendTo()`       | `targetElement.appendChild(element)`                                 |
| `.before()`         | `element.insertAdjacentHTML('beforebegin', htmlString)`              |
| `.clone()`          | `element.cloneNode(true)`                                            |
| `.detach()`         | `element.parentElement.removeChild(element)`                         |
| `.empty()`          | `element.innerHTML = ''`                                             |
| `.html()`           | `element.innerHTML` / `element.innerHTML = htmlString`               |
| `.insertAfter()`    | `targetElement.insertAdjacentElement('afterend', element)`           |
| `.insertBefore()`   | `targetElement.insertAdjacentElement('beforebegin', element)`        |
| `.prepend()`        | `element.insertAdjacentHTML('afterbegin', htmlString)`               |
| `.prependTo()`      | `targetElement.insertAdjacentHTML('afterbegin', htmlString)`         |
| `.remove()`         | `element.remove()`                                                   |
| `.replaceAll()`     | `element.outerHTML = htmlString`                                     |
| `.replaceWith()`    | `element.outerHTML = htmlString`                                     |
| `.text()`           | `element.textContent` / `element.textContent = textString`           |
| `.unwrap()`         | Custom function to replace parent with its children                  |
| `.wrap()`           | Custom function to wrap element with another element                 |
| `.wrapAll()`        | Custom function to wrap all elements with a single parent element    |
| `.wrapInner()`      | `element.innerHTML = wrapperElement.outerHTML` and move original children into wrapper |

## CSS

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.css()`            | `element.style.propertyName` / `element.style.propertyName = value` |
| `.height()`         | `element.clientHeight`                                              |
| `.innerHeight()`    | `element.clientHeight`                                              |
| `.innerWidth()`     | `element.clientWidth`                                               |
| `.offset()`         | `element.getBoundingClientRect()`                                    |
| `.outerHeight()`    | `element.offsetHeight`                                              |
| `.outerWidth()`     | `element.offsetWidth`                                               |
| `.position()`       | `element.getBoundingClientRect()`                                    |
| `.scrollLeft()`     | `element.scrollLeft` / `element.scrollLeft = value`                  |
| `.scrollTop()`      | `element.scrollTop` / `element.scrollTop = value`                    |
| `.width()`          | `element.clientWidth`                                               |

## Events

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.bind()`           | `element.addEventListener()`                                         |
| `.blur()`           | `element.blur()`                                                    |
| `.change()`         | `element.change()`                                                  |
| `.click()`          | `element.click()`                                                   |
| `.contextmenu()`    | `element.addEventListener('contextmenu', callback)`                 |
| `.dblclick()`       | `element.addEventListener('dblclick', callback)`                    |
| `.delegate()`       | `parentElement.addEventListener(event, callback)` (using event delegation) |
| `.die()`            | `element.removeEventListener()`                                     |
| `.error()`          | `element.addEventListener('error', callback)`                       |
| `.focus()`          | `element.focus()`                                                   |
| `.focusin()`        | `element.addEventListener('focusin', callback)`                     |
| `.focusout()`       | `element.addEventListener('focusout', callback)`                    |
| `.hover()`          | `element.addEventListener('mouseenter', enterCallback)` and `element.addEventListener('mouseleave', leaveCallback)` |
| `.keydown()`        | `element.addEventListener('keydown', callback)`                     |
| `.keypress()`       | `element.addEventListener('keypress', callback)`                    |
| `.keyup()`          | `element.addEventListener('keyup', callback)`                       |
| `.live()`           | `document.addEventListener(event, callback)` (using event delegation) |
| `.load()`           | `element.addEventListener('load', callback)`                        |
| `.mousedown()`      | `element.addEventListener('mousedown', callback)`                   |
| `.mouseenter()`     | `element.addEventListener('mouseenter', callback)`                  |
| `.mouseleave()`     | `element.addEventListener('mouseleave', callback)`                  |
| `.mousemove()`      | `element.addEventListener('mousemove', callback)`                   |
| `.mouseout()`       | `element.addEventListener('mouseout', callback)`                    |
| `.mouseover()`      | `element.addEventListener('mouseover', callback)`                   |
| `.mouseup()`        | `element.addEventListener('mouseup', callback)`                     |
| `.off()`            | `element.removeEventListener()`                                     |
| `.on()`             | `element.addEventListener()`                                        |
| `.one()`            | `element.addEventListener(event, callback, { once: true })`        |
| `.ready()`          | `document.addEventListener('DOMContentLoaded', callback)`           |
| `.resize()`         | `window.addEventListener('resize', callback)`                       |
| `.scroll()`         | `element.addEventListener('scroll', callback)`                      |
| `.select()`         | `element.addEventListener('select', callback)`                      |
| `.submit()`         | `element.addEventListener('submit', callback)`                      |
| `.trigger()`        | `element.dispatchEvent(new Event(event))`                           |
| `.triggerHandler()` | `element.dispatchEvent(new Event(event, { bubbles: false }))`       |
| `.unbind()`         | `element.removeEventListener()`                                     |
| `.undelegate()`     | `parentElement.removeEventListener(event, callback)`               |
| `.unload()`         | `window.addEventListener('unload', callback)`                       |

## Effects

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.animate()`        | Use CSS transitions or the Web Animations API                       |
| `.clearQueue()`     | Custom function to handle animation queue                           |
| `.delay()`          | `setTimeout(callback, delay)`                                       |
| `.dequeue()`        | Custom function to handle animation queue                           |
| `.fadeIn()`         | `element.style.opacity = 0; element.style.transition = 'opacity 0.4s'; requestAnimationFrame(() => element.style.opacity = 1);` |
| `.fadeOut()`        | `element.style.opacity = 1; element.style.transition = 'opacity 0.4s'; requestAnimationFrame(() => element.style.opacity = 0);` |
| `.fadeTo()`         | `element.style.transition = 'opacity 0.4s'; element.style.opacity = opacityValue;` |
| `.fadeToggle()`     | `if (element.style.opacity === '1') { element.style.opacity = 0; } else { element.style.opacity = 1; }` |
| `.finish()`         | Custom function to complete all animations                          |
| `.hide()`           | `element.style.display = 'none'`                                    |
| `.queue()`          | Custom function to handle animation queue                           |
| `.show()`           | `element.style.display = ''` (or a specific display value like 'block') |
| `.slideDown()`      | `element.style.height = '0'; element.style.transition = 'height 0.4s'; requestAnimationFrame(() => element.style.height = 'auto');` |
| `.slideToggle()`    | `if (element.style.height === '0px') { element.style.height = 'auto'; } else { element.style.height = '0px'; }` |
| `.slideUp()`        | `element.style.height = 'auto'; element.style.transition = 'height 0.4s'; requestAnimationFrame(() => element.style.height = '0');` |
| `.stop()`           | Custom function to stop animations                                  |

## AJAX

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `$.ajax()`          | `fetch()`                                                           |
| `$.ajaxPrefilter()` | N/A (jQuery-specific functionality)                                  |
| `$.ajaxSetup()`     | N/A (jQuery-specific functionality)                                  |
| `$.ajaxTransport()` | N/A (jQuery-specific functionality)                                  |
| `$.get()`           | `fetch(url).then(response => response.text())`                      |
| `$.getJSON()`       | `fetch(url).then(response => response.json())`                      |
| `$.getScript()`     | `fetch(url).then(response => response.text()).then(script => eval(script))` |
| `$.param()`         | `new URLSearchParams(object).toString()`                            |
| `$.post()`          | `fetch(url, { method: 'POST', body: formData })`                    |
| `.ajaxComplete()`   | Custom function using `fetch()` and `then()`                        |
| `.ajaxError()`      | Custom function using `fetch()` and `catch()`                       |
| `.ajaxSend()`       | Custom function using `fetch()` with event listeners                |
| `.ajaxStart()`      | Custom function to handle the start of an AJAX request              |
| `.ajaxStop()`       | Custom function to handle the end of all AJAX requests              |
| `.ajaxSuccess()`    | Custom function using `fetch()` and `then()`                        |
| `.load()`           | `element.addEventListener('load', callback)`                        |
| `.serialize()`      | `new FormData(formElement).toString()`                              |
| `.serializeArray()` | `Array.from(new FormData(formElement)).map(([name, value]) => ({ name, value }))` |

## Utilities

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `$.boxModel`        | N/A (Outdated concept)                                               |
| `$.browser`         | `navigator.userAgent`                                               |
| `$.contains()`      | `parentElement.contains(childElement)`                              |
| `$.data()`          | `element.dataset`                                                   |
| `$.each()`          | `array.forEach()`                                                   |
| `$.extend()`        | `Object.assign(target, ...sources)`                                 |
| `$.fn.extend()`     | `Object.assign(target, ...sources)`                                 |
| `$.globalEval()`    | `eval(script)`                                                      |
| `$.grep()`          | `array.filter(callback)`                                            |
| `$.hasData()`       | Custom function to check for dataset properties                     |
| `$.holdReady()`     | N/A (jQuery-specific functionality)                                  |
| `$.inArray()`       | `array.includes(value)`                                             |
| `$.isArray()`       | `Array.isArray()`                                                   |
| `$.isEmptyObject()` | `Object.keys(object).length === 0`                                  |
| `$.isFunction()`    | `typeof function === 'function'`                                    |
| `$.isNumeric()`     | `!isNaN(parseFloat(value)) && isFinite(value)`                      |
| `$.isPlainObject()` | `object !== null && typeof object === 'object' && object.constructor === Object` |
| `$.isWindow()`      | `object !== null && object === object.window`                       |
| `$.isXMLDoc()`      | `object instanceof XMLDocument`                                     |
| `$.makeArray()`     | `Array.from(arrayLikeObject)`                                       |
| `$.map()`           | `array.map(callback)`                                               |
| `$.merge()`         | `array1.concat(array2)`                                             |
| `$.noConflict()`    | N/A (jQuery-specific functionality)                                  |
| `$.noop()`          | `() => {}`                                                          |
| `$.now()`           | `Date.now()`                                                        |
| `$.parseHTML()`     | `new DOMParser().parseFromString(htmlString, 'text/html').body.childNodes` |
| `$.parseJSON()`     | `JSON.parse()`                                                      |
| `$.parseXML()`      | `new DOMParser().parseFromString(xmlString, 'application/xml')`     |
| `$.proxy()`         | `callback.bind(context)`                                            |
| `$.queue()`         | Custom function to handle queues                                    |
| `$.removeData()`    | `delete element.dataset[key]`                                       |
| `$.sub()`           | N/A (jQuery-specific functionality)                                  |
| `$.support`         | Feature detection (Use Modernizr for detailed support)              |
| `$.trim()`          | `string.trim()`                                                     |
| `$.type()`          | `typeof value`                                                      |
| `$.unique()`        | `Array.from(new Set(array))`                                        |

## Plugins

| jQuery Method       | Equivalent JavaScript                                               |
|---------------------|----------------------------------------------------------------------|
| `.data()`           | `element.dataset`                                                   |
| `.each()`           | `nodeList.forEach()`                                                |
| `.extend()`         | `Object.assign(target, ...sources)`                                 |
| `.get()`            | `element.innerHTML` or `fetch(url)`                                 |
| `.index()`          | `Array.prototype.indexOf.call(nodeList, element)`                   |
| `.removeData()`     | `delete element.dataset[key]`                                       |
| `.toArray()`        | `Array.from(nodeList)`                                              |

Note: Some jQuery-specific functionalities, like `$.holdReady()`, `$.noConflict()`, `$.ajaxPrefilter()`, and `$.ajaxSetup()`, do not have direct vanilla JavaScript equivalents as they are specific to jQuery's internal workings. For these cases, custom implementations or alternative approaches would be necessary.
