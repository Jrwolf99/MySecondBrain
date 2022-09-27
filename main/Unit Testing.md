---
tags:
- programming
---
# Unit Testing

Unit Tests are the easiest to write. 
You can expect specific results for your input. No dependencies or complex interactions. This is the black box testing. 

## Example
Consider this function which we use in our app. It will take name and age as inputs and return a greeting with these two parameters.

```javascript
const greeting = (firstName, lastName) => {
 return `Hello Mr./Mrs. ${firstName} ${lastName}`
}
```

A valuable unit test could be:

```javascript
test('should output firstName and lastName', () => {
 const text = greeting('Moataz', 'Mahmoud')
 expect(text).toBe('Hello Mr./Mrs. Moataz Mahmoud')
})
```

This test will check whether the _greeting_ function returns the expected text. If we now change the _greeting_ function, let’s say like this:

```javascript
const greeting = (firstName, lastName) => {
 return `Hello Mr./Mrs. ${firstName} ${firstName}`
}
```

Then our test will fail since it will return _Hello Mr./Mrs. Moataz Moataz_ instead of _Hello Mr./Mrs. Moataz Mahmoud_.


#### References
[Modus Create](https://moduscreate.com/blog/an-overview-of-unit-integration-and-e2e-testing/#:~:text=End%20to%20End%20Tests,that's%20loaded%20behind%20the%20scenes).)