
# **[TF2] Auto Pumpkins**
#### Current Version: 2.2.2

## Description:
Spawn and save pumpkin locations! They will be restored at the start of each round just like Harvest.  Pumpkin locations are saved per-map, so don't worry about pumpkins on dustbowl showing up in 2fort.

## Commands:
-   **sm_spawnpumpkin**  - Spawns a pumpkin and saves it's location to the database. Pumpkin spawns where you stand.
    Power and Angle are optional, and will use the default values that can be set in a cvar below.
-   **sm_deletepumpkin**  - Disables the pumpkin you're looking at in the database.

## Cvars:
-   **sm_pumpkin_version** Plugin Version
-   **sm_pumpkin_respawntime "20" -** How fast pumpkins respawn. -1 = pumpkins only respawn at round start.


## Install Instructions:
1.  Place  **AutoPumpkins****.smx**  into your addons/sourcemod/plugins/ folder.
2. Update your database.cfg file:

        "autopumpkins"
		{
	        "driver" "mysql"
	        "host" "webserver IP"
	        "database" "database name"
	        "user" "database username"
	        "pass" "database username password"
	        //"timeout" "0"
	        "port" "3306"
	    }

## Notes:
Command's access level is ROOT.  
Have your servers share a database to sync pumpkins across multiple servers.  

When first spawning a pumpkin, it will be non-solid to prevent you getting stuck. When they are spawned at the start of the round they will be solid as normal.  

**Plugin requires SDKHooks and as such will not compile on the forums!  
Use the pre-compiled .smx or compile it yourself locally!**

## Version History:

-   **v1.0.0**
    -   Initial Release
-   **v1.1.1**
    -   Plugin now escapes map filenames before inserting them into the database.
    -   Pumpkins now spawn with a random rotation so they don't always point "north".
-   **v2.0.0**
    -   Minor code cleanup
    -   Plugin now uses a threaded SQL connection
    -   Pumpkins now respawn after they explode (cvar sm_pumpkin_respawntime)
    -   **Plugin now requires SDKHooks**!
-   **v2.0.1**
    -   Fixed a typo in a log message.
-   **v2.0.2**
    -   sm_pumpkin_respawntime -1 now works as intended.
-   **v2.2.2**
    -   A little more code cleanup
    -   Updated a sql query left from before v2.0 that was not threaded to be threaded (Plugin is now fully threaded).
