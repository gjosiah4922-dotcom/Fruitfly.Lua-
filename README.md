-- 🪰 FRUIT FLY BRAIN
-- Observe → Think → Decide → Act

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")

local player = Players.LocalPlayer
local gui = Instance.new("ScreenGui")
gui.Name = "FruitFlyBrain"
gui.ResetOnSpawn = false
gui.Parent = player:WaitForChild("PlayerGui")

local panel = Instance.new("TextLabel")
panel.Size = UDim2.fromOffset(300, 190)
panel.Position = UDim2.fromOffset(15, 15)
panel.BackgroundColor3 = Color3.fromRGB(15,15,20)
panel.TextColor3 = Color3.new(1,1,1)
panel.TextSize = 15
panel.Font = Enum.Font.Code
panel.TextXAlignment = Enum.TextXAlignment.Left
panel.TextYAlignment = Enum.TextYAlignment.Top
panel.Text = "🪰 FRUIT FLY BRAIN\n\nLoading..."
panel.Parent = gui

local character
local humanoid
local root

local Brain = {
    status = "BOOTING",
    activity = 0,
    stability = 0,
    confidence = 0,
    goal = "Initializing",
    decision = "None",
    target = nil
}

local function setup()
    character = player.Character or player.CharacterAdded:Wait()
    humanoid = character:WaitForChild("Humanoid")
    root = character:WaitForChild("HumanoidRootPart")
end

setup()

player.CharacterAdded:Connect(function()
    task.wait(1)
    setup()
end)

local function display()
    panel.Text =
        "🪰 FRUIT FLY BRAIN\n\n" ..
        "STATUS: " .. Brain.status .. "\n" ..
        "ACTIVITY: " .. math.floor(Brain.activity) .. "%\n" ..
        "STABILITY: " .. math.floor(Brain.stability) .. "%\n" ..
        "CONFIDENCE: " .. math.floor(Brain.confidence) .. "%\n\n" ..
        "GOAL: " .. Brain.goal .. "\n" ..
        "DECISION: " .. Brain.de
