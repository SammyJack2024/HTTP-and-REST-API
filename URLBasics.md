- URL are protocol-independent.

- URLs can use other protocols to communicate asides from HTTP, like fp, https etc.

- A URL (Uniform Resource Locator) is a general way to **locate a resource on a network**, no matter how it’s accessed.

- Structure: scheme://host:port/path
- ### Examples:

- `http://example.com` → uses HTTP
- `https://example.com` → uses HTTPS
- `ftp://example.com` → uses FTP
- `file://localfile.txt` → accesses local files

Note: Swift and React-Native are used for mobile application development.

This is a back request to get data from this URL using typescript.

const issueURL: string = 'https://api.boot.dev/v1/courses_rest_api/learn-http/issues'

const issues = await getData<Issue[]>(issueURL)

logIssues(issues)

async function getData<T>(url: string): Promise<T> {
  const apiKey = generateKey()
  const response = await fetch(url, {
    method: 'GET',
    mode: 'cors',
    headers: {
      'X-API-Key': apiKey,
      'Content-Type': 'application/json'
    }
  })
  return response.json()
}

---------------------------------------------------------------------------------------------

