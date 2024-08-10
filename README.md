# custom-google-keep
Google Keep is an unassuming note taking app from Google.
It’s simplicity and the fact that it just works, is the reason it’s been on every smartphone I’ve ever used, and that I use the web version regularly. I know that my notes will be accessible wherever I use my Google account.

The Challenge - Building Your Own Version Of Google Keep

For this challenge you’re going to build a clone of what I regard as the killer functionality of Google Keep - being a simple to use distributed note taking tool with a mobile and web UI.

Here’s what it looks like on my iPhone:

![img1](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F78ce435d-5d0d-4a04-8526-936fdfd43c85_1170x2532.png)

I love the simplicity and knowing that the notes I create on my laptop will be there on my phone when I’m away from the laptop and vice versa.

Step Zero

Coding Challenges is zero-indexed like all good programming languages! For this step you’re going to set your environment up, ready to begin developing and testing your solution.

You’re going to be building a backend service, which will need some persistent data store. You’ll also want to build a frontend that uses the backend.

You could of course build it all in one application, say as a CLI tool, but I’m suggesting you build it with separate frontend and backend components so you can experiment with building an API - it’s an opportunity to learn RESTful APIs if you’ve never done it. Or if you’ve done plenty of REST perhaps experiment with gRPC or GraphQL. Have fun learning something new is the safe space that is Coding Challenges!

I’ll leave you to setup your IDE / editor of choice and programming language of choice.

Step 1

In this step your goal is to create the API endpoint to be able to add a new note. For this challenge a note consists of:

Title
Note Content
Make sure that your API allows a new note to be created and that the note is saved to some persistent storage. You could simple save the notes to disk or you could use some form of database.

Consider carefully the trade-offs. Disk is fine for a personal application with a single user, even a few hundred users if done with care. If you wanted to be able to support the scale of Google Keep, some form of database will be required with thought given to how it scales.

At this stage it would also be great to build some test automation and a set of tests that check both the happy path and error conditions.

Step 2

In this step your goal is to create an API endpoint to be able to view a single note. Depending on your approach you might like to combined this with Step 3.

Don’t forget to consider how you uniquely identify a note.

Step 3

In this step your goal is to create an API endpoint to be able to fetch a list of notes.

At this point, if you haven’t already thought of it, you really should consider authentication. Notes are specific to a user and contain potentially private information. If you didn’t think to include it already, don’t worry you’re not alone, we’ve all gotten several steps into building an API at some point in our careers before remembering that authentication is important.

For this challenge consider using social login and read about the pros and cons of doing so. It’s useful to know.

Step 4

In this step your goal is to create one or more UIs to list and view notes. Google Keep provides a simple view of your notes, as though they are a collection of sticky notes. On mobile it looks like this:

![img2](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F09a45f37-d747-4c7f-a84e-367d09403765_1170x2532.png)

The web UI is fairly similar.

Step 5

In this step your goal is to create one or more UIs to add and list notes. You should provide a button to add a new note, the UI to allow the entry of the note and a call to the backend API to store the note.

Consider how the UI should handle things if the backend call fails and the different reasons it could fail for. Some will be permanent failures requiring a user action, others may be transient, and can be handled in the background by your UI.

Step 6

In this step your goal is to extend your UIs to allow editing of a note. You should add a UI that provides a way to select a note and edit it. In the case of Google Keep, just clicking on a note takes you to the editor and the changes are saved on exit.

As part of this step you will need to add or change an API endpoint to update a note. Be sure to include some tests and to validate the data sent to the endpoint.

Going Further

If you’ve got this far, you’ve built a simple clone all the bits of Google Keep that I use. If you fancy taking things further here are some extension ideas.

If you haven’t already, add a second UI - ie if you did web, add mobile.
Add the ability to record and save voice notes.
Add searching through the notes
Add the ability to ordering and pin notes in the UI(s).
