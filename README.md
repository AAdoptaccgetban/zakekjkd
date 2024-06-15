local Library = loadstring(game:HttpGet("https://pastebin.com/raw/vff1bQ9F"))()
local Window = Library.CreateLib("Adopt V1", "Ocean")

local Tab1 = Window:NewTab("AV1")
local Section1 = Tab1:NewSection("Credits")
Section1:NewLabel("Discord: @cyber.devv & @adoptfrfr")

local Tab2 = Window:NewTab("Auto farm")
local Section2 = Tab2:NewSection("Menu")

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

Section2:NewButton("Toggle Auto Race", "ButtonInfo", function()
    _G.autoRaceEnabled = not _G.autoRaceEnabled
    game:GetService('ReplicatedStorage').raceInProgress.Changed:Connect(function()
        if game:GetService('ReplicatedStorage').raceInProgress.Value == true then
            if _G.autoRaceEnabled then
                game:GetService('ReplicatedStorage').rEvents.raceEvent:FireServer("joinRace")
            end
        end
    end)

game:GetService('ReplicatedStorage').raceStarted.Changed:Connect(function()
        if game:GetService('ReplicatedStorage').raceStarted.Value == true then
            if _G.autoRaceEnabled then
                for i, v in pairs(game:GetService('Workspace').raceMaps:GetChildren()) do
                    local OldFinishPosition = v.finishPart.CFrame
                    v.finishPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                    wait()
                    v.finishPart.CFrame = OldFinishPosition
                end
            end
            wait(2)
        end
    end)
end)

Section2:NewToggle("Toggle Auto Rebirth", "ButtonInfo", function(state)
    _G.autoRebirthEnabled = state
    if _G.autoRebirthEnabled then
        spawn(function()
            while _G.autoRebirthEnabled do
                wait()
                -- Check rebirth stopping condition
                if _G.rebirthStoppingPoint and game.Players.LocalPlayer.leaderstats.Rebirths.Value >= _G.rebirthStoppingPoint then
                    game.Players.LocalPlayer:Kick("Reached rebirth stopping point")
                    return
                end
                -- Perform rebirth
                game:GetService("ReplicatedStorage").rEvents.rebirthEvent:FireServer()
            end
        end)
    end
end)

Section2:NewTextBox("Set Rebirth Stopping Point", "Number", function(text)
    _G.rebirthStoppingPoint = tonumber(text)
end)

wait(0.5)

local bb = game:service'VirtualUser'
game:service'Players'.LocalPlayer.Idled:connect(function()
    bb:CaptureController()
    bb:ClickButton2(Vector2.new())
end)

local Tab3 = Window:NewTab("Glitching")
local Section3 = Tab3:NewSection("")

-- Your existing orb farming buttons


Section3:NewButton("Yellow Orbs (Main City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do 
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Yellow Orb", "City")
        end
    end
end)

Section3:NewButton("Orange Orbs (Main City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do 
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Orange Orb", "City")
        end
    end
end)

Section3:NewButton("Blue Orbs (Main City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do 
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Blue Orb", "City")
        end
    end
end)

Section3:NewButton("Red Orbs (Main City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do 
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Red Orb", "City")
        end
    end
end)
Section3:NewButton("Orange Orbs (Snow City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do 
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Orange Orb", "Snow City")
        end
    end
end)

Section3:NewButton("Blue Orbs (Snow City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Blue Orb", "Snow City")
        end
    end
end)

Section3:NewButton("Red Orbs (Snow City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Red Orb", "Snow City")
        end
    end
end)

Section3:NewButton("Gem Farm (Snow City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Gem", "Snow City")
        end
    end
end)

Section3:NewButton("Yellow Orbs (Magma City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Yellow Orb", "Magma City")
        end
    end
end)

Section3:NewButton("Orange Orbs (Magma City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Orange Orb", "Magma City")
        end
    end
end)

Section3:NewButton("Blue Orbs (Magma City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Blue Orb", "Magma City")
        end
    end
end)

Section3:NewButton("Red Orbs (Magma City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Red Orb", "Magma City")
        end
    end
end)

Section3:NewButton("Gem Farm (Magma City)", "ButtonInfo", function()
    _G.loop = true
    while _G.loop == true do
        wait()
        for i = 200 do
            game:GetService('ReplicatedStorage').rEvents.orbEvent:FireServer("collectOrb", "Gem", "Magma City")
        end
    end
