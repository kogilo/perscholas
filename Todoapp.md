# Lesson Part Two

Hello, everyone.

In this video, part two of this lesson, we're picking up right where we left off.

So we're still working on the update or edit feature for an item, and we've already set things up so that when you click on the edit button, you can type in new text.

Hello there.

And we are successfully receiving that value within our Node server.

So now our goal for this video is to write Node code to actually talk to our MongoDB database and update the correct document with that new value.

So without further ado, let's get started on that. From within your `server.js` file, I want you to scroll down to the very bottom. This is where we set up our express server to receive that incoming post request to the URL of update item. 

And then just as a test, we were logging that value to the console. But what we actually want to do here is communicate with our MongoDB database.

So let's do this, let's delete that `console.log` line and also delete this `response.send` line. Let's just give ourselves a clean, empty slate within the body of this function.

All right.

And then type this out with me:

```javascript
// DB because we want to begin working with our database.
db.collection('items').findOneAndUpdate(
  a, // First argument to find one document
  {
    $set: {
      text: req.body.text
    }
  }
)
await
res.send('Success')
