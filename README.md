# qb-vape
Vape item for QBCore

qb-smallresources/client/consumables.lua

```
RegisterNetEvent("consumables:client:Vape")
AddEventHandler("consumables:client:Vape", function()
    QBCore.Functions.Progressbar("vape_smoke", "Puting Juice Into Vape..", 1500, false, true, {
        disableMovement = false,
        disableCarMovement = false,
		disableMouse = false,
		disableCombat = true,
    }, {}, {}, {}, function() -- Done
        TriggerEvent("inventory:client:ItemBox", QBCore.Shared.Items["vapepen"], "remove")
        if IsPedInAnyVehicle(PlayerPedId(), false) then
            TriggerEvent('animations:client:EmoteCommandStart', {"vape"})
        else
            TriggerEvent('animations:client:EmoteCommandStart', {"vape"})
        end
        TriggerEvent("evidence:client:SetStatus", "weedsmell", 300)
        TriggerEvent('animations:client:SmokeWeed')
    end)
end)
```

qb-core/shared.lua
```
["vapepen"] 			 		 = {["name"] = "vapepen", 						["label"] = "Vape Pen", 				["weight"] = 400, 		["type"] = "item", 		["image"] = "vapepen.png", 			["unique"] = false, 	["useable"] = true, 	["shouldClose"] = true,	   ["combinable"] = nil,   ["description"] = "Vape Pen"},
```
dpemotes/client/AnimationList @ lines 2061 to  2068
```
["vape"] = {"mp_player_inteat@burger", "mp_player_int_eat_burger_fp", "base", "Vape", AnimationOptions =
   {
       Prop = "ba_prop_battle_vape_01",
       PropBone = 18905,
       PropPlacement = {0.08, -0.00, 0.03, -150.0, 90.0, -10.0},
       EmoteLoop = true,
       EmoteMoving = true,
   }},
```  
