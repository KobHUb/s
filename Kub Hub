local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "🥶 Kob Hub | #silaskid🥶",
   LoadingTitle = "😈Kob Hub Loading....😈",
   LoadingSubtitle = "by #silaskid",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = true,
      Invite = "2p3aza4HCz", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = false -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "🔑 Kob Hub | Key 🔑",
      Subtitle = "🔑 Key System 🔑",
      Note = "Get Key In discord https://discord.gg/2p3aza4HCz",
      FileName = "Kob Hub Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = true, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"https://pastebin.com/raw/cM35CfPJ"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})
Rayfield:Notify({
   Title = "Kob Hub On Top",
   Content = "You Executed Kub Hub",
   Duration = 5,
   Image = nil,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay",
         Callback = function()
         print("The user tapped Okay!")
      end
   },
},
})


local MainTab = Window:CreateTab("Player👲", nil) -- Title, Image

local MainSection = MainTab:CreateSection("Player 👲")

local Button = MainTab:CreateButton({
   Name = "infinite jump (CLICK F)",
   Callback = function()
        -- //~ F to toggle ~\\ --
 
_G.infinjump = true
 
local Player = game:GetService("Players").LocalPlayer
local Mouse = Player:GetMouse()
Mouse.KeyDown:connect(function(k)
if _G.infinjump then
if k:byte() == 32 then
Humanoid = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
Humanoid:ChangeState("Jumping")
wait(0.1)
Humanoid:ChangeState("Seated")
end
end
end)
 
local Player = game:GetService("Players").LocalPlayer
local Mouse = Player:GetMouse()
Mouse.KeyDown:connect(function(k)
k = k:lower()
if k == "f" then
if _G.infinjump == true then
_G.infinjump = false
else
_G.infinjump = true
end
end
end)

   end,
})

local Toggle = MainTab:CreateToggle({
   Name = "infinite yield",
   CurrentValue = false,
   Flag = "infinite yield", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
   end,
})

local Slider = MainTab:CreateSlider({
   Name = "Walkspeed",
   Range = {0, 500},
   Increment = 1,
   Suffix = "Walkspeed",
   CurrentValue = 10,
   Flag = "Walkspeed", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
         game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
        end,
})

local Slider = MainTab:CreateSlider({
   Name = "JumpPower",
   Range = {0, 300},
   Increment = 1,
   Suffix = "JumpPower",
   CurrentValue = 10,
   Flag = "JumpPower", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = (Value)
   end,
})

local GameTab = Window:CreateTab("🕹️ Game", nil) -- Title, Image

local Section = GameTab:CreateSection("🕹️ Game 🕹️")


local Button = GameTab:CreateButton({
   Name = "Btools (CLICK P)",
   Callback = function()
local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
 
mouse.KeyDown:connect(function(key)
    key = string.lower(key)
 
	if key == "p" then
		for item = 1, 4 do
			HopperBin = Instance.new("HopperBin", game.Players.LocalPlayer.Backpack)
			HopperBin.BinType = item
		end
	elseif key == "l" then
		function UnlockWorkspace(a)
			for n,part in pairs(a:GetChildren()) do
				if(part:IsA("BasePart")) then 
					part.Locked = false 
				end
				UnlockWorkspace(part)
			end
		end
		UnlockWorkspace(workspace)
	elseif key == "k" then
		local StarterGui = game:GetService("StarterGui")
		StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.All, true)
	end
end)
 

   end,
})

local Toggle = GameTab:CreateToggle({
   Name = "🤖 Aimbot (click X)🤖",
   CurrentValue = false,
   Flag = "🤖 Aimbot 🤖", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
        -- Made By Hugbif4
-- Variables
local player = game.Players.LocalPlayer
local camera = workspace.CurrentCamera
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local aimAssistEnabled = false
local targetPlayer = nil

-- Function to find the closest target
local function findClosestTarget()
	local closestTarget = nil
	local shortestDistance = math.huge

	for _, target in pairs(game.Players:GetPlayers()) do
		if target ~= player and target.Character and target.Character:FindFirstChild("Head") then
			local targetPos = target.Character.Head.Position
			local screenPos, onScreen = camera:WorldToScreenPoint(targetPos)

			if onScreen then
				local mousePos = UserInputService:GetMouseLocation()
				local distance = (Vector2.new(mousePos.X, mousePos.Y) - Vector2.new(screenPos.X, screenPos.Y)).magnitude
				if distance < shortestDistance then
					shortestDistance = distance
					closestTarget = target
				end
			end
		end
	end

	return closestTarget
end

-- Function to lock the camera onto the target
local function lockCameraOntoTarget(targetPlayer)
	if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("Head") then
		local targetPos = targetPlayer.Character.Head.Position
		camera.CFrame = CFrame.new(camera.CFrame.Position, targetPos)
	end
end

-- Enable aim assist when "X" is pressed
UserInputService.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == Enum.KeyCode.X then
		aimAssistEnabled = true
		targetPlayer = findClosestTarget()
		if targetPlayer then
			print("Aim assist enabled. Locked onto: " .. targetPlayer.Name)
		else
			print("No target found")
		end
	end
end)

-- Disable aim assist when "X" is released
UserInputService.InputEnded:Connect(function(input)
	if input.KeyCode == Enum.KeyCode.X then
		aimAssistEnabled = false
		targetPlayer = nil
		print("Aim assist disabled")
	end
end)

-- Update camera lock if aim assist is enabled
RunService.RenderStepped:Connect(function()
	if aimAssistEnabled and targetPlayer then
		lockCameraOntoTarget(targetPlayer)
	end
end)


   end,
})
