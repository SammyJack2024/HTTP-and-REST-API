Exercise 3

import { Issue } from "./types";

const testURL = "http://why.wont.it.fetch";

const issueURL: string =
  "https://api.boot.dev/v1/courses_rest_api/learn-http/issues";

const issues = await getData<Issue[]>(testURL);

logIssues(issues);

// don't touch below this line

async function getData<T>(url: string): Promise<T> {
  const apiKey = generateKey();
  const response = await fetch(url, {
    method: "GET",
    mode: "cors",
    headers: {
      "X-API-Key": apiKey,
      "Content-Type": "application/json",
    },
  });
  return response.json();
}

// async → This means the function works with asynchronous operations (like network requests).
<T> (Generic Type) → This lets you decide the type of data the function will return.
url: string → The function takes a URL as input.
Promise<T> → It returns a promise that resolves to type T.

👉 In simple terms:
“This function fetches data from a URL and returns it in whatever type you expect.”

function generateKey(): string {
  const characters = "ABCDEF0123456789";
  let result = "";
  for (let i = 0; i < 16; i++) {
    result += characters.charAt(Math.floor(Math.random() * characters.length));
  }
  return result;
}

function logIssues(issues: Issue[]): void {
  for (const issue of issues) {
    console.log(issue.title);

There is an error in this code. Figure it out and correct it.

Answer

The Fix
You need to change the variable you are passing into getData. Instead of using testURL, you should use issueURL, which contains the actual API link for Boot.dev.

Change this line:

TypeScript
const issues = await getData<Issue[]>(testURL);
To this:

TypeScript
const issues = await getData<Issue[]>(issueURL);

Why this was breaking:
The Wrong Map: testURL is set to "http://why.wont.it.fetch". Since that isn't a real website, the fetch command inside your helper function will fail because it can't find the server.

The Correct Map: issueURL is set to the real address: "https://api.boot.dev/v1/courses_rest_api/learn-http/issues". This is where the "toy box" full of issues actually is!





  }
}
