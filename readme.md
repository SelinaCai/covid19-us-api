![](https://github.com/energee/covid19-us-api/workflows/.github/workflows/main.yml/badge.svg)

Transforms data from https://github.com/nytimes/covid-19-data into json. Available at https://energ.ee/covid19-us-api/states.json.

The json contains the number of COVID-19 confirmed cases and deaths for every state starting on January 21st. Note: there no entries for states on days that have 0 confirmed or dead:

```
"Washington": {
  "2020-01-21": {
    "date": "2020-01-21",
    "confirmed": "1",
    "deaths": "0"
  },
  "2020-01-22": {
    "date": "2020-01-22",
    "confirmed": "1",
    "deaths": "0"
  },
  ```

**Example:**
```
fetch("https://energ.ee/covid19-us-api/states.json")
  .then(response => response.json())
  .then(data => {
    data["Pennsylvania"].forEach(({ date, confirmed, deaths }) =>
      console.log(`${date} active cases: ${confirmed} deaths: ${deaths}`)
    );
  });
```
