local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
    Name = "Early Dawn script",
    Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
    LoadingTitle = "Early Dawn script",
    LoadingSubtitle = "Made By DashBlox",
    Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
    ConfigurationSaving = {
       Enabled = false,
       FolderName = nil, -- Create a custom folder for your hub/game
       FileName = "Early Dawn script"
    },
 
    Discord = {
       Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
       Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
       RememberJoins = true -- Set this to false to make them join the discord every time they load it up
    },
 
    KeySystem = true, -- Set this to true to use our key system
    KeySettings = {
       Title = "Early Dawn | Key",
       Subtitle = "Key System",
       Note = "Thank you for using this", -- Use this to tell the user how to get a key
       FileName = "Roblox", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = true, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"https://pastebin.com/raw/5TE200BX"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
 })

 local MainTab = Window:CreateTab("🏠Home🏠", nil) -- Title, Image
 local MainSection = MainTab:CreateSection("Local Player")

 local Button = MainTab:CreateButton({
    Name = "Always Run",
    Callback = function()
         -- Infinite Sprint (Bypass Stamina System)
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

while true do
    wait(0.1) -- Runs every 0.1 sec to prevent lag
    if character and character:FindFirstChild("Humanoid") then
        character.Humanoid.WalkSpeed = 25 -- Change to your preferred speed
    end
end

    end,
 })

 local Section = MainTab:CreateSection("🥚Esp Resources🥚")

 local Button = MainTab:CreateButton({
    Name = "🗑Esp Rock🗑",
    Callback = function()
         -- Optimized by ChatGPT for better performance & light colors
local RunService = game:GetService("RunService")

-- Tables for tracking objects and updates
local highlightedObjects = {}
local updateConnections = {}

local function getRandomLightColor()
    -- Generate random light pastel colors
    local r = math.random(180, 255) / 255
    local g = math.random(180, 255) / 255
    local b = math.random(180, 255) / 255
    return Color3.new(r, g, b)
end

local function handleNewObject(obj)
    if obj:IsA('UnionOperation') and obj.Parent and obj.Parent.Name == 'Rock' then
        if not highlightedObjects[obj] then
            if not obj.Parent:FindFirstChildOfClass('BillboardGui') then
                local BillboardGui = Instance.new('BillboardGui')
                local TextLabel = Instance.new('TextLabel')

                BillboardGui.Parent = obj.Parent
                BillboardGui.AlwaysOnTop = true
                BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2, 0)

                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundTransparency = 1
                TextLabel.Size = UDim2.new(1, 0, 1, 0)
                TextLabel.Text = "Rock"
                TextLabel.TextScaled = true
                TextLabel.TextStrokeTransparency = 0.5
                TextLabel.TextColor3 = getRandomLightColor() -- Set to a light color

                highlightedObjects[obj] = true
            end
        end
    end
end

-- Handle new objects
game.Workspace.ChildAdded:Connect(handleNewObject)

-- Cleanup when objects are removed
game.Workspace.DescendantRemoving:Connect(function(obj)
    if highlightedObjects[obj] then
        highlightedObjects[obj] = nil
    end
end)

-- Initial scan
for _, obj in ipairs(game.Workspace:GetDescendants()) do
    handleNewObject(obj)
end
    end,
 })

 local Button = MainTab:CreateButton({
    Name = "🍂Esp Mud🍂",
    Callback = function()
         -- Optimized by ChatGPT for better performance & light colors
local RunService = game:GetService("RunService")

-- Tables for tracking objects and updates
local highlightedObjects = {}
local updateConnections = {}

local function getRandomLightColor()
    -- Generate random light pastel colors
    local r = math.random(180, 255) / 255
    local g = math.random(180, 255) / 255
    local b = math.random(180, 255) / 255
    return Color3.new(r, g, b)
end

local function handleNewObject(obj)
    if obj:IsA('MeshPart') and obj.Parent and obj.Parent.Name == 'Mud' then
        if not highlightedObjects[obj] then
            if not obj.Parent:FindFirstChildOfClass('BillboardGui') then
                local BillboardGui = Instance.new('BillboardGui')
                local TextLabel = Instance.new('TextLabel')

                BillboardGui.Parent = obj.Parent
                BillboardGui.AlwaysOnTop = true
                BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2, 0)

                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundTransparency = 1
                TextLabel.Size = UDim2.new(1, 0, 1, 0)
                TextLabel.Text = "Mud"
                TextLabel.TextScaled = true
                TextLabel.TextStrokeTransparency = 0.5
                TextLabel.TextColor3 = getRandomLightColor() -- Set to a light color

                highlightedObjects[obj] = true
            end
        end
    end
end

-- Handle new objects
game.Workspace.ChildAdded:Connect(handleNewObject)

-- Cleanup when objects are removed
game.Workspace.DescendantRemoving:Connect(function(obj)
    if highlightedObjects[obj] then
        highlightedObjects[obj] = nil
    end
end)

-- Initial scan
for _, obj in ipairs(game.Workspace:GetDescendants()) do
    handleNewObject(obj)
end

    end,
 })

 local Button = MainTab:CreateButton({
    Name = "Esp Branch",
    Callback = function()
        local RunService = game:GetService("RunService")

        -- Table to track highlighted objects
        local highlightedObjects = {}
        
        -- Function to generate a random light color
        local function getRandomLightColor()
            return Color3.new(
                math.random(180, 255) / 255,
                math.random(180, 255) / 255,
                math.random(180, 255) / 255
            )
        end
        
        -- Function to highlight "Prompt" objects under BranchTree
        local function handleNewObject(obj)
            if obj:IsA("MeshPart") and obj.Name == "Prompt" and obj.Parent and obj.Parent.Name == "BranchTree" then
                if not highlightedObjects[obj] then
                    print("✅ Highlighting:", obj.Parent.Name) -- Debug info
        
                    -- Prevent duplicates
                    if not obj:FindFirstChildOfClass("BillboardGui") then
                        local BillboardGui = Instance.new("BillboardGui")
                        local TextLabel = Instance.new("TextLabel")
        
                        -- BillboardGui Properties
                        BillboardGui.Parent = obj
                        BillboardGui.AlwaysOnTop = true
                        BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                        BillboardGui.StudsOffset = Vector3.new(0, 2, 0)
        
                        -- TextLabel Properties
                        TextLabel.Parent = BillboardGui
                        TextLabel.BackgroundTransparency = 1
                        TextLabel.Size = UDim2.new(1, 0, 1, 0)
                        TextLabel.Text = "Tree Prompt"
                        TextLabel.TextScaled = true
                        TextLabel.TextStrokeTransparency = 0.5
                        TextLabel.TextColor3 = getRandomLightColor()
        
                        highlightedObjects[obj] = true
                    end
                end
            end
        end
        
        -- Scan for existing objects at script start
        for _, obj in ipairs(game.Workspace:GetDescendants()) do
            handleNewObject(obj)
        end
        
        -- Detect new objects appearing in the game
        game.Workspace.DescendantAdded:Connect(handleNewObject)
        
        -- Remove from tracking when objects are deleted
        game.Workspace.DescendantRemoving:Connect(function(obj)
            if highlightedObjects[obj] then
                highlightedObjects[obj] = nil
                print("❌ Removed:", obj.Name)
            end
        end)
    end,
 })

 local Button = MainTab:CreateButton({
    Name = "Berry",
    Callback = function()
        local RunService = game:GetService("RunService")

        -- Table to track highlighted objects
        local highlightedObjects = {}
        
        -- Function to generate a random light color
        local function getRandomLightColor()
            return Color3.new(
                math.random(180, 255) / 255,
                math.random(180, 255) / 255,
                math.random(180, 255) / 255
            )
        end
        
        -- Function to highlight "MeshPart" objects inside "Berry"
        local function handleNewObject(obj)
            if obj:IsA("MeshPart") and obj.Parent and obj.Parent.Name == "Berry" then
                if not highlightedObjects[obj] then
                    print("✅ Highlighting:", obj.Parent.Name) -- Debug log
        
                    -- Prevent duplicates
                    if not obj.Parent:FindFirstChild("BillboardGui") then
                        local BillboardGui = Instance.new("BillboardGui")
                        local TextLabel = Instance.new("TextLabel")
        
                        -- BillboardGui Properties
                        BillboardGui.Parent = obj.Parent
                        BillboardGui.AlwaysOnTop = true
                        BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                        BillboardGui.StudsOffset = Vector3.new(0, 2, 0)
        
                        -- TextLabel Properties
                        TextLabel.Parent = BillboardGui
                        TextLabel.BackgroundTransparency = 1
                        TextLabel.Size = UDim2.new(1, 0, 1, 0)
                        TextLabel.Text = "Berry"
                        TextLabel.TextScaled = true
                        TextLabel.TextStrokeTransparency = 0.5
                        TextLabel.TextColor3 = getRandomLightColor()
        
                        highlightedObjects[obj] = true
                    end
                end
            end
        end
        
        -- Scan for existing objects at script start
        for _, obj in ipairs(game.Workspace:GetDescendants()) do
            handleNewObject(obj)
        end
        
        -- Detect new objects appearing in the game
        game.Workspace.DescendantAdded:Connect(handleNewObject)
        
        -- Remove from tracking when objects are deleted
        game.Workspace.DescendantRemoving:Connect(function(obj)
            if highlightedObjects[obj] then
                highlightedObjects[obj] = nil
                print("❌ Removed:", obj.Name)
            end
        end)
    end,
 })

 local MainButton = MainTab:CreateButton({
    Name = "FiberBush",
    Callback = function()
        local RunService = game:GetService("RunService")
        local Workspace = game:GetService("Workspace")
        
        -- Table to track highlighted objects
        local highlightedObjects = {}
        
        -- Function to generate a color-changing effect
        local function getColor()
            local hue = tick() % 5 / 5
            return Color3.fromHSV(hue, 1, 1)
        end
        
        -- Function to create ESP
        local function createESP(obj)
            if obj:IsA('MeshPart') and obj.Parent and obj.Parent.Name == 'FiberBush' then
                -- Prevent duplicate ESPs
                if highlightedObjects[obj] then return end
                
                local BillboardGui = Instance.new('BillboardGui')
                local TextLabel = Instance.new('TextLabel')
        
                BillboardGui.Parent = obj.Parent
                BillboardGui.AlwaysOnTop = true
                BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2, 0)
                BillboardGui.Name = "ESP"
        
                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundTransparency = 1
                TextLabel.Size = UDim2.new(1, 0, 1, 0)
                TextLabel.Text = "Fiber"
                TextLabel.TextScaled = true
                TextLabel.TextStrokeTransparency = 0.5
        
                highlightedObjects[obj] = BillboardGui
        
                -- Remove ESP when object is destroyed
                obj.AncestryChanged:Connect(function(_, parent)
                    if not parent then
                        if highlightedObjects[obj] then
                            highlightedObjects[obj]:Destroy()
                            highlightedObjects[obj] = nil
                        end
                    end
                end)
            end
        end
        
        -- Function to update text colors periodically
        RunService.Heartbeat:Connect(function()
            local newColor = getColor()
            for obj, gui in pairs(highlightedObjects) do
                if gui and gui:FindFirstChildOfClass("TextLabel") then
                    gui.TextLabel.TextColor3 = newColor
                end
            end
        end)
        
        -- Detect existing objects at startup
        for _, obj in ipairs(Workspace:GetDescendants()) do
            createESP(obj)
        end
        
        -- Detect new objects
        Workspace.DescendantAdded:Connect(createESP)
        
        -- Remove ESP when an object disappears
        Workspace.DescendantRemoving:Connect(function(obj)
            if highlightedObjects[obj] then
                highlightedObjects[obj]:Destroy()
                highlightedObjects[obj] = nil
            end
        end)
    end
})


 local Section = MainTab:CreateSection("Esp Animals")

 local Button = MainTab:CreateButton({
    Name = "Esp Elephant if theres around",
    Callback = function()
         -- Optimized by ChatGPT for better performance & light colors
local RunService = game:GetService("RunService")

-- Tables for tracking objects and updates
local highlightedObjects = {}
local updateConnections = {}

local function getRandomLightColor()
    -- Generate random light pastel colors
    local r = math.random(180, 255) / 255
    local g = math.random(180, 255) / 255
    local b = math.random(180, 255) / 255
    return Color3.new(r, g, b)
end

local function handleNewObject(obj)
    if obj:IsA('Part') and obj.Parent and obj.Parent.Name == 'Elephasrecki' then
        if not highlightedObjects[obj] then
            if not obj.Parent:FindFirstChildOfClass('BillboardGui') then
                local BillboardGui = Instance.new('BillboardGui')
                local TextLabel = Instance.new('TextLabel')

                BillboardGui.Parent = obj.Parent
                BillboardGui.AlwaysOnTop = true
                BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2, 0)

                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundTransparency = 1
                TextLabel.Size = UDim2.new(1, 0, 1, 0)
                TextLabel.Text = "Elephant"
                TextLabel.TextScaled = true
                TextLabel.TextStrokeTransparency = 0.5
                TextLabel.TextColor3 = getRandomLightColor() -- Set to a light color

                highlightedObjects[obj] = true
            end
        end
    end
end

-- Handle new objects
game.Workspace.ChildAdded:Connect(handleNewObject)

-- Cleanup when objects are removed
game.Workspace.DescendantRemoving:Connect(function(obj)
    if highlightedObjects[obj] then
        highlightedObjects[obj] = nil
    end
end)

-- Initial scan
for _, obj in ipairs(game.Workspace:GetDescendants()) do
    handleNewObject(obj)
end
    end,
 })

 local Button = MainTab:CreateButton({
   Name = "Hyena",
   Callback = function()
        local RunService = game:GetService("RunService")

-- Table to track highlighted objects
local highlightedObjects = {}

-- Function to generate a random light color
local function getRandomLightColor()
    return Color3.new(
        math.random(180, 255) / 255,
        math.random(180, 255) / 255,
        math.random(180, 255) / 255
    )
end

-- Function to check if the parent is "Hyena" even if deeper in hierarchy
local function isHyenaObject(obj)
    while obj.Parent do
        if obj.Parent.Name == "Hyena" then
            return true
        end
        obj = obj.Parent
    end
    return false
end

-- Function to handle ESP for hyenas
local function handleNewObject(obj)
    if obj:IsA("MeshPart") and isHyenaObject(obj) then
        if not highlightedObjects[obj] then
            print("✅ Highlighting Hyena:", obj.Parent.Name) -- Debug log

            -- Prevent duplicates
            if not obj.Parent:FindFirstChild("BillboardGui") then
                local BillboardGui = Instance.new("BillboardGui")
                local TextLabel = Instance.new("TextLabel")

                -- BillboardGui Properties
                BillboardGui.Parent = obj.Parent
                BillboardGui.AlwaysOnTop = true
                BillboardGui.Size = UDim2.new(0, 50, 0, 50)
                BillboardGui.StudsOffset = Vector3.new(0, 2, 0)

                -- TextLabel Properties
                TextLabel.Parent = BillboardGui
                TextLabel.BackgroundTransparency = 1
                TextLabel.Size = UDim2.new(1, 0, 1, 0)
                TextLabel.Text = "Hyena"
                TextLabel.TextScaled = true
                TextLabel.TextStrokeTransparency = 0.5
                TextLabel.TextColor3 = getRandomLightColor()

                highlightedObjects[obj] = true
            end
        end
    end
end

-- Scan for existing hyenas at script start
for _, obj in ipairs(game.Workspace:GetDescendants()) do
    handleNewObject(obj)
end

-- Detect new hyenas appearing in the game
game.Workspace.DescendantAdded:Connect(handleNewObject)

-- Remove from tracking when objects are deleted
game.Workspace.DescendantRemoving:Connect(function(obj)
    if highlightedObjects[obj] then
        highlightedObjects[obj] = nil
        print("❌ Removed:", obj.Name)
    end
end)
   end,
})

 local MiscTab = Window:CreateTab("🙂Misc🙂") -- Title, Image
 local MiscSection = MiscTab:CreateSection("🧩Add-Ons🧩")

 local MiscButton = MiscTab:CreateButton({
    Name = "Fullbright",
    Callback = function()
         -- Get Lighting Service
local lighting = game:GetService("Lighting")

-- Apply FullBright once
lighting.Brightness = 10
lighting.ShadowSoftness = 0
lighting.OutdoorAmbient = Color3.new(1, 1, 1)
lighting.Ambient = Color3.new(1, 1, 1)

-- Keep enforcing FullBright (prevents game resets)
lighting.Changed:Connect(function()
    lighting.Brightness = 10
    lighting.ShadowSoftness = 0
    lighting.OutdoorAmbient = Color3.new(1, 1, 1)
    lighting.Ambient = Color3.new(1, 1, 1)
end)

    end,
 })
