- ❌ don't read this shit
- 👋 Hi, I’m @JacksonBnolbob
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
JacksonBnolbob/JacksonBnolbob is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


local ws = cloneref(game:GetService("Workspace"))

if ws:FindFirstChild("FriedChicken") then
cloneref(game:GetService("StarterGui")):SetCore("SendNotification", {
    Title = "Notification";
    Text = "Script already executed";
    Duration = 5;
})
return end

local part = Instance.new("Part")
part.Parent = ws
part.Name = "FriedChicken"
part.Size = Vector3.new(5, 5, 5)
part.Position = Vector3.new(0, 5, 0)
part.Transparency = 1
part.CanCollide = false
part.Anchored = true

function Load(url)
    coroutine.wrap(function()
        local success, scriptFunction = pcall(function()
            return loadstring(game:HttpGet(url, true))
        end)

        if success and scriptFunction then
            coroutine.wrap(scriptFunction)() 
        else
            warn("Failed to load script:", scriptFunction)
        end
    end)()
end


function info(txt)
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Credits = Instance.new("TextLabel")
pcall(function() game.CoreGui.Revit:Destroy() end)
task.wait(.1)
ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.IgnoreGuiInset = true
ScreenGui.ResetOnSpawn = false
ScreenGui.Name = 'ShedletskyGui'
MainFrame.Name = "Fried Chicken Jockey"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.BorderColor3 = Color3.fromRGB(255, 0, 0)


spawn(function()
Credits.Parent = ScreenGui
Credits.Font=Enum.Font.Arcade
Credits.TextColor3=Color3.new(1,1,1)
Credits.Position = UDim2.new(0,0,0,0)
Credits.TextSize = 35
Credits.Size = UDim2.new(1,0,.1,0)
Credits.Text = ''
Credits.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Credits.BorderColor3 = Color3.fromRGB(255, 0, 0)
end)
function tw(var,s)
local a = ""
local s_l = #s
for i = 1, s_l do
local c = string.sub(s, i, i)
a = a .. c
var.Text = a
if c == "." then
wait(.6)
elseif c == ";" then
wait(.3)
elseif c == "," then
wait(.3)
elseif c == "!" then
wait(.3)
end
wait(.03)
end end
tw(Credits,txt)
task.wait(2)
ScreenGui:Destroy()
end

spawn(function()
info('🍗ty for using ShedSaken🍗')

end)
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function SetupScript(Character)
    -- Your script main code here
    print("Im shedletsky and I like fried chicken")
   LocalCD = 1
end

-- Run immediately if already spawned
if LocalPlayer.Character then
    SetupScript(LocalPlayer.Character)
end

-- Run again every time the player respawns
LocalPlayer.CharacterAdded:Connect(function(Character)
    SetupScript(Character)
end)
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
local Window = Rayfield:CreateWindow({
   Name = "ShedSaken",
   Icon = 92658833430818, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "Loading",
   LoadingSubtitle = "Wait...",
   Theme = "Amethyst", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "Type Key",
      Subtitle = "",
      Note = "The key is ICastNecromancyRiseOiOi", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"ICastNecromancyRiseOiOi"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})
local Tab = Window:CreateTab("Stamina",4483362458)
local Section = Tab:CreateSection("Stamina")
local Button = Tab:CreateButton({
   Name = "Infinite Stamina",
   Callback = function()
   local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function SetupStaminaScript(Character)
    local StaminaModule = require(game.ReplicatedStorage.Systems.Character.Game.Sprinting)

    -- Disable stamina loss
    StaminaModule.StaminaLossDisabled = true

    -- Continuously refill stamina
    task.spawn(function()
        while true do
            task.wait(0.1)
            if StaminaModule then
                StaminaModule.Stamina = StaminaModule.MaxStamina
                StaminaModule.StaminaChanged:Fire()
            end
        end
    end)
end

-- Run once if already spawned
if LocalPlayer.Character then
    SetupStaminaScript(LocalPlayer.Character)
end

-- Run again every time you respawn
LocalPlayer.CharacterAdded:Connect(function(Character)
    -- Little delay to make sure the character loads properly
    task.wait(1)
    SetupStaminaScript(Character)
end)
       local rs = cloneref(game:GetService("ReplicatedStorage"))
local sprint = rs.Systems.Character.Game.Sprinting
local m = require(sprint)

m.Stamina = 100

task.spawn(function()
    while task.wait(0.1) do
        if m.Stamina <= 5 then
            m.Stamina = 20
        end
    end
end)
      print("infinite stamina Loaded")
      end,
})
local Slider = Tab:CreateSlider({
   Name = "Set Max Stamina",
   Range = {1, 1000},
   Increment = 5,
   Suffix = "Stamina",
   CurrentValue = 10,
   Flag = "Slider1",
   Callback = function(Value)
       local Sprinting = game:GetService("ReplicatedStorage").Systems.Character.Game.Sprinting
local m = require(Sprinting)
       m.MaxStamina = Value
   end,
})
local Slider = Tab:CreateSlider({
   Name = "Set Stamina Gain",
   Range = {10, 1000},
   Increment = 5,
   Suffix = "Stamina",
   CurrentValue = 10,
   Flag = "Slider1",
   Callback = function(Value)
       local Sprinting = game:GetService("ReplicatedStorage").Systems.Character.Game.Sprinting
local m = require(Sprinting)
       m.StaminaGain = Value
   end,
})
local Slider = Tab:CreateSlider({
   Name = "Set Stamina Loss",
   Range = {0, 10},
   Increment = 5,
   Suffix = "Stamina",
   CurrentValue = 10,
   Flag = "Slider1",
   Callback = function(Value)
       local Sprinting = game:GetService("ReplicatedStorage").Systems.Character.Game.Sprinting
local m = require(Sprinting)
       m.StaminaLoss = value
   end,
})
local Tab = Window:CreateTab("Visual", 4483362458)
local Section = Tab:CreateSection("Esp")
local Button = Tab:CreateButton({
   Name = "Esp Player",
   Callback = function()
       --// Wait for map
workspace:WaitForChild("Map")

local localPlayer = game:GetService("Players").LocalPlayer

--// Function to create the distance Billboard under a character
local function createDistanceBillboard(char)
    if char:FindFirstChild("HumanoidRootPart") and not char:FindFirstChild("DistanceBillboard") then
        local hrp = char:FindFirstChild("HumanoidRootPart")

        local billboard = Instance.new("BillboardGui")
        billboard.Name = "DistanceBillboard"
        billboard.AlwaysOnTop = true
        billboard.Size = UDim2.new(0, 100, 0, 20)
        billboard.StudsOffset = Vector3.new(0, -3, 0) -- BELOW the player
        billboard.Adornee = hrp
        billboard.Parent = char

        local distLabel = Instance.new("TextLabel")
        distLabel.Size = UDim2.new(1, 0, 1, 0)
        distLabel.BackgroundTransparency = 1
        distLabel.Text = "0.0"
        distLabel.TextColor3 = Color3.new(1, 1, 1) -- White
        distLabel.TextScaled = true
        distLabel.Font = Enum.Font.SourceSans
        distLabel.TextSize = 10
        distLabel.Name = "DistanceLabel"
        distLabel.Parent = billboard

        -- Update distance in real-time
        task.spawn(function()
            while billboard.Parent == char and char:FindFirstChild("HumanoidRootPart") do
                local myChar = localPlayer.Character
                if myChar and myChar:FindFirstChild("HumanoidRootPart") then
                    local dist = (hrp.Position - myChar.HumanoidRootPart.Position).Magnitude
                    distLabel.Text = string.format("%.1f studs", dist)
                end
                task.wait(0.5)
            end
        end)
    end
end

--// Monitor characters
local function trackPlayer(player)
    player.CharacterAdded:Connect(function(char)
        char:WaitForChild("HumanoidRootPart", 5)
        createDistanceBillboard(char)
    end)
    if player.Character then
        createDistanceBillboard(player.Character)
    end
end

--// For current and new players
for _, player in pairs(game:GetService("Players"):GetPlayers()) do
    if player ~= localPlayer then
        trackPlayer(player)
    end
end

game:GetService("Players").PlayerAdded:Connect(function(player)
    if player ~= localPlayer then
        trackPlayer(player)
    end
end)
       --// Wait for map
workspace:WaitForChild("Map")

--// Function to add ESP to character
local function createESP(char)
    if char:FindFirstChild("Head") and not char:FindFirstChild("NameESP") then
        local billboard = Instance.new("BillboardGui")
        billboard.Name = "NameESP"
        billboard.AlwaysOnTop = true
        billboard.Size = UDim2.new(0, 100, 0, 20)
        billboard.StudsOffset = Vector3.new(0, 2.5, 0)
        billboard.Adornee = char:FindFirstChild("Head")
        billboard.Parent = char

        local label = Instance.new("TextLabel")
        label.Size = UDim2.new(1, 0, 1, 0)
        label.BackgroundTransparency = 1
        label.Text = char.Name
        label.TextColor3 = Color3.new(1, 1, 1)
        label.TextScaled = true
        label.Font = Enum.Font.SourceSans
        label.TextSize = 10 -- small text
        label.Parent = billboard
    end
end

--// Function to hook character spawns
local function trackPlayer(player)
    player.CharacterAdded:Connect(function(char)
        char:WaitForChild("Head", 5)
        createESP(char)
    end)
    if player.Character then
        createESP(player.Character)
    end
end

--// Initial players
for _, player in pairs(game:GetService("Players"):GetPlayers()) do
    trackPlayer(player)
end

--// New players
game:GetService("Players").PlayerAdded:Connect(function(player)
    trackPlayer(player)
end)

--// Optional: Re-apply ESP every few seconds in case it gets removed (anti-ESP safe)
task.spawn(function()
    while true do
        for _, player in pairs(game:GetService("Players"):GetPlayers()) do
            local char = player.Character
            if char and char:FindFirstChild("Head") and not char:FindFirstChild("NameESP") then
                createESP(char)
            end
        end
        task.wait(5)
    end
end)
   end,
})
local Button = Tab:CreateButton({
   Name = "Esp Item",
   Callback = function()
 local ws = cloneref(game:GetService("Workspace"))

local function addLabel(tool)
    if string.lower(tool.Name):find("flag") then return end

    local parentPart = tool:FindFirstChild("Handle") or tool:FindFirstChildWhichIsA("BasePart")
    if not parentPart then return end

    local bb = Instance.new("BillboardGui")
    bb.Name = "ToolLabel"
    bb.Size = UDim2.new(0, 150, 0, 30)
    bb.StudsOffset = Vector3.new(0, 2, 0)
    bb.AlwaysOnTop = true
    bb.MaxDistance = math.huge
    bb.LightInfluence = 0
    bb.Parent = parentPart

    local lbl = Instance.new("TextLabel")
    lbl.Size = UDim2.new(1, 0, 1, 0)
    lbl.BackgroundTransparency = 1
    lbl.TextScaled = true
    lbl.Font = Enum.Font.SourceSansBold
    lbl.TextColor3 = Color3.fromRGB(170, 0, 255) -- Purple color
    lbl.TextStrokeTransparency = 0
    lbl.TextTransparency = 0.5
    lbl.Text = tool.Name
    lbl.Parent = bb
end

for _, tool in ipairs(ws:GetDescendants()) do
    if tool:IsA("Tool") then addLabel(tool) end
end

ws.DescendantAdded:Connect(function(tool)
    if tool:IsA("Tool") then 
        task.wait(0.1) 
        addLabel(tool) 
    end
end)

ws.DescendantRemoving:Connect(function(tool)
    local parentPart = tool:FindFirstChild("Handle") or tool:FindFirstChildWhichIsA("BasePart")
    if parentPart then
        local lbl = parentPart:FindFirstChild("ToolLabel")
        if lbl then lbl:Destroy() end
    end
end)
   end,
})
local Button = Tab:CreateButton({
   Name = "Esp Generator",
   Callback = function()
             local cref = cloneref or function(ref) return ref end
local ts = cref(game:GetService("TweenService"))
local ws = cref(workspace)

local gens, hl = {}, {}

local function getColors(p)
    local progress = math.clamp(p / 100, 0, 1)
    
    -- Color transition logic:
    local fillColor
    if progress < 1 then
        fillColor = Color3.new(1, progress, 0) -- Red (1,0,0) to Yellow (1,1,0)
    else
        fillColor = Color3.new(0, 1, 0) -- Green (0,1,0) at 100%
    end
    
    local outlineColor = fillColor:Lerp(Color3.new(0, 0, 0), 0.3) -- Slightly darker outline

    return fillColor, outlineColor
end

local function updateHL(gen)
    local prog, h = gen:FindFirstChild("Progress"), hl[gen]
    if prog and h then
        local f, o = getColors(prog.Value)
        local speed = math.clamp(1 - (prog.Value / 100), 0.2, 0.5)
        
        local tf = ts:Create(h, TweenInfo.new(speed, Enum.EasingStyle.Linear), {FillColor = f})
        local to = ts:Create(h, TweenInfo.new(speed, Enum.EasingStyle.Linear), {OutlineColor = o})
        tf:Play()
        to:Play()
        
        tf.Completed:Connect(function()
            tf:Destroy()
            to:Destroy()
        end)
    end
end

local function monitorProgress(gen)
    local prog = gen:FindFirstChild("Progress")
    if not prog then return end

    -- Constantly check for changes every 0.1 seconds
    task.spawn(function()
        while gens[gen] and prog do
            updateHL(gen)
            task.wait(0.1) -- Fast detection
        end
    end)
end

local function addGen(obj)
    if obj:IsA("Model") and obj.Name == "Generator" and not gens[obj] then
        gens[obj] = true
        local h = Instance.new("Highlight", obj)
        h.Adornee, hl[obj] = obj, h
        local f, o = getColors(1)
        h.FillColor, h.OutlineColor = f, o
        local prog = obj:FindFirstChild("Progress")
        if prog and prog:IsA("NumberValue") then
            monitorProgress(obj) -- Start the manual detection loop
            updateHL(obj)
        end
    end
end

local function removeGen(obj)
    if gens[obj] then
        gens[obj] = nil
        if hl[obj] then hl[obj]:Destroy() hl[obj] = nil end
    end
end

local function validateGenerators()
    local m = ws:FindFirstChild("Map")
    local gm = m and m:FindFirstChild("Ingame") and m.Ingame:FindFirstChild("Map")
    
    if gm then
        -- Add missing generators
        for _, obj in ipairs(gm:GetChildren()) do
            if obj:IsA("Model") and obj.Name == "Generator" and not gens[obj] then
                addGen(obj)
            end
        end
        
        -- Remove invalid generators
        for obj in pairs(gens) do
            if not obj or not obj.Parent or obj.Parent ~= gm then
                removeGen(obj)
            end
        end
    end
end

-- Loop to continuously check for new or missing generators
task.spawn(function()
    while true do
        validateGenerators()
        task.wait(1) -- Check every 1 second
    end
end)-- The function that takes place when the button is pressed
   end,
})
local Section = Tab:CreateSection("Etc")
local Button = Tab:CreateButton({
   Name = "Health Check",
   Callback = function()
       -- FE-compatible visual health indicators for other players
-- Works in Forsaken and similar games

local player = game.Players.LocalPlayer
local camera = workspace.CurrentCamera

function createBillboard(playerTarget)
    if playerTarget == player then return end -- Skip local player

    local char = playerTarget.Character
    if not char then return end

    if char:FindFirstChild("Head") and char:FindFirstChild("Humanoid") and not char:FindFirstChild("HealthBillboard") then
        local bb = Instance.new("BillboardGui")
        bb.Name = "HealthBillboard"
        bb.Adornee = char.Head
        bb.Size = UDim2.new(4, 0, 0.5, 0)
        bb.StudsOffset = Vector3.new(0, 2.5, 0)
        bb.AlwaysOnTop = true
        bb.Parent = char

        local barBg = Instance.new("Frame", bb)
        barBg.Size = UDim2.new(1, 0, 1, 0)
        barBg.BackgroundColor3 = Color3.new(0, 0, 0)
        barBg.BorderSizePixel = 0

        local bar = Instance.new("Frame", barBg)
        bar.Name = "HealthBar"
        bar.Size = UDim2.new(1, 0, 1, 0)
        bar.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
        bar.BorderSizePixel = 0

        local humanoid = char.Humanoid

        humanoid.HealthChanged:Connect(function()
            local percent = humanoid.Health / humanoid.MaxHealth
            bar.Size = UDim2.new(percent, 0, 1, 0)
            if percent > 0.5 then
                bar.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
            elseif percent > 0.25 then
                bar.BackgroundColor3 = Color3.fromRGB(255, 170, 0)
            else
                bar.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
            end
        end)
    end
end

-- Create for players that already exist
for _, p in pairs(game.Players:GetPlayers()) do
    if p ~= player then
        p.CharacterAdded:Connect(function()
            wait(1)
            createBillboard(p)
        end)
        if p.Character then
            createBillboard(p)
        end
    end
end

-- Detect new players
game.Players.PlayerAdded:Connect(function(p)
    p.CharacterAdded:Connect(function()
        wait(1)
        createBillboard(p)
    end)
end)
       -- FE Visual Health Indicator for Forsaken-type games
-- Made for mobile & PC

-- Remove previous GUI if it exists
pcall(function() game.Players.LocalPlayer.PlayerGui:FindFirstChild("HealthGUI"):Destroy() end)

-- Create GUI
local gui = Instance.new("ScreenGui", game.Players.LocalPlayer:WaitForChild("PlayerGui"))
gui.Name = "HealthGUI"
gui.ResetOnSpawn = false

local background = Instance.new("Frame", gui)
background.Size = UDim2.new(0, 200, 0, 25)
background.Position = UDim2.new(0.5, -100, 0.9, 0)
background.BackgroundColor3 = Color3.new(0.1, 0.1, 0.1)
background.BorderSizePixel = 0
background.AnchorPoint = Vector2.new(0.5, 0.5)

local bar = Instance.new("Frame", background)
bar.Size = UDim2.new(1, 0, 1, 0)
bar.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
bar.BorderSizePixel = 0

local label = Instance.new("TextLabel", background)
label.Size = UDim2.new(1, 0, 1, 0)
label.Text = "Health: 100"
label.BackgroundTransparency = 1
label.TextColor3 = Color3.new(1, 1, 1)
label.TextScaled = true
label.Font = Enum.Font.GothamBold

-- Health update function
local player = game.Players.LocalPlayer
local char = player.Character or player.CharacterAdded:Wait()
local humanoid = char:WaitForChild("Humanoid")

local function updateHealth()
	local health = humanoid.Health
	local maxHealth = humanoid.MaxHealth
	local percent = health / maxHealth
	bar.Size = UDim2.new(percent, 0, 1, 0)
	label.Text = "Health: " .. math.floor(health)

	if percent > 0.5 then
		bar.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
	elseif percent > 0.25 then
		bar.BackgroundColor3 = Color3.fromRGB(255, 170, 0)
	else
		bar.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
	end
end

-- Connect health change
humanoid.HealthChanged:Connect(updateHealth)
updateHealth()

-- In case of respawn
player.CharacterAdded:Connect(function(newChar)
	char = newChar
	humanoid = char:WaitForChild("Humanoid")
	humanoid.HealthChanged:Connect(updateHealth)
	updateHealth()
end)
   end,
})
local Tab = Window:CreateTab("Fun",4483362458)
local Section = Tab:CreateSection("Etc")
local Button = Tab:CreateButton({
   Name = "Dash Button",
   Callback = function()
     local UserInputService = game:GetService("UserInputService")  
local Players = game:GetService("Players")  
local RunService = game:GetService("RunService")  
  
local player = Players.LocalPlayer  
local character = player.Character or player.CharacterAdded:Wait()  
local debounce = false  
local dashPower = 100  
local dashTime = 0.2  
  
-- Fungsi Dash  
local function dash()  
 if debounce then return end  
 debounce = true  
  
 local char = player.Character or player.CharacterAdded:Wait()  
 local hrp = char:WaitForChild("HumanoidRootPart")  
  
 local bv = Instance.new("BodyVelocity")  
 bv.Velocity = hrp.CFrame.LookVector * dashPower  
 bv.MaxForce = Vector3.new(1e5, 0, 1e5)  
 bv.Parent = hrp  
  
 game.Debris:AddItem(bv, dashTime)  
  
 wait(0.5)  
 debounce = false  
end  
  
-- Deteksi PC (Shift)  
UserInputService.InputBegan:Connect(function(input, gameProcessed)  
 if gameProcessed then return end  
 if input.KeyCode == Enum.KeyCode.LeftShift then  
  dash()  
 end  
end)  
  
-- Jika Mobile, buat tombol  
if UserInputService.TouchEnabled and not UserInputService.KeyboardEnabled then  
 local screenGui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))  
 screenGui.Name = "DashGUI"  
 screenGui.ResetOnSpawn = false
  
 local button = Instance.new("TextButton")  
 button.Size = UDim2.new(0, 80, 0, 40)  
 button.Position = UDim2.new(1, -90, 0.5, -20) -- Right center  
 button.Text = "Dash"  
 button.BackgroundColor3 = Color3.fromRGB(30, 144, 255)  
 button.TextColor3 = Color3.new(1, 1, 1)  
 button.Font = Enum.Font.SpecialElite  
 button.TextSize = 18  
 button.Parent = screenGui
 button.Active = true
 button.Draggable = true  
  
 -- RGB effect  
 spawn(function()  
  while true do  
   for i = 0, 1, 0.01 do  
    local color = Color3.fromHSV(i, 1, 1)  
    button.BackgroundColor3 = color  
    wait(0.03)  
   end  
  end  
 end)  
  
 button.MouseButton1Click:Connect(dash)  
end
     print("jwkll")
   end,
})
local Button = Tab:CreateButton({
   Name ="Im Not Gonna Sugarcoat It",
   Callback = function()
       -- FE Frontflip GUI - Top Left & Works After Respawn
local player = game.Players.LocalPlayer

-- GUI Setup
local gui = Instance.new("ScreenGui")
gui.Name = "FrontflipGUI"
gui.ResetOnSpawn = false
gui.Parent = player:WaitForChild("PlayerGui")

local button = Instance.new("ImageButton")
button.Name = "FlipButton"
button.Size = UDim2.new(0, 100, 0, 100)
button.Position = UDim2.new(0, 20, 0, 20) -- Top left corner with some padding
button.Image = "rbxassetid://77415745267974"
button.BackgroundTransparency = 1
button.Parent = gui

local duration = 0.6
local steps = 30
local FlipCooldown = false

-- Flip Function
local function doFrontflip()
	if FlipCooldown then return end

	local char = player.Character
	local humanoid = char and char:FindFirstChildWhichIsA("Humanoid")
	local hrp = char and char:FindFirstChild("HumanoidRootPart")
	if not char or not humanoid or not hrp then return end

	FlipCooldown = true

	local animator = humanoid:FindFirstChildOfClass("Animator")
	local startCFrame = hrp.CFrame
	local forwardVector = startCFrame.LookVector
	local upVector = Vector3.new(0, 1, 0)

	humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
	humanoid:SetStateEnabled(Enum.HumanoidStateType.Freefall, false)
	humanoid:SetStateEnabled(Enum.HumanoidStateType.Running, false)
	humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
	humanoid:SetStateEnabled(Enum.HumanoidStateType.Climbing, false)

	local savedTracks = {}
	if animator then
		for _, track in ipairs(animator:GetPlayingAnimationTracks()) do
			table.insert(savedTracks, {track = track, time = track.TimePosition})
			track:Stop()
		end
	end

	task.spawn(function()
		local startTime = tick()
		for i = 1, steps do
			local t = i / steps
			local height = 4 * (t - t ^ 2) * 10
			local nextPos = startCFrame.Position + forwardVector * (35 * t) + upVector * height
			local rotation = startCFrame.Rotation * CFrame.Angles(-math.rad(i * (360 / steps)), 0, 0)
			hrp.CFrame = CFrame.new(nextPos) * rotation

			local elapsedTime = tick() - startTime
			local expectedTime = (duration / steps) * i
			local waitTime = expectedTime - elapsedTime
			if waitTime > 0 then task.wait(waitTime) end
		end

		hrp.CFrame = CFrame.new(startCFrame.Position + forwardVector * 35) * startCFrame.Rotation

		humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, true)
		humanoid:SetStateEnabled(Enum.HumanoidStateType.Freefall, true)
		humanoid:SetStateEnabled(Enum.HumanoidStateType.Running, true)
		humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
		humanoid:SetStateEnabled(Enum.HumanoidStateType.Climbing, true)
		humanoid:ChangeState(Enum.HumanoidStateType.Running)

		if animator then
			for _, data in ipairs(savedTracks) do
				local track = data.track
				track:Play()
				track.TimePosition = data.time
			end
		end

		task.wait(0.25)
		FlipCooldown = false
	end)
end

-- Ensure Button Works on Respawn
local function setupButton()
	button.MouseButton1Click:Connect(doFrontflip)
end

setupButton()

-- Reconnect after character respawn
player.CharacterAdded:Connect(function()
	task.wait(1)
	setupButton()
end)
   end,
})

local Button = Tab:CreateButton({
   Name = "Custom Jason",
   Callback = function()
       local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local SoundService = game:GetService("SoundService")
local Player = Players.LocalPlayer

-- Function to play a sound
local function playSound(soundId)
    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://" .. tostring(soundId)
    sound.Volume = 1
    sound.Looped = false
    sound.Parent = SoundService
    sound:Play()
end

-- Watch character for "Stunned" effect
local function watchForStunEffect(character)
    character.DescendantAdded:Connect(function(descendant)
        if descendant.Name == "Stunned" then
            playSound(17496290473) -- Ichigo scream for stunned
        end
    end)

    for _, desc in ipairs(character:GetDescendants()) do
        if desc.Name == "Stunned" then
            playSound(17496290473)
        end
    end
end

Player.CharacterAdded:Connect(watchForStunEffect)
if Player.Character then
    watchForStunEffect(Player.Character)
end

-- Bind ability button sounds
local function bindButtonSound(buttonName, soundId)
    local success, gui = pcall(function()
        return Player:WaitForChild("PlayerGui"):WaitForChild("MainUI"):WaitForChild("AbilityContainer"):WaitForChild(buttonName)
    end)

    if success and (gui:IsA("TextButton") or gui:IsA("ImageButton")) then
        gui.MouseButton1Click:Connect(function()
            playSound(soundId)
        end)
    end
end

-- Updated sound IDs
bindButtonSound("RagingPace", 12222225)
bindButtonSound("Slash", 7953014104)
bindButtonSound("Behead", 18884968375)
bindButtonSound("GashingWound", 18884968832)

-- Replace sound ID in ReplicatedStorage
local function replaceReplicatedSound()
    local soundsFolder = ReplicatedStorage:WaitForChild("Assets"):WaitForChild("Sounds")
    local oldId = "rbxassetid://125611325245826"
    local newId = "rbxassetid://1848090337"

    local function replaceIfNeeded(sound)
        if sound:IsA("Sound") and sound.SoundId == oldId then
            sound.SoundId = newId
            warn("Replaced ReplicatedStorage sound ID:", sound.Name)
        end
    end

    for _, sound in ipairs(soundsFolder:GetChildren()) do
        replaceIfNeeded(sound)
    end

    soundsFolder.ChildAdded:Connect(replaceIfNeeded)
end

-- Replace and monitor workspace sound
local function replaceWorkspaceSound()
    local soundsFolder = workspace:WaitForChild("Sounds")
    local oldId = "rbxassetid://70658180298709"
    local newId = "rbxassetid://99818660648586"

    local function replaceIfNeeded(sound)
        if sound:IsA("Sound") and sound.SoundId == oldId then
            sound.SoundId = newId
            warn("Replaced workspace sound ID:", sound.Name)
        end
    end

    for _, sound in ipairs(soundsFolder:GetChildren()) do
        replaceIfNeeded(sound)
    end

    soundsFolder.ChildAdded:Connect(replaceIfNeeded)
end

-- Run replacements
replaceReplicatedSound()
replaceWorkspaceSound()

-- Appearance customization
local character = Player.Character or Player.CharacterAdded:Wait()
local bodyColors = character:FindFirstChild("Body Colors")
if bodyColors then
    local black = BrickColor.new("Really black")
    bodyColors.HeadColor = black
    bodyColors.LeftArmColor = black
    bodyColors.RightArmColor = black
    bodyColors.LeftLegColor = black
    bodyColors.RightLegColor = black
    bodyColors.TorsoColor = black
end

-- Apply shirt and pants
local shirt = character:FindFirstChildOfClass("Shirt") or Instance.new("Shirt", character)
shirt.ShirtTemplate = "http://www.roblox.com/asset/?id=144076759"

local pants = character:FindFirstChildOfClass("Pants") or Instance.new("Pants", character)
pants.PantsTemplate = "http://www.roblox.com/asset/?id=2864356251"

-- Head visibility (optional)
local head = character:FindFirstChild("Head")
if head then
    head.Transparency = 0
end-- The function that takes place when the button is pressed
   end,
})
local Input = Tab:CreateInput({
   Name = "Sprint Speed",
   CurrentValue = "24",
   PlaceholderText = "Sprint Speed",
   RemoveTextAfterFocusLost = false,
   Flag = "Input1",
   Callback = function(Text)
   local Sprinting = game:GetService("ReplicatedStorage").Systems.Character.Game.Sprinting
local m = require(Sprinting)
       m.SprintSpeed = Text-- The function that takes place when the input is changed
   -- The variable (Text) is a string for the value in the text box
   end,
})
local Button = Tab:CreateButton({
   Name = "Play Close To Me Button",
   Callback = function()
       -- Always creates a new Sound to ensure it plays

local player = game.Players.LocalPlayer
local gui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
gui.ResetOnSpawn = false
gui.Name = "CloseToMeButtonGui"

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 160, 0, 50)
frame.Position = UDim2.new(1, -180, 0.4, 0)
frame.BackgroundColor3 = Color3.fromRGB(255, 105, 180)
frame.BorderSizePixel = 0
frame.Parent = gui

local gradient = Instance.new("UIGradient", frame)
gradient.Color = ColorSequence.new{
	ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 105, 180)),
	ColorSequenceKeypoint.new(1, Color3.fromRGB(255, 20, 60))
}

local button = Instance.new("TextButton")
button.Size = UDim2.new(1, 0, 1, 0)
button.Text = "★ Play Close to me ★"
button.BackgroundTransparency = 1
button.TextColor3 = Color3.new(1, 1, 1)
button.Font = Enum.Font.GothamBlack
button.TextSize = 16
button.TextStrokeTransparency = 0.1
button.TextStrokeColor3 = Color3.fromRGB(80, 0, 80)
button.Parent = frame

-- Cooldown
local isCooldown = false

button.MouseButton1Click:Connect(function()
	if not isCooldown then
		isCooldown = true

		-- Create a new sound each time
		local sound = Instance.new("Sound")
		sound.SoundId = "rbxassetid://90022574613230"
		sound.Volume = 1
		sound.Parent = workspace
		sound:Play()

		-- Auto-destroy the sound after it's done
		sound.Ended:Connect(function()
			sound:Destroy()
		end)

		button.Text = "Cooldown (70s)"
		for i = 69, 1, -1 do
			wait(1)
			button.Text = "Cooldown (" .. i .. "s)"
		end

		button.Text = "★ Play Close to me ★"
		isCooldown = false
	end
end)
   end,
})
local Button = Tab:CreateButton({
   Name = "Play Close To Me Button",
   Callback = function()

