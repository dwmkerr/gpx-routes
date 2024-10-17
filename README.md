# gpx-routes

GPX routes for hiking, running, scrambling and so on. Very much a work in progress.

## Routes

TODO

## Route Developer Guide

This is the process I currently follow to build routes. It is still work in progress, and elements of it I may end up automating or building a command-line tool to simplify.

**Create the initial route in OS Maps**

First I use OS Maps to create the basic route. If you have a premium account you can use 'snap to path'.

_Note: It seems that with updates on the way to Garmin Explore, this step might be possible in the Garmin Explore website. Previously snapping was poor and maps were poor, but it looks like they're moving to TopoActive._

The route is then exported to GPX and stored in the `/routes/01-working` folder, with a name ending in `-osmaps.gpx`.

**Clean up waypoints in Garmin Connect**

The working route is then loaded into the [Garmin Connect](https://connect.garmin.com) website. For some reason all waypoints from OSMaps are shown as course points. I manually remove all of these course points and any waypoints that are remaining.

_Note: this step could be automated with a simple CLI tool._

**Add Course Points**

Now I add course points. As [Garmin does not show peak names (bug)](https://forums.garmin.com/outdoor-recreation/outdoor-recreation/f/epix-2/353378/peak-summit-names-not-displayed-on-the-maps/1848086#1848086) I add the summits that are on the route as Course Points. I typically add a few more course points as well to add some interest to the route, such as overlooks of tarns and so on. Note that [Talky Toaster seems to show peak names](https://talkytoaster.me.uk/latest-style-changes-and-map-improvements/).

For scrambles or mountaineering routes, I also add 'Steep Ascent' course points to indicate the start of a rock climbing / scrambling section.

This route is then saved to the `./routes/01-working` folder, with a name ending in `-garmin.gpx`.

**Test the route, add points of interest**

Now I'll walk/run/scramble the route. On the way if I discover the start of a climb or something similar is wrong, I'll save a location and note down the saved location name so that I can fix up the route later. If there are other interesting features, such as a hidden tarn or great lunch spot I'll save them too.

**Add points of interest to course**

_Note: this step is still work in progress, I'm not 100% happy with it._

Now I need to add the points of interest back to the course. I load the route in [GPX Studio](https://gpx.studio) and manually add new course points with the GPS coordinates from the saved locations.

The saved locations are then deleted, as most of them are 'course specific' (e.g. I don't need to know about the base of a scramble route if I'm just in the vicinity and doing something else, although I may keep a picnic spot or similar locations saved).

**Share the final course**

_Note: I have not got to this  step yet.**

At this point, the final course can be moved into a new location and marked as 'done' and shared with others.
