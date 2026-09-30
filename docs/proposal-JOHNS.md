Team name: Johns

Team members: Ryan Johns

# Introduction

For my term project, I’m building a web application that helps estimate the amount of Cat6 Ethernet cable needed for a network installation and calculates the best path to route those cables. When setting up a network in a home or office building, figuring out how much cable to buy and where to run it is usually done by hand, which often leads to underestimating lengths, wasting materials, or accidentally making cable runs that are too long to work properly. This app aims to automate that process by giving users a visual tool to map out their cable runs before doing any physical installation.



Users will be able to upload a floor plan image, set a scale for measurement, and place components like patch panels and wall outlets. The application will then automatically calculate the shortest and most practical route for each cable run along designated pathways like conduits or drop ceilings. Crucially, the system will apply real-world networking rules—such as accounting for vertical ceiling drops, adding extra slack for terminations, and flagging any cable run that exceeds the standard 90-meter limit for Cat6 permanent links.

# Anticipated Technologies

\*Frontend (What you see): React and HTML5 Canvas. This lets you upload a picture of a floor plan, draw lines for cable paths, click to place outlets, and see the route drawn on the screen.



\*Backend (Behind the scenes): Node.js or Python. This runs the math that calculates exact cable distances and figures out the best path.



\*Pathfinder Algorithm: Dijkstra’s Algorithm or A\*. These are search algorithms (like Google Maps for cables) that find the shortest route from point A to point B while avoiding wall obstacles.



\*Database: SQLite or a simple JSON file. A simple setup to save your floor plans, drawn paths, and project settings.

# Method/Approach

\*Upload \& Set Scale: Create a tool where you upload a floor plan image and draw a line over a known wall (e.g., a 10-foot wall) so the app knows how many pixels equal one foot.



\*Draw Paths: Let users click and draw lines showing where cables are actually allowed to go (like hallways or ceiling spaces). The app converts these lines into a map grid.



\*Run the Pathfinder: Use the routing algorithm to calculate the shortest path along the drawn lines from the main server rack to each room's outlet box.



\*Add Extra Cable \& Rules: Program the app to automatically add extra cable length for floor-to-ceiling drops, extra slack for plugging things in, and a 5–10% safety margin. If any cable goes over 90 meters (the max limit for Cat6), flag it red with a warning.

# Estimated Timeline

\*Phase 1: Basic Canvas \& Scale Tool



\*\*Get the project set up, build the main page, and make the tool that lets you upload an image and measure scale.



\*Phase 2: Path Drawing \& Routing Engine



\*\*Build the tools to draw cable paths on the screen and code the backend algorithm that calculates the routes.



\*Phase 3: Cable Rules \& Warnings



\*\*Add the math for extra ceiling height, slack, safety margins, and the 90-meter distance limit warning.



\*Phase 4: Totals Summary \& Cleanup



\*\*Build a final summary screen showing total feet of cable and how many 1,000 ft cable boxes to buy, fix bugs, and wrap up the presentation.

# Anticipated Problems

\*Converting 2D Pictures to Real 3D Lengths: A floor plan is flat, but cables go up into ceilings and down into walls. Getting the extra vertical height math right will take careful setup.



\*App Slowdowns on Huge Floor Plans: If a floor plan map gets way too large or complicated, running the algorithm over and over might lag the screen. The path grid needs to stay simple.



\*Making the Paths Realistic: The algorithm might try to make tight, sharp turns that ruin real Ethernet cables. Tweaking the logic to force wider, more practical turns will take some testing.

