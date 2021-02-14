# Beeks Technical Test

## Design
- Toggleable content is hidden by default
- Provided URL was used - `wss://www.bitmex.com/realtime?subscribe=trade:XBTUSD,liquidation:XBTUSD`
- No error handling is provided for the WebSocket connection
- I used the WebSocket API provided by the browser. I haven't worked with websockets before, but for the sake of this project it didn't seem worth introducing and learning another lib
- The data is kept for a 60 second rolling window
- Toggling the visibility of the chart does not effect the subscription to the API
- I have tried to keep things related to the API in `bitmexApi` file
- Likewise, things specific to the graph live in the `Chart` file
- I tried to treat the data as if we were dealing with a large volume, hence using for loops instead of a more functional approach (`forEach`, `map`, `filter` etc.).

## Setbacks
- I faced some serious usability issues with stackblitz. It was reporting false type errors. Refreshing the page fixed it. I lost all faith in it as a platform! It took me a long time to rule out coding errors
- The Bitmex API _is_ rate limited! This caused me issues early on. See https://www.bitmex.com/app/wsAPI#Rate-Limits
- I do not know what "liquidation" means, so I have ignored this aspect
- The git integration on stackblitz is poor - I'm used to doing experiments on branches, so I found this quite limiting
- I prefer IntelliJ to VSCode (and embedded versions)
- Couldn't figure out how to set Highcharts themes
- Exporting the project to develop locally was a pain - I didn't successfully manage this. There is a lot of config missing in the exported zip - you can't just download and run it

## Observations
- The max & min lines are sometimes not visible at the bottom of the graph
- I am not convinced this is the correct kind of graph to use
- The `size` series is particularly difficult to see
- I have added comments throughout the code with thoughts. I would not typically do this in a production codebase

## Project URLs
- https://github.com/RAM92/beeks-tech-test-v4
- https://beeks-tech-test-v4.stackblitz.io
- https://stackblitz.com/edit/beeks-tech-test-v4?file=README.md