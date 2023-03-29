## Data Statistics
| Cities | Counties | Districts | Neighborhoods |
| --- | --- | --- | --- |
| 81 | 973 | 2771 | 73305 |

## Data Structure
The `data.json` file contains a hierarchical of Turkey's administrative divisions, including cities, counties, districts, and neighborhoods.

### `Neighborhood`

Represents a neighborhood within a district.

| Field | Type | Description |
| --- | --- | --- |
| `name` | `string` | The name of the neighborhood. |
| `code` | `string` | A unique code for the neighborhood. |

### `District`

Represents a district within a county.

| Field | Type | Description |
| --- | --- | --- |
| `name` | `string` | The name of the district. |
| `neighborhoods` | `Neighborhood[]` | An array of neighborhoods within the district. |

### `County`

Represents a county within a city.

| Field | Type | Description |
| --- | --- | --- |
| `name` | `string` | The name of the county. |
| `districts` | `District[]` | An array of districts within the county. |

### `City`

Represents a city.

| Field | Type | Description |
| --- | --- | --- |
| `name` | `string` | The name of the city. |
| `counties` | `County[]` | An array of counties within the city. |

The `data.json` file contains an array of `City` objects, each of which contains an array of `County` objects, which in turn contain an array of `District` objects, and so on.

## Example Data

Here is an example of the data structure in `data.json`:

```json
{
    [
        {
            "name": "City A",
            "counties": [
                {
                    "name": "County A1",
                    "districts": [
                        {
                            "name": "District A1.1",
                            "neighborhoods": [
                                {
                                    "name": "Neighborhood A1.1.1",
                                    "code": "A1.1.1"
                                },
                                {
                                    "name": "Neighborhood A1.1.2",
                                    "code": "A1.1.2"
                                }
                            ]
                        },
                        {
                            "name": "District A1.2",
                            "neighborhoods": [
                                {
                                    "name": "Neighborhood A1.2.1",
                                    "code": "A1.2.1"
                                },
                                {
                                    "name": "Neighborhood A1.2.2",
                                    "code": "A1.2.2"
                                }
                            ]
                        }
                    ]
                },
                {
                    "name": "County A2",
                    "districts": [
                        {
                            "name": "District A2.1",
                            "neighborhoods": [
                                {
                                    "name": "Neighborhood A2.1.1",
                                    "code": "A2.1.1"
                                },
                                {
                                    "name": "Neighborhood A2.1.2",
                                    "code": "A2.1.2"
                                }
                            ]
                        },
                        {
                            "name": "District A2.2",
                            "neighborhoods": [
                                {
                                    "name": "Neighborhood A2.2.1",
                                    "code": "A2.2.1"
                                },
                                {
                                    "name": "Neighborhood A2.2.2",
                                    "code": "A2.2.2"
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
