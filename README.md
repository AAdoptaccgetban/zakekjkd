local OrionLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Orion/main/source'))()

local Window = OrionLib:MakeWindow({
    Name = "Adopt V1",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionTest"
})

local Tab = Window:MakeTab({
    Name = "Auto Farm",
    Icon = "rbxassetid://17616325905",
    PremiumOnly = false
})

local Section = Tab:AddSection({
    Name = "Section"
})

OrionLib:MakeNotification({
    Name = "Title!",
    Content = "Notification content... what will it say??",
    Image = "rbxassetid://4483345998",
    Time = 5
})

Tab:AddLabel("City Farm")

Tab:AddButton({
    Name = "Autofarm All Hoops",
    Callback = function()
              _G.autoHoopEnabled = false
_G.autoRaceEnabled = false
_G.autoRebirthEnabled = false
_G.rebirthStoppingPoint = nil

Section2:NewButton("Toggle Auto Hoop", "ButtonInfo", function()
    _G.autoHoopEnabled = not _G.autoHoopEnabled
    while _G.autoHoopEnabled do
        wait()
        local children = workspace.Hoops:GetChildren()
        for i, child in ipairs(children) do
            if child.Name == "Hoop" then
                child.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
            end
        end
    end
end)
})

Tab:AddButton({
    Name = "City Red Orb",
    Callback = function()
        _G.loop = true
        while _G.loop do
            wait()
            for i = 1, 200 do
                game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Red Orb", "City")
            end
        end
    end
})

Tab:AddButton({
   Name = "City Orange Orb",
   Callback = function()
     _G.loop = true
     while _G.loop do
       Wait()
       for i = 1, 200 do
         game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Orange Orb", "City")
            end
        end
    end
})

Tab:AddLabel("Magma Farm")

Tab:AddButton({
    Name = "Magma City Red Orb",
    Callback = function()
        _G.loop = true
        while _G.loop do
            wait()
            for i = 1, 200 do
                game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Red Orb", "Magma City")
            end
        end
    end
})

Tab:AddButton({
   Name = "Magma City Orange Orb",
   Callback = function()
     _G.loop = true
     while _G.loop do
       Wait()
       for i = 1, 200 do
         game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Orange Orb", "Magma City")
            end
        end
    end
})

Tab:AddButton({
	Name = "Auto Race",
	Callback = function()
      		game:GetService("ReplicatedStorage").rEvents.raceEvent:FireServer()
  	end    
})
