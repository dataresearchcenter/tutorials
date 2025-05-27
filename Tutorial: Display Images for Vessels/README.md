# Tutorial: Display images for Vessels

This tutorial is meant to demonstrate the feature in OpenAleph that allows a user to import a preview image based on the WikidataID of an object. 

First, use the `images.ipnb` notebook to create a CSV file with all the icebreaker vessels from Wikipedia.

Afterwards, edit the `icebreakers_wikipedia.yml` file, adding the path of your resulting CSV to: `csv_url: "file:///<PATH>/icebreakers.csv"`. 

Then, in your command line, run:
`ftm map icebreakers_wikipedia.yml -o icebreakers.entities`

In order to write these entities to OpenAleph, create an investigation (for exmaple, called "Icebreakers 🧊 🔨" ) and copy the foreign ID of this collection. Run the command:
`export ALEPH_HOST=<HOST>; export ALEPH_API_KEY=<API KEY; alephclient write-entities -i icebreakers.entities -f <foreign_id_of_collection>`
