authors: Yuki Tanabe
summary: Firebase Studio Hands-on
id: en
categories: firebase,javascript
environments: Web
status: Published
url: https://tanabee.github.io/firebase-studio-codelab/en/
feedback_link: https://github.com/tanabee/firebase-studio-codelab/issues

# Building a Full-Stack Application with Firebase Studio

## Intro
Duration: 0:02:00

In this hands-on tutorial, you will build a full-stack web application using Firebase Studio.

### What You'll Learn in This Codelab

- Basic usage of Firebase Studio
- Troubleshooting methods in Firebase Studio
- How to build a full-stack application using Firebase Studio
- How to integrate AI features into your application using Firebase Studio
- How to deploy an app created with Firebase Studio to a Firebase environment

### Final Output

You will develop a diary app with an AI proofreading feature as shown below. (Since generative AI is used, the exact output may vary.)

![Firebase Studio Final Output](./assets/firebase-studio-final-output.png)

The technology stack is as follows:

#### Technology Stack

- Hosting: Firebase App Hosting
- Database: Firestore
- Authentication: Firebase Authentication

### Prerequisites

- You have a Google account

## Getting Started with Firebase Studio
Duration: 0:10:00

Open [https://studio.firebase.google.com](https://studio.firebase.google.com/).

Enter a prompt like the following:

```
Please develop a diary app.
Add an AI proofreading feature that allows users to proofread their entries before saving.
Authentication and database connection are not needed at first; temporary storage in memory is sufficient.
```

![Firebase Studio First Prompt](./assets/firebase-studio-first-prompt.png)

After a while, the app blueprint will be generated. Customize any parts you'd like, then select "Prototype this App" to start generation.

![Firebase Studio Blue Print](./assets/firebase-studio-blue-print.png)

If you're asked for a Gemini API key, create one from the following site:

[https://aistudio.google.com/api-keys](https://aistudio.google.com/api-keys)

![Firebase Studio Gemini Api Key](./assets/firebase-studio-gemini-api-key.png)

The web application will be created.

![Firebase Studio First Output](./assets/firebase-studio-first-output.png)

## Troubleshooting
Duration: 0:03:00

### Resolving Errors

Here's how to resolve errors when they occur. You can check error details from the icon in the lower left corner.

If you open the error and see a `Fix Error` button, selecting it will proceed with fixing that error.
![Firebase Studio Fix Error Button](./assets/firebase-studio-fix-error-button.png)

If the `Fix Error` button is not displayed, simply copy and paste the error content.
![Firebase Studio Fix Error Copy And Paste](./assets/firebase-studio-fix-error-copy-and-paste.png)

### Restoring to a Previous State

If errors occur and cannot be fixed, it may be better to restore to a previous working state.

Checkpoints are created for each user message, so you can restore to a specific point by selecting the Restore button.
![Firebase Console Restore](./assets/firebase-studio-restore.png)

### Effective Prompts

If the generated results are not as expected, you can adjust your prompts by adding details or providing specific instructions. Refer to the official documentation [Refining prompts to improve response quality](https://firebase.google.com/docs/studio/prompting#refining-prompts) for guidance on making revision requests.

- **Add constraints**: Specify constraints regarding the UI, data model, or functionality.
- **Provide examples**: Show examples of how users will interact with the app and what data will be displayed.
- **Use keywords**: Use keywords to describe features that the LLM can associate with the required output class. For example, you can use Material Design in prompts to indicate that the app should comply with Google's design standards.
- **Request specific changes**: Request specific changes to the generated code or blueprint. Add each feature request in separate requests.
- **Ask the model to reason**: If you're having trouble getting the desired result, try asking the model to reason through the prompt. For example, you can request: "Think step by step. I want to create an input box for a task app. It needs to include an 'Add Task' button and a 'Cancel' button."

## Requesting Customizations
Duration: 0:03:00

Let's try requesting some simple customizations. Here are some examples:

- Change the colors used in the application
- Change the app name
- Modify specific text

### Changing the Colors Used in the Application

![Firebase Studio Before Change Color](./assets/firebase-studio-before-change-color.png)

![Firebase Studio After Change Color](./assets/firebase-studio-after-change-color.png)

### Modifying Specific Text

![Firebase Studio Before Change Text](./assets/firebase-studio-before-change-text.png)

![Firebase Studio After Change Text](./assets/firebase-studio-after-change-text.png)

## Adding Authentication and Database
Duration: 0:10:00

Send the following prompt to add authentication and database functionality:

```
Please add authentication and database connection with the following specifications:

- Authentication: Firebase Authentication
  - Email and password authentication
  - Features:
    - Sign up
    - Login
    - Logout
- Database: Firestore
  - Diary storage path: users/:userId/posts/:postId
```

Note: The [Firebase Studio official documentation](https://firebase.google.com/docs/studio/get-started-ai#iterate) states: "Tip: The app prototyping agent can add Cloud Firestore and Firebase Authentication to your app during the iteration phase, rather than in the initial app blueprint." Therefore, we add authentication and database connection at this point rather than in the initial prompt.

Sign up and post a diary entry to verify the functionality. Let's confirm that it's actually connected to Firebase Authentication and Firestore. First, select the orange-framed area in the image below to navigate to the Firebase Project.

![Firebase Studio - Open Firebase Console](./assets/firebase-studio-open-firebase-console.png)

In the Authentication menu, you can see that the signed-up user information has been added.

![Firebase Console Authentication](./assets/firebase-console-authentication.png)

In the Firestore menu, you can confirm that the posted diary content has been saved.

![Firebase Console Firestore](./assets/firebase-console-firestore.png)

## Deploying to Firebase Environment
Duration: 0:10:00

Deploying to a Firebase environment allows other users to use your app.

Press the Publish button.

![Firebase Console Publish](./assets/firebase-console-publish.png)

Link to Google Cloud Platform billing information. This is a required procedure to use Firebase App Hosting, but it can be used within the free tier up to a certain scale.

![Firebase Studio Link To GCP Billing](./assets/firebase-studio-link-to-gcp-billing.png)

Once deployment is successful, you can access the app from the generated URL.

![Firebase Studio Complete Deployment](./assets/firebase-studio-complete-deployment.png)

## Congrats!
Duration: 0:02:00

This concludes the hands-on tutorial. If you have extra time, try customizing further. Here are some customization examples:

- Display diary entries in a sidebar list
- Calendar view to access diary entries for specific dates
- Generate diary titles using generative AI
- Generate summaries for specific periods (weekly, monthly, etc.) using generative AI
- Control public/private visibility of diary entries
- Follow feature between users

For those who want to understand Firebase Studio more deeply, you can find more detailed information from the following links:

### Reference Links

- [Firebase Official Documentation](https://firebase.google.com/docs/studio)
- [Connect to Model Context Protocol (MCP) Servers](https://firebase.google.com/docs/studio/mcp-servers)
- [Get Started with Firebase Studio Templates](https://firebase.google.com/docs/studio/get-started-template?template_type=official)
- [Firebase Studio Pricing, Quotas, and Limits](https://firebase.google.com/docs/studio/pricing)
- [Upload Your App to GitHub](https://firebase.google.com/docs/studio/github)
- [Enhance Your Firebase Studio Workflow with Gemini CLI](https://firebase.blog/posts/2025/07/firebase-studio-gemini-cli/)
- [Bridge the design to development gap with Builder.io and Firebase Studio](https://firebase.blog/posts/2025/09/firebase-studio-builder-io-design-development)
