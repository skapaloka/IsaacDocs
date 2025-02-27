# Class "Level"

???+ info
    You can get this class by using the following functions:

    * [Game:GetLevel()](Game.md#getlevel)

    ???+ example "Example Code"
        ```lua
        local level = Game():GetLevel()
        ```

## Functions
### Add·Angel·Room·Chance () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void AddAngelRoomChance ( float Chance ) {: .copyable aria-label='Functions' }

___
### Add·Curse () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void AddCurse ( [LevelCurse](enums/LevelCurse.md) Curse, boolean ShowName ) {: .copyable aria-label='Functions' }

???+ info
    As entries in curses.xml enumerate from 1 instead of 0, the LevelCurse bitmask value for a new curse must be acquired by doing 1 << (Isaac.GetCurseIdByName("...") - 1). This bitmask value is what's accepted by Level:AddCurse and the return value of MC_POST_CURSE_EVAL.
___
### Apply·Blue·Map·Effect () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void ApplyBlueMapEffect ( ) {: .copyable aria-label='Functions' }

___
### Apply·Compass·Effect () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void ApplyCompassEffect ( boolean Persistent ) {: .copyable aria-label='Functions' }

___
### Apply·Map·Effect () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void ApplyMapEffect ( ) {: .copyable aria-label='Functions' }

___
### Can·Open·Challenge·Room () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean CanOpenChallengeRoom ( int RoomIndex ) {: .copyable aria-label='Functions' }

___
### Can·Spawn·Devil·Room () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean CanSpawnDevilRoom ( ) {: .copyable aria-label='Functions' }

___
### Can·Stage·Have·Curse·Of·Labyrinth () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean CanStageHaveCurseOfLabyrinth ( [LevelStage](enums/LevelStage.md) Stage ) {: .copyable aria-label='Functions' }

___
### Change·Room () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### void ChangeRoom ( int RoomIndex, int Dimension = -1 ) {: .copyable aria-label='Functions' }

???+ bug "Bugs"
    This method does not update the fxlayers properly. Do not use this method and use `Game.ChangeRoom` instead.

___
### Disable·Devil·Room () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void DisableDevilRoom ( ) {: .copyable aria-label='Functions' }

___
### Force·Horseman·Boss () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean ForceHorsemanBoss ( int Seed ) {: .copyable aria-label='Functions' }
return true on success
___
### Get·Absolute·Stage () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [LevelStage](enums/LevelStage.md) GetAbsoluteStage ( ) {: .copyable aria-label='Functions' }
In non-Greed Mode, returns the same thing as the `GetStage()` method. In Greed Mode, returns the adjusted stage similar to what it would be in non-Greed Mode.

For example:

- On Greed Mode Basement, `GetStage()` returns 1, and `GetAbsoluteStage()` returns 1.
- On Greed Mode Caves, `GetStage()` returns 2, and `GetAbsoluteStage()` returns 3.
- On Greed mode Depths, `GetStage()` returns 3, and `GetAbsoluteStage()` returns 5.

___
### Get·Angel·Room·Chance () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### float GetAngelRoomChance ( ) {: .copyable aria-label='Functions' }

___
### Get·Can·See·Everything () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean GetCanSeeEverything ( ) {: .copyable aria-label='Functions' }

___
### Get·Current·Room () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [Room](Room.md) GetCurrentRoom ( ) {: .copyable aria-label='Functions' }

___
### Get·Current·Room·Desc () {: aria-label='Functions' }
[ ](#){: .const .tooltip .badge } [ ](#){: .abrep .tooltip .badge }
#### const [RoomDescriptor](RoomDescriptor.md) GetCurrentRoomDesc ( ) {: .copyable aria-label='Functions' }
This functions returns a read only version of the [RoomDescriptor](RoomDescriptor.md) of the current room. If you want to edit the [RoomDescriptor](RoomDescriptor.md), use `GetRoomByIdx()` with `GetCurrentRoomIndex()` instead.

???- example "Example Code"
    This gets the current rooms [RoomDescriptor](RoomDescriptor.md) class in read only and writeable versions.
    ```lua
    local level = Game():GetLevel()
    local readOnlyRoomDesc = level:GetCurrentRoomDesc()
    local writeableRoomDesc = level:GetRoomByIdx(level:GetCurrentRoomIndex())
    ```
___
### Get·Current·Room·Index () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetCurrentRoomIndex ( ) {: .copyable aria-label='Functions' }


???- note "Notes"
    This will always return the roomindex on the levelgrid, on which you entered the current room from. (see black entries in graphic below)

    ![Room Grid indices](images/infographics/RoomGridIndices.png)
___
### Get·Curse·Name () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### string GetCurseName ( ) {: .copyable aria-label='Functions' }

___
### Get·Curses () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetCurses ( ) {: .copyable aria-label='Functions' }

___
### Get·Devil·Angel·Room·RNG () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [RNG](RNG.md) GetDevilAngelRoomRNG ( ) {: .copyable aria-label='Functions' }

___
### Get·Dungeon·Placement·Seed () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetDungeonPlacementSeed ( ) {: .copyable aria-label='Functions' }

___
### Get·Enter·Position () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [Vector](Vector.md) GetEnterPosition ( ) {: .copyable aria-label='Functions' }

___
### Get·Heart·Picked () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean GetHeartPicked ( ) {: .copyable aria-label='Functions' }

___
### Get·Last·Boss·Room·List·Index () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetLastBossRoomListIndex ( ) {: .copyable aria-label='Functions' }

___
### Get·Last·Room·Desc () {: aria-label='Functions' }
[ ](#){: .const .tooltip .badge } [ ](#){: .abrep .tooltip .badge }
#### const [RoomDescriptor](RoomDescriptor.md) GetLastRoomDesc ( ) {: .copyable aria-label='Functions' }

___
### Get·Name () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### string GetName ( ) {: .copyable aria-label='Functions' }

___
### Get·Non·Complete·Room·Index () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetNonCompleteRoomIndex ( ) {: .copyable aria-label='Functions' }

___
### Get·Planetarium·Chance () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### float GetPlanetariumChance ( ) {: .copyable aria-label='Functions' }
Returns the probability of getting a Planetarium (in the 0-1 range)

___
### Get·Previous·Room·Index () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetPreviousRoomIndex ( ) {: .copyable aria-label='Functions' }

___
### Get·Random·Room·Index () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetRandomRoomIndex ( boolean IAmErrorRoom, int Seed ) {: .copyable aria-label='Functions' }

___
### Get·Room·By·Idx () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### [RoomDescriptor](RoomDescriptor.md) GetRoomByIdx ( int RoomIdx, int Dimension = -1 ) {: .copyable aria-label='Functions' }

???- example "Example Code"
    This gets the current rooms [RoomDescriptor](RoomDescriptor.md) class.
    ```lua
    local level = Game():GetLevel()
    local curRoomDesc = level:GetRoomByIdx(level:GetCurrentRoomIndex())
    ```

???- info "Dimension Info"
    Dimension: ID of the dimension to get the room from

		* -1: Current dimension
		* 0: Main dimension
		* 1: Secondary dimension, used by Downpour mirror dimension and Mines escape sequence
		* 2: Death Certificate dimension

???- warn "Warning"
    This function always returns a valid RoomDescriptor object, so error checking is recommended. The `GridIndex` property of an invalid RoomDescriptor object seems to always be -1. Note that this specific `GridIndex` is also used by the Devil/Angel Room, but those rooms will have a different `VisitedCount`.

___
### Get·Room·Count () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetRoomCount ( ) {: .copyable aria-label='Functions' }

___
### Get·Rooms () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [RoomDescriptor List](CppContainer_ArrayProxy_RoomDescriptor.md) GetRooms ( ) {: .copyable aria-label='Functions' }

___
### Get·Stage () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [LevelStage](enums/LevelStage.md) GetStage ( ) {: .copyable aria-label='Functions' }

___
### Get·Stage·Type () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### [StageType](enums/StageType.md) GetStageType ( ) {: .copyable aria-label='Functions' }

___
### Get·Starting·Room·Index () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### int GetStartingRoomIndex ( ) {: .copyable aria-label='Functions' }

___
### Get·State·Flag () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean GetStateFlag ( [LevelStateFlag](enums/LevelStateFlag.md) LevelStateFlag) {: .copyable aria-label='Functions' }

___
### Has·Boss·Challenge () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean HasBossChallenge ( ) {: .copyable aria-label='Functions' }

___
### Initialize·Devil·Angel·Room () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void InitializeDevilAngelRoom ( boolean ForceAngel, boolean ForceDevil ) {: .copyable aria-label='Functions' }

___
### Is·Alt·Stage () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean IsAltStage ( ) {: .copyable aria-label='Functions' }

___
### Is·Ascent () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### boolean IsAscent ( ) {: .copyable aria-label='Functions' }
Returns true if the player is in the Ascent.

___
### Is·Devil·Room·Disabled () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean IsDevilRoomDisabled ( ) {: .copyable aria-label='Functions' }

___
### Is·Next·Stage·Available () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### boolean IsNextStageAvailable ( ) {: .copyable aria-label='Functions' }

___
### Is·Pre·Ascent () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### boolean IsPreAscent ( ) {: .copyable aria-label='Functions' }
Returns true if the player is in the version of Mausoleum/Gehenna II leading to the Ascent.

___
### Make·Red·Room·Door () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### boolean MakeRedRoomDoor ( int CurrentRoomIdx, DoorSlot Slot ) {: .copyable aria-label='Functions' }
Attempts to create a red room door in the given room at the given door slot

Returns true on success.
___
### Query·Room·Type·Index () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### int QueryRoomTypeIndex ( [RoomType](enums/RoomType.md) RoomType, boolean Visited, [RNG](RNG.md) rng, boolean IgnoreGroup = false ) {: .copyable aria-label='Functions' }
IgnoreGroup: If set to true, includes rooms that do not have the same group ID as the current room (currently unused)
___
### Remove·Compass·Effect () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void RemoveCompassEffect ( ) {: .copyable aria-label='Functions' }

___
### Remove·Curses () {: aria-label='Functions' }
[ ](#){: .rep .tooltip .badge }
#### void RemoveCurses ( [LevelCurse](enums/LevelCurse.md) Curses ) {: .copyable aria-label='Functions' }
Curses: A bitmask of LevelCurse that indicates which curses will be removed

???- example "Example Code"
    This example removes curse of darkness and curse of the blind
    ```lua
    Game():GetLevel():RemoveCurses(LevelCurse.CURSE_OF_DARKNESS | LevelCurse.CURSE_OF_BLIND)
    ```
___
### Set·Can·See·Everything () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void SetCanSeeEverything ( boolean Value ) {: .copyable aria-label='Functions' }

___
### Set·Heart·Picked () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void SetHeartPicked ( ) {: .copyable aria-label='Functions' }

___
### Set·Next·Stage () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void SetNextStage ( ) {: .copyable aria-label='Functions' }

This function puts you in the next stage without applying any of the floor changes except visuals until you use StartStageTransition()
___
### Set·Red·Heart·Damage () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void SetRedHeartDamage ( ) {: .copyable aria-label='Functions' }

___
### Set·Stage () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void SetStage ( [LevelStage](enums/LevelStage.md) Stage, [StageType](enums/StageType.md) StageType ) {: .copyable aria-label='Functions' }
for SetStage/SetNextStage to have effect, call Init afterward
___
### Set·State·Flag () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void SetStateFlag ( [LevelStateFlag](enums/LevelStateFlag.md) LevelStateFlag, boolean Val ) {: .copyable aria-label='Functions' }

___
### Show·Map () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void ShowMap ( ) {: .copyable aria-label='Functions' }
Show's all map (world/sun card effect) except the top secret room.
___
### Show·Name () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void ShowName ( boolean Sticky ) {: .copyable aria-label='Functions' }

___
### Uncover·Hidden·Door () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void UncoverHiddenDoor ( int CurrentRoomIdx, [DoorSlot](enums/DoorSlot.md) Slot ) {: .copyable aria-label='Functions' }
Uncovers the door on both sides by modifying the saved grid entities for neighboring room.
___
### Update () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void Update ( ) {: .copyable aria-label='Functions' }

___
### Update·Visibility () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
#### void UpdateVisibility ( ) {: .copyable aria-label='Functions' }


???- note "Notes"
    Whenever you update the visibility of a room on the minimap, it won't update the map automatically, since it is cached. You have to explicitly call  UpdateVisibility() afterwards to apply any changes.

???- example "Example Code"
    This code
    ```lua
    -- Local variables
    local game = Game()
    local level = game:GetLevel()

    -- Give the player the Compass effect, which will display all of the floor's special rooms on the mini-map
    level:ApplyCompassEffect()

    -- Remove the icon for the Treasure Room specifically
    local treasureIndex = level:QueryRoomTypeIndex(RoomType.ROOM_TREASURE, false, RNG())
    local treasureRoom = level:GetRoomByIdx(treasureIndex)
    treasureRoom.DisplayFlags = 0

    -- Since the mini-map is cached, changing display flags won't update it unless we explicitly call this function
    level:UpdateVisibility()

    ```

___
## Variables
### Dungeon·Return·Position {: aria-label='Variables' }
[ ](#){: .abrep .tooltip .badge }
#### [Vector](Vector.md) DungeonReturnPosition {: .copyable aria-label='Variables' }

___
### Dungeon·Return·Room·Index {: aria-label='Variables' }
[ ](#){: .abrep .tooltip .badge }
#### int DungeonReturnRoomIndex  {: .copyable aria-label='Variables' }

___
### Enter·Door {: aria-label='Variables' }
[ ](#){: .abrep .tooltip .badge }
#### int EnterDoor  {: .copyable aria-label='Variables' }

This value defines on which doorslot you entered the room.

???+ bug "Bugs"
    Changing this value has no impact on anything. the EnterDoor value is always determined by the LeaveDoor Value and the game itself.
___
### Greed·Mode·Wave {: aria-label='Variables' }
[ ](#){: .abrep .tooltip .badge }
#### int GreedModeWave  {: .copyable aria-label='Variables' }

___
### Leave·Door {: aria-label='Variables' }
[ ](#){: .abrep .tooltip .badge }
#### int LeaveDoor  {: .copyable aria-label='Variables' }

This value defines on which doorslot you are positioned after the transition. You will always end up at the oposite side of the door specified. Example: LeaveDoor=1 (Up0) will position you at Doorslot Down0 (Logic: Doorslot+2)

???- note "Notes"
    if level.LeaveDoor is set to anything other than -1, the function will transition based on the room you are currently in.
___
