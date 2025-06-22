local player = game.Players.LocalPlayer

local gui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
gui.Name = "TestMenu"

local frame = Instance.new("Frame", gui)
frame.Size = UDim2.new(0, 300, 0, 360)
frame.Position = UDim2.new(0.5, -150, 0.5, -180)
frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
frame.BorderSizePixel = 0
frame.Active = true
frame.Draggable = true

local image = Instance.new("ImageLabel", frame)
image.Size = UDim2.new(0, 260, 0, 200)
image.Position = UDim2.new(0.5, -130, 0, 10)
image.BackgroundTransparency = 1
image.Image = "rbxassetid://155788288"

local helloBtn = Instance.new("TextButton", frame)
helloBtn.Size = UDim2.new(0, 260, 0, 50)
helloBtn.Position = UDim2.new(0.5, -130, 0, 220)
helloBtn.Text = "Say Hello"
helloBtn.BackgroundColor3 = Color3.fromRGB(0, 170, 255)
helloBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
helloBtn.Font = Enum.Font.GothamBold
helloBtn.TextSize = 20

helloBtn.MouseButton1Click:Connect(function()
	game.StarterGui:SetCore("ChatMakeSystemMessage", {
		Text = "👋 Hello there!";
		Color = Color3.fromRGB(0, 255, 0);
		Font = Enum.Font.SourceSansBold;
		FontSize = Enum.FontSize.Size24;
	})
end)

local teleportBtn = Instance.new("TextButton", frame)
teleportBtn.Size = UDim2.new(0, 260, 0, 50)
teleportBtn.Position = UDim2.new(0.5, -130, 0, 280)
teleportBtn.Text = "Teleport"
teleportBtn.BackgroundColor3 = Color3.fromRGB(255, 100, 100)
teleportBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
teleportBtn.Font = Enum.Font.GothamBold
teleportBtn.TextSize = 20

teleportBtn.MouseButton1Click:Connect(function()
	local placeId = 8737602449
	game:GetService("TeleportService"):Teleport(placeId, player)
end)
