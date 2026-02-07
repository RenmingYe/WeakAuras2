WeakAuras2 WoW 12.0 Secret Value Fix
=====================================

This archive contains 6 modified files from WeakAuras2 v5.21.1 that add
pcall protection for WoW 12.0's "Secret Value" API changes.

Problem:
  WoW 12.0 marks UnitHealth/UnitPower/UnitHealthMax/UnitPowerMax return 
  values as "secret values" that throw errors on any arithmetic or comparison.
  This breaks all WeakAuras2 progress bars (health, mana, etc.).

Solution:
  Following ElvUI/oUF's approach, all Lua-side arithmetic on potentially 
  secret values is wrapped in pcall() with safe fallback defaults.

Modified Files:
  1. WeakAuras/Prototypes.lua
  2. WeakAuras/GenericTrigger.lua  
  3. WeakAuras/RegionTypes/RegionPrototype.lua
  4. WeakAuras/RegionTypes/ProgressTexture.lua
  5. WeakAuras/RegionTypes/AuraBar.lua
  6. WeakAuras/RegionTypes/SmoothStatusBarMixin.lua

Installation:
  1. Navigate to your WoW AddOns folder:
     World of Warcraft/_retail_/Interface/AddOns/WeakAuras/
  
  2. BACKUP your existing files before replacing!
  
  3. Extract the ZIP maintaining directory structure:
     - Copy files from WeakAuras/ in the ZIP to your WeakAuras/ addon folder
     - The RegionTypes/ subfolder files go in WeakAuras/RegionTypes/
  
  4. Restart WoW or /reload in game.

Base Version: WeakAuras2 v5.21.1
