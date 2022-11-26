DayZ Chernarus Krasno Airfield NEAF Custom Evac POI For Console and PC xml json Mod Instructions & Terms Of Use

Limited Testing on PC Chernarus Local Server & Xbox Nirado Server DAYZ Version 1.15 Nov 2021.

Created by @scalespeeder. Please report bugs & errors to scalespeeder@gmail.com with screenshots.

TERMS OF USE
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS
OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Using these modded xml / json files and instructions could break the functioning of your DAYZ server, requiring a reinstall that would wipe
all player progress.

Using these modded files neccessitates increased regular restarts to prevent server crashing.

It is suggested you thoroughly test your server after applying these files to ensure proper
functioning of your server.

I always recomend you validate your files at: https://www.xmlvalidation.com/ and https://jsonformatter.curiousconcept.com/

Instructions:

Click the "Code" button and "Download Zip" on the Github Repository and extract the files on your local PC for access.

Ensure your DayZ Server has activated the cfggameplay.json. For console users on Nitrado Servers, go to "General Settings" on your server and tick "Enable cfggameplay.json".

On PC Servers add the following line to your serverDZ.cfg:

enableCfgGameplayFile = 1;

(On some PC servers, including Nitrado, the serverDZ.cfg is "hidden", so you need to enable "expert mode" in settings,
then go to "expert settings", which is the serverDZ.cfg. Stop the server before making changes this way.)

Upload "neafevac.json" from the extracted files to inside the "custom" folder of the mission directory on your server. This file places the structures on your map.
(If you haven't got a "custom" folder, create one.)

Open the cfggameplay.json file and look for the "objectSpawnersArr" line.

This file tells your server to access your custom file.

Edit it to look like this: 

	"objectSpawnersArr": ["custom/neafevac.json"],
	
If you already are calling custom jsons to spawn items, seperate the files like this:

	"objectSpawnersArr": ["custom/neafevac.json,"custom/otherfile.json","custom/differentfile.json"],
	
Save your changes & upload if you need to.
	
Next we add loot to the structures by adding the following code snippet to the top of your mapgrouppos.xml file, after <map> 

	<group name="Land_Wreck_C130J" pos="12390.099609 145.043930 12407.900391" rpy="10.000000 0.000000 71.065910" a="18.93409" />
	<group name="Land_Wreck_Ikarus" pos="12388.700195 141.151016 12368.599609" rpy="-4.999999 0.000000 0.000000" a="90" />
	<group name="Land_Wreck_Lada_Red" pos="12401.885742 140.625809 12357.383789" rpy="-0.000000 -0.000000 -132.216751" a="-137.783249" />
	<group name="Land_Wreck_S1023_Blue" pos="12403.991211 140.975281 12353.405273" rpy="-0.000000 -0.000000 120.477470" a="-30.47747" />
	<group name="Land_Wreck_Volha_Blue" pos="12408.135742 140.627853 12351.487305" rpy="-0.000000 -0.000000 76.421211" a="13.578789" />
	<group name="Land_Wreck_Volha_Police" pos="12389.500977 140.617661 12381.939453" rpy="-0.000000 -0.000000 -36.409214" a="126.409214" />
	<group name="Land_Wreck_Volha_Police" pos="12394.616211 140.598190 12379.117188" rpy="-0.000000 -0.000000 82.992867" a="7.007133" />
	<group name="Land_Wreck_sed02_aban2_red" pos="12412.013672 140.491791 12349.364258" rpy="-0.000000 -0.000000 165.113495" a="-75.113495" />
	<group name="Land_Wreck_sed02_aban2_yellow" pos="12417.682617 140.479767 12350.207031" rpy="-0.000000 -0.000000 97.783035" a="-7.783035" />
	<group name="Land_Wreck_Ikarus" pos="12394.645508 141.184952 12357.510742" rpy="-4.999999 0.000000 -38.407074" a="128.407074" />
	<group name="Wreck_UH1Y" pos="12182.833008 141.813568 12637.925781" rpy="0.000000 -0.000000 -0.000000"a="90" />
	<group name="Land_Mil_Tent_Big1_1" pos="12123.044922 140.038696 12677.236328" rpy="0.000000 -0.000000 -0.000000" a="90" />
	<group name="Land_Mil_Tent_Big1_1" pos="12133.375977 140.012573 12673.356445" rpy="0.000000 -0.000000 -0.000000" a="90" />
	<group name="Land_Mil_Tent_Big1_1" pos="12143.750977 140.049042 12669.730469" rpy="0.000000 -0.000000 -0.000000" a="90" />
	<group name="Land_Mil_Tent_Big3" pos="12121.874023 141.081039 12660.271484" rpy="-0.000000 -0.000000 109.756859" a="-19.756859" />
	<group name="Land_Container_1Moh" pos="12133.468750 141.225037 12655.682617" rpy="-0.000000 -0.000000 19.591286" a="70.408714" />
	<group name="Land_Container_1Moh" pos="12139.664063 141.128708 12653.165039" rpy="-0.000000 -0.000000 158.008392" a="-68.008392" />
	
Save your changes & upload if you need to.
	
Next we add the infected that will spawn by the police cars and military tents. Open up your zombie_territories.xml file, which in inside the env directory.

Scroll down through the file until you find the section concerning infected police. Add the following line:

<zone name="InfectedPolice" smin="0" smax="0" dmin="3" dmax="5" x="12394.6162109375" z="12379.1171875" r="50"/>

Now scroll further until you find the military section and add this line:

<zone name="InfectedArmy" smin="0" smax="0" dmin="5" dmax="8" x="12121.9" z="12660.3" r="75"/>

Save your changes & upload if you need to.

Restart your server and the new structures will appear immediatly, and then they will slowly stock with loot.

Thanks, Rob.
