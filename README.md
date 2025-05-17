local Players = game:GetService("Players")
local player = Players.LocalPlayer

local adminGui = Instance.new("ScreenGui")
adminGui.Name = "AdminPanel"
adminGui.ResetOnSpawn = false
adminGui.Parent = player:WaitForChild("PlayerGui")

local panel = Instance.new("Frame")
panel.Size = UDim2.new(0, 400, 0, 300)
panel.Position = UDim2.new(0.5, -200, 0.5, -150)
panel.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
panel.BackgroundTransparency = 0.2
panel.BorderSizePixel = 0
panel.Parent = adminGui

local username = Instance.new("TextLabel")
username.Size = UDim2.new(1, 0, 0, 50)
username.Position = UDim2.new(0, 0, 0, 0)
username.BackgroundTransparency = 1
username.Text = "toast  |  Guest\n@blve_hxrizon\n1883128632"
username.TextColor3 = Color3.fromRGB(255, 255, 255)
username.TextWrapped = true
username.TextYAlignment = Enum.TextYAlignment.Top
username.Font = Enum.Font.SourceSansBold
username.TextSize = 18
username.Parent = panel

local actions = {"Ban", "Configure", "Kick", "Mute", "Notify", "View More"}
for i, action in ipairs(actions) do
	local btn = Instance.new("TextButton")
	btn.Size = UDim2.new(0.4, 0, 0, 30)
	btn.Position = UDim2.new(0.05, 0, 0, 60 + (i - 1) * 35)
	btn.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
	btn.TextColor3 = Color3.fromRGB(255, 255, 255)
	btn.Text = action
	btn.Font = Enum.Font.SourceSans
	btn.TextSize = 16
	btn.Parent = panel

	btn.MouseButton1Click:Connect(function()
		print(action .. " clicked for user toast.")
	end)
end

local eventLog = Instance.new("TextLabel")
eventLog.Size = UDim2.new(0.45, 0, 0.35, 0)
eventLog.Position = UDim2.new(0.5, 0, 0.6, 0)
eventLog.BackgroundTransparency = 1
eventLog.TextColor3 = Color3.fromRGB(180, 180, 180)
eventLog.Text = "Joined\nChatted \"Hello!\"\nKicked\nJoined\nLeft\nJoined\nCharacter Reset"
eventLog.TextWrapped = true
eventLog.TextYAlignment = Enum.TextYAlignment.Top
eventLog.Font = Enum.Font.Code
eventLog.TextSize = 14
eventLog.TextXAlignment = Enum.TextXAlignment.Left
eventLog.Parent = panel
