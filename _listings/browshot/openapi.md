swagger: "2.0"
x-collection-name: Browshot
x-complete: 1
info:
  title: Browshot
  description: take-screenshots-of-any-website-in-real-time
  termsOfService: https://browshot.com/terms
  contact:
    name: API Support
    url: https://browshot.com/contact
    email: support@browshot.com
  version: 1.17.0
host: api.browshot.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /screenshot/multiple:
    get:
      summary: Request multiple screenshots
      description: |-
        Request multiple screenshots in one API call. The API call accepts all the parameters supported by screenshot/create.
        You can specify up to 10 URLs and 10 instances for a total of 100 screenshots in one API call.
      operationId: CreateMultipleScreenshots
      x-api-path-slug: screenshotmultiple-get
      parameters:
      - in: query
        name: cache
        description: use a previous screenshot (same URL, same instance) if it was
          done within  seconds
      - in: query
        name: cookie
        description: set a cookie for the URL requested (see Custom POST Data, Referer
          and Cookie) Cookies should be separated by a ; - paid screenshots only
      - in: query
        name: delay
        description: number of seconds to wait after the page has loaded
      - in: query
        name: details
        description: level of information available with screenshot/info
      - in: query
        name: flash_delay
        description: number of seconds to wait after the page has loaded if Flash
          elements are present
      - in: query
        name: headers
        description: any custom HTTP headers
      - in: query
        name: hosting
        description: hosting option - s3 or browshot
      - in: query
        name: hosting_bucket
        description: S3 bucket to upload the screenshot or thumbnail (required for
          S3)
      - in: query
        name: hosting_file
        description: file name to use (for S3 only)
      - in: query
        name: hosting_headers
        description: list of headers to add to the S3 object (for S3 only)
      - in: query
        name: hosting_height
        description: maximum height of the thumbnail to host
      - in: query
        name: hosting_scale
        description: scale of the thumbnail to host
      - in: query
        name: hosting_width
        description: maximum height of the thumbnail to host
      - in: query
        name: html
        description: saves the HTML of the rendered page which can be retrieved by
          the API call screenshot/html
      - in: query
        name: instance_id
        description: instance ID to use
      - in: query
        name: max_wait
        description: maximum number of seconds to wait before triggering the PageLoad
          event
      - in: query
        name: post_data
        description: send a POST requests with post_data, useful for filling out forms
          - paid screenshots only
      - in: query
        name: priority
        description: assign priority to the screenshot (for private instances only)
      - in: query
        name: referer
        description: use a custom referrer header - paid screenshots only
      - in: query
        name: screen_height
        description: height of the browser window
      - in: query
        name: screen_width
        description: width of the browser window
      - in: query
        name: script
        description: URL of javascript file to execute after the page load event
      - in: query
        name: size
        description: screenshot size - screen (default) or page
      - in: query
        name: url
        description: URL of the page to get a screenshot for
      responses:
        200:
          description: OK
      tags:
      - Screenshot
      - Multiple