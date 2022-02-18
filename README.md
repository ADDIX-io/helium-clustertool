# helium-clustertool
A Node-Red flow, that plots the witnesses of witnesses of a given Helium-Hotspot to get clusters within the helium network.


Requirements:
- installed Node-Red

Plugins/Nodes:
- Node-red-dashboard
- Node-red-contrib-web-worldmap

Configuration:
- Create Dashboard Group and Node in config Dialog of a Dashboard Node
- Make sure all Dashboard nodes are added to it.

Go to the Dashboard of your NodeRed, it should look like this:

![Dashboard Clustertool](https://user-images.githubusercontent.com/62546625/154693847-fb735ea0-f762-4ebe-8d40-cf88fb16844d.png)

Insert a GWB58 Adress of a Hotspot and the radius (i.e. 150 km) that you want to inspect.

![Clustertool GWB58 and Range Input](https://user-images.githubusercontent.com/62546625/154695135-dc3d98ef-8498-4fb8-aace-28b51b14c265.png)

wait for the witnesses to show up. This takes a while... Hotspots, that get witnessed multiple times, will change their colour on the map. This flow will do 6 iterations (Witnesses of Witnesses). You can see the (total) number of Hotspots rising in the chart.
- if your chosen Hotspot doesn't have witnesses in the last 5 days available in the API, nothing will happen.

![Clustertool Output open](https://user-images.githubusercontent.com/62546625/154695274-4da7c647-4ec0-43da-a590-881446c546e9.png)

The Chart will reach a platoo before the last iteration if you found a cluster. If it doesn't reach a platoo the 6 iterations are not enough to get all hotspots within the network you are inspecting. The clusters we found (within a 150 km radius) reached a platoo within 4-5 iterations.

![Clustertool Output mark all](https://user-images.githubusercontent.com/62546625/154695838-d649444d-df88-4d05-bd74-1eeaf820c7b0.png)

Open the output button and mark the list of hotspots by tripple-clicking and copy it. THis is your result list.

![Clustertool zoomed in](https://user-images.githubusercontent.com/62546625/154696942-13201ba2-d20a-447b-beef-20124fd3f330.png)

Zoom in the map to see if the distribution of the hotspots are random / normal / as expected. Fake-Clusters often have unlikely distribution of hotspots.
