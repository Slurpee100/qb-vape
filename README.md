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
["vape"] = {"amb@world_human_smoking@female@idle_a", "idle_b", "Vape", AnimationOptions =
   {
       Prop = "ba_prop_battle_vape_01",
       PropBone = 28422,
       PropPlacement = {0.015, -0.009, 0.003, 55.0, 0.0, 110.0},
       EmoteLoop = true,
       EmoteMoving = true,
   }},
```  
Add image to qb-inventory/html/images or aj-inventory/html/images
