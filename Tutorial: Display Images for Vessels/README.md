# Tutorial: Display images for Vessels

This tutorial is meant to demonstrate the feature in OpenAleph that allows a user to import a preview image based on the WikidataID of an object. 

First, use the `images.ipnb` notebook to create a CSV file with all the icebreaker vessels from Wikipedia.

Afterwards, edit the `icebreakers_wikipedia.yml` file, adding the path of your resulting CSV to: `csv_url: "file:///<PATH>/icebreakers.csv"`. 

Then, in your command line, run:
`ftm map icebreakers_wikipedia.yml -o icebreakers.entities`

In order to write these entities to OpenAleph, create an investigation (for exmaple, called "Icebreakers 🧊 🔨" ) and copy the foreign ID of this collection. Run the command:
`export ALEPH_HOST=<HOST>; export ALEPH_API_KEY=<API KEY; alephclient write-entities -i icebreakers.entities -f <foreign_id_of_collection>`

### Running OpenAleph locally

If you want to run this tutorial in your local OpenAleph instance, you need a running instance of [ftm-assets](https://github.com/dataresearchcenter/ftm-assets/). The [README](https://github.com/dataresearchcenter/ftm-assets/blob/main/README.md) contains command to run `ftm-assets` either on your development device or as a Docker container. 

Set the `FTM_ASSETS_URL` variable to point to the running `ftm-assets` instance, either in the docker-compose file:
```
api:
    build:
      context: .
    ...
    environment:
      ...
      FTM_ASSETS_URL: "http://localhost:8000/api"
...
```
or in your local environment, if you are not running OpenAleph using Docker containers. 
