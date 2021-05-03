# epoch-right-click-actions for Epoch 1.0.7+

This is an Update of the Click Actions by Mudzereli: https://github.com/mudzereli/DayZEpochDeployableBike/tree/master/overwrites/click_actions

# REPORTING ERRORS/PROBLEMS

1. Please, if you report issues can you please attach (on pastebin or similar) your CLIENT rpt log file as this helps find out the errors very quickly. To find this logfile:

	```sqf
	C:\users\<YOUR WINDOWS USERNAME>\AppData\Local\Arma 2 OA\ArmA2OA.RPT
	```
	
# Index:

* [Mission folder install](https://github.com/AirwavesMan/epoch-right-click-actions#mission-folder-install)


**[>> Download <<](https://github.com/AirwavesMan/epoch-right-click-actions/archive/refs/heads/main.zip)**

# Install:

* This install basically assumes you have a custom compiles.sqf.

** If not, visit this repo and follow the steps there**
https://github.com/AirwavesMan/custom-epoch-functions

# Mission folder install

1. Move the <code>scripts</code> folder and files <code>scripts\clickActions</code> to your mission folder root preserving directory structure.
	
	```sqf
	scripts\clickActions	
	```
	
2. Move the <code>dayz_code</code> folder and files <code>dayz_code\compile</code> to your mission folder root preserving directory structure.
	
	```sqf
	dayz_code\compile	
	``` 	
	
3. Find in your init.sqf

	```sqf
	0 fadeMusic 0;	
	```
	
	And added directly under:

	```sqf
	call compile preprocessFileLineNumbers "scripts\clickActions\config.sqf";	
	```	
	
4. Open your custom compiles and find:

	```sqf
	if (!isDedicated) then {	
	```
	
	And add this inside the square brackets so it looks similar like this:
	
	```sqf
	if (!isDedicated) then {
		player_selectSlot = compile preprocessFileLineNumbers "dayz_code\compile\ui_selectSlot.sqf";
	};	
	```	
	
	You may have the fn_selfaction.sqf also there. Do not delete it then.
	
5. You are done and can use the right-click-actions	with other scripts now.
	
	