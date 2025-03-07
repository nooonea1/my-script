local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
    Name = "Early Dawn script",
    Icon = 0,
    LoadingTitle = "Early Dawn script",
    LoadingSubtitle = "Made By DashBlox",
    Theme = "Default",
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false,
    ConfigurationSaving = {
       Enabled = false,
       FolderName = nil,
       FileName = "Early Dawn script"
    },
    Discord = {
       Enabled = false,
       Invite = "noinvitelink",
       RememberJoins = true
    },
    KeySystem = true,
    KeySettings = {
       Title = "Early Dawn | Key",
       Subtitle = "Key System",
       Note = "Thank you for using this",
       FileName = "Roblox",
       SaveKey = true,
       GrabKeyFromSite = true,
       Key = {"https://pastebin.com/raw/5TE200BX"}
    }
})

local MainTab = Window:CreateTab("🏠Home🏠", nil)
local MainSection = MainTab:CreateSection("Local Player")

local Button = MainTab:CreateButton({
    Name = "Always Run",
    Callback = function()
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        while true do
            wait(0.1)
            if character and character:FindFirstChild("Humanoid") then
                character.Humanoid.WalkSpeed = 25
            end
        end
    end,
})

local ResourceTab = Window:CreateTab("🥚Esp Resources🥚")
local ResourceSection = ResourceTab:CreateSection("Resources")

local AnimalTab = Window:CreateTab("🦁Esp Animals🦁")
local AnimalSection = AnimalTab:CreateSection("Animals")

local MiscTab = Window:CreateTab("🙂Misc🙂")
local MiscSection = MiscTab:CreateSection("🧩Add-Ons🧩")

-- ESP Buttons for Resources
local resources = {
    {Name = "Esp Rock", Parent = "Rock", Class = "UnionOperation"},
    {Name = "Esp Mud", Parent = "Mud", Class = "MeshPart"},
    {Name = "Esp Branch", Parent = "BranchTree", Class = "MeshPart"},
    {Name = "Berry", Parent = "Berry", Class = "MeshPart"},
    {Name = "FiberBush", Parent = "FiberBush", Class = "MeshPart"}
}

for _, resource in ipairs(resources) do
    ResourceTab:CreateButton({
        Name = resource.Name,
        Callback = function()
            local function handleNewObject(obj)
                if obj:IsA(resource.Class) and obj.Parent and obj.Parent.Name == resource.Parent then
                    if not obj.Parent:FindFirstChild("BillboardGui") then
                        local BillboardGui = Instance.new("BillboardGui")
                        local TextLabel = Instance.new("TextLabel")
                        BillboardGui.Parent = obj.Parent
                        BillboardGui.AlwaysOnTop = true
                        BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                        BillboardGui.StudsOffset = Vector3.new(0, 2, 0)
                        TextLabel.Parent = BillboardGui
                        TextLabel.BackgroundTransparency = 1
                        TextLabel.Size = UDim2.new(1, 0, 1, 0)
                        TextLabel.Text = resource.Parent
                        TextLabel.TextScaled = true
                        TextLabel.TextStrokeTransparency = 0.5
                        TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                    end
                end
            end
            for _, obj in ipairs(game.Workspace:GetDescendants()) do
                handleNewObject(obj)
            end
            game.Workspace.DescendantAdded:Connect(handleNewObject)
        end,
    })
end

-- ESP Buttons for Animals
local animals = {
    {Name = "Hyena", Parent = "Hyena", Class = "MeshPart"},
    {Name = "Elephant", Parent = "Elephasrecki", Class = "Part"}
}

for _, animal in ipairs(animals) do
    AnimalTab:CreateButton({
        Name = "Esp " .. animal.Name,
        Callback = function()
            local function handleNewObject(obj)
                if obj:IsA(animal.Class) and obj.Parent and obj.Parent.Name == animal.Parent then
                    if not obj.Parent:FindFirstChild("BillboardGui") then
                        local BillboardGui = Instance.new("BillboardGui")
                        local TextLabel = Instance.new("TextLabel")
                        BillboardGui.Parent = obj.Parent
                        BillboardGui.AlwaysOnTop = true
                        BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                        BillboardGui.StudsOffset = Vector3.new(0, 2, 0)
                        TextLabel.Parent = BillboardGui
                        TextLabel.BackgroundTransparency = 1
                        TextLabel.Size = UDim2.new(1, 0, 1, 0)
                        TextLabel.Text = animal.Name
                        TextLabel.TextScaled = true
                        TextLabel.TextStrokeTransparency = 0.5
                        TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
                    end
                end
            end
            for _, obj in ipairs(game.Workspace:GetDescendants()) do
                handleNewObject(obj)
            end
            game.Workspace.DescendantAdded:Connect(handleNewObject)
        end,
    })
end

-- Misc Buttons
MiscTab:CreateButton({
    Name = "Fullbright",
    Callback = function()
        local lighting = game:GetService("Lighting")
        lighting.Brightness = 10
        lighting.ShadowSoftness = 0
        lighting.OutdoorAmbient = Color3.new(1, 1, 1)
        lighting.Ambient = Color3.new(1, 1, 1)
        lighting.Changed:Connect(function()
            lighting.Brightness = 10
            lighting.ShadowSoftness = 0
            lighting.OutdoorAmbient = Color3.new(1, 1, 1)
            lighting.Ambient = Color3.new(1, 1, 1)
        end)
    end,
})

MiscTab:CreateButton({
    Name = "Inf Yield",
    Callback = function()
        loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
    end,
})
