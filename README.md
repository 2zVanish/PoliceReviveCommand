# Police Revive and Teleport Script for FiveM

This script allows police officers in your FiveM server to revive and teleport a specified dead player to the police department. The player ID of the deceased player needs to be provided as an argument.

## Installation

1. Ensure you have the [FiveM](https://fivem.net/) client installed on your system.
2. Copy the `PoliceReviveCommand` file into your FiveM resources folder.
3. Add `start PoliceReviveCommand` to your `server.cfg` file to ensure the script is started when your server launches.

## Usage

- To revive and teleport a dead player, police officers can use the command `/gotopd [PlayerID]` in the in-game chat, replacing `[PlayerID]` with the ID of the deceased player.
- The specified player will be revived and transported to the police department if they are dead, have the police job, and are within the server's police job constraints.
- If the specified player is not dead, does not have the police job, or the provided player ID is invalid, appropriate error messages will be displayed.

## Frequently Asked Questions (FAQ)

### Q: How do I change the teleport destination?
**A:** You can modify the destination coordinates by editing the `reviveCoords` variable in the script. Adjust the `x`, `y`, and `z` values to specify the new teleportation location.

### Q: Can I customize the job requirement for reviving players?
**A:** Yes, you can modify the job requirement by changing the job name in the line `if job and job.name == "police" then`. Replace `"police"` with the desired job name in your server configuration.

### Q: How do I add my own revive trigger to the script?
**A:** To add your own revive trigger, you need to modify the script at the comment `-- ADD your own revive trigger  or use TriggerEvent('wasabi_ambulance:revive', playerId)`. For example, if you are using the ESX ambulance job, you can replace the line with the following code:
```lua
TriggerEvent('esx_ambulancejob:revive', playerId)
```

Feel free to reach out if you have any further questions or issues.
