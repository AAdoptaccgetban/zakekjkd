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
              local rootpart = game.Players.LocalPlayer.Character.HumanoidRootPart

for i, v in pairs(workspace.Hoops:GetChildren()) do
rootpart.CFrame = v.CFrame wait(0.2)
end
      end
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
