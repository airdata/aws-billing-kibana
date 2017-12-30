{
  "title": "finalVisualization_5days_30min_line_split",
  "type": "line",
  "params": {
    "addLegend": true,
    "addTimeMarker": true,
    "addTooltip": true,
    "defaultYExtents": true,
    "drawLinesBetweenPoints": true,
    "interpolate": "linear",
    "radiusRatio": "3",
    "scale": "linear",
    "setYExtents": false,
    "shareYAxis": true,
    "showCircles": true,
    "smoothLines": true,
    "times": [],
    "yAxis": {}
  },
  "aggs": [
    {
      "id": "1",
      "type": "sum",
      "schema": "metric",
      "params": {
        "field": "lineItem/UnblendedCost"
      }
    },
    {
      "id": "2",
      "type": "date_histogram",
      "schema": "segment",
      "params": {
        "field": "lineItem/UsageStartDate",
        "interval": "custom",
        "customInterval": "30m",
        "min_doc_count": 1,
        "extended_bounds": {}
      }
    },
    {
      "id": "3",
      "type": "significant_terms",
      "schema": "group",
      "params": {
        "field": "lineItem/ProductCode",
        "size": 10
      }
    }
  ],
  "listeners": {}
}