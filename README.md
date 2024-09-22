# AOE - CURRENT MATCH SCRIPT
This code fetches information about the most recent Age of Empires 2 match played by a specific profile and summarizes it. 

    **Functions:**
        get_civilization_descriptions(file_path): This function reads a JSON file containing civilization information (likely names and descriptions) and returns a dictionary where the key is the civilization name and the value is its description.
        get_match_info(api_url, civilizations_file): This is the main function that retrieves and processes match data.
            It takes the API URL and the path to the civilization data file as input.
            It sends a request to the provided API to get match information for a specific profile.
            If the request is successful (status code 200), it parses the JSON response and extracts details of the most recent match, including map name, start time, and player information (names, ratings, and civilizations).
            It then calls the get_civilization_descriptions function to get descriptions for each player's civilization from the provided file.
            Finally, it returns a dictionary containing all the retrieved match information, including player details and civilization descriptions.

    **Main Script:**
        Defines the API URL to retrieve match data for profile ID 208269.
        Defines the path to the file containing civilization data (likely civilizations.json).
        Calls the get_match_info function with the API URL and civilization data file path.
        Converts the retrieved match start time from a timestamp format to a more readable date and time format.
        Checks if the get_match_info function returned any data (indicating a successful match retrieval).
            If there's match data:
                Prints the match date, map name, and detailed information about each player, including their name, rating, civilization, and civilization description.
            If no data is found (likely due to API request failure or missing players in the match data), it prints a message indicating no match information was found.
