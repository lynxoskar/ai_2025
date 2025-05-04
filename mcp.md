Google maps MCP protocol

maps_geocode

Convert address to coordinates
Input: address (string)
Returns: location, formatted_address, place_id

maps_reverse_geocode

Convert coordinates to address
Inputs:
latitude (number)
longitude (number)
Returns: formatted_address, place_id, address_components
maps_search_places

Search for places using text query
Inputs:
query (string)
location (optional): { latitude: number, longitude: number }
radius (optional): number (meters, max 50000)
Returns: array of places with names, addresses, locations
maps_place_details

Get detailed information about a place
Input: place_id (string)
Returns: name, address, contact info, ratings, reviews, opening hours
maps_distance_matrix

Calculate distances and times between points
Inputs:
origins (string[])
destinations (string[])
mode (optional): "driving" | "walking" | "bicycling" | "transit"
Returns: distances and durations matrix
maps_elevation

Get elevation data for locations
Input: locations (array of {latitude, longitude})
Returns: elevation data for each point
maps_directions

Get directions between points
Inputs:
origin (string)
destination (string)
mode (optional): "driving" | "walking" | "bicycling" | "transit"
Returns: route details with steps, distance, duration