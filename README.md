local OrionLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Orion/main/source'))()

local Window = OrionLib:MakeWindow({
    Name = "Adopt V1",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionTest"
})

local Tab = Window:MakeTab({
    Name = "Auto Farm",
    Icon = "rbxassetid://4483345998",
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

Tab:AddButton({
    Name = "Auto Farm Orb",
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

local bb=game:service'VirtualUser'
game:service'Players'.LocalPlayer.Idled:connect(function()
bb:CaptureController()bb:ClickButton2(Vector2.new())
