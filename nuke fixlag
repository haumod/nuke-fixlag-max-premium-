repeat task.wait() until game:IsLoaded()
local Players = game:GetService("Players")
local Lighting = game:GetService("Lighting")
local Workspace = game:GetService("Workspace")
local RunService = game:GetService("RunService")
local Stats = game:GetService("Stats")
local TweenService = game:GetService("TweenService")
local Terrain = Workspace:FindFirstChildOfClass("Terrain")

local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

pcall(function()
	if playerGui:FindFirstChild("NUKE_FINAL") then
		playerGui.NUKE_FINAL:Destroy()
	end
end)

local glitch = false
local showHUD = true
local hue = 0

local originalData = {
	Lighting = {},
	Parts = {},
	MeshParts = {},
	Unions = {},
	Terrain = {}
}

local function SaveOriginal()
	pcall(function()
		originalData.Lighting.Brightness = Lighting.Brightness
		originalData.Lighting.Ambient = Lighting.Ambient
		originalData.Lighting.OutdoorAmbient = Lighting.OutdoorAmbient
		originalData.Lighting.ClockTime = Lighting.ClockTime
		originalData.Lighting.FogEnd = Lighting.FogEnd
		originalData.Lighting.GlobalShadows = Lighting.GlobalShadows
		originalData.Lighting.EnvironmentDiffuseScale = Lighting.EnvironmentDiffuseScale
		originalData.Lighting.EnvironmentSpecularScale = Lighting.EnvironmentSpecularScale
		originalData.Lighting.ShadowSoftness = Lighting.ShadowSoftness
		originalData.Lighting.Technology = Lighting.Technology
		originalData.QualityLevel = settings().Rendering.QualityLevel
		originalData.MeshPartDetailLevel = settings().Rendering.MeshPartDetailLevel
		
		if Terrain then
			originalData.Terrain.WaterWaveSize = Terrain.WaterWaveSize
			originalData.Terrain.WaterWaveSpeed = Terrain.WaterWaveSpeed
			originalData.Terrain.WaterReflectance = Terrain.WaterReflectance
			originalData.Terrain.WaterTransparency = Terrain.WaterTransparency
		end
		
		for _, obj in pairs(Workspace:GetDescendants()) do
			if obj:IsA("BasePart") and not obj:IsA("Terrain") then
				originalData.Parts[obj] = {
					Color = obj.Color,
					Material = obj.Material,
					Reflectance = obj.Reflectance,
					CastShadow = obj.CastShadow,
					Transparency = obj.Transparency
				}
			elseif obj:IsA("MeshPart") then
				originalData.MeshParts[obj] = {
					TextureID = obj.TextureID,
					RenderFidelity = obj.RenderFidelity,
					CollisionFidelity = obj.CollisionFidelity
				}
			elseif obj:IsA("UnionOperation") then
				originalData.Unions[obj] = {
					RenderFidelity = obj.RenderFidelity,
					CollisionFidelity = obj.CollisionFidelity,
					UsePartColor = obj.UsePartColor
				}
			end
		end
	end)
end
SaveOriginal()

local gui = Instance.new("ScreenGui")
gui.Name = "NUKE_FINAL"
gui.ResetOnSpawn = false
gui.IgnoreGuiInset = true
gui.Parent = playerGui

-- INTRO TEXT
local intro = Instance.new("TextLabel")
intro.Size = UDim2.new(1,0,1,0)
intro.BackgroundTransparency = 1
intro.Text = "cali cc tuổi lồn"
intro.Font = Enum.Font.Arcade
intro.TextSize = 40
intro.TextColor3 = Color3.fromRGB(255,0,0)
intro.TextStrokeTransparency = 0
intro.TextStrokeColor3 = Color3.fromRGB(0,0,0)
intro.ZIndex = 10
intro.Parent = gui

local main = Instance.new("Frame")
main.Size = UDim2.new(0,240,0,310)
main.Position = UDim2.new(0.5,-120,0.5,-155)
main.BackgroundColor3 = Color3.fromRGB(20,20,20)
main.BorderSizePixel = 0
main.Active = true
main.Draggable = true
main.Visible = false
main.Parent = gui
Instance.new("UICorner", main)

local title = Instance.new("TextLabel")
title.Name = "Rainbow"
title.Size = UDim2.new(1,0,0,35)
title.BackgroundTransparency = 1
title.Text = "nuke mod - fixlag max premium 💎"
title.Font = Enum.Font.Arcade
title.TextSize = 14
title.TextColor3 = Color3.fromRGB(255,0,0)
title.Parent = main

local contact = Instance.new("TextLabel")
contact.Size = UDim2.new(1,0,0,20)
contact.Position = UDim2.new(0,0,0,35)
contact.BackgroundTransparency = 1
contact.Text = "TikTok: haumodlag | Zalo: 0586884767"
contact.Font = Enum.Font.Gotham
contact.TextSize = 9
contact.TextColor3 = Color3.fromRGB(150,150,150)
contact.Parent = main

local fpsLeft = Instance.new("TextLabel")
fpsLeft.Name = "Rainbow"
fpsLeft.Size = UDim2.new(0,70,0,20)
fpsLeft.Position = UDim2.new(0.5,-120,0.5,-180)
fpsLeft.BackgroundTransparency = 0.3
fpsLeft.BackgroundColor3 = Color3.fromRGB(0,0,0)
fpsLeft.Font = Enum.Font.SourceSansBold
fpsLeft.TextSize = 14
fpsLeft.Text = "FPS: 0"
fpsLeft.TextXAlignment = Enum.TextXAlignment.Center
fpsLeft.Visible = false
fpsLeft.Parent = gui
Instance.new("UICorner", fpsLeft)

local fpsRight = Instance.new("TextLabel")
fpsRight.Name = "Rainbow"
fpsRight.Size = UDim2.new(0,70,0,20)
fpsRight.Position = UDim2.new(0.5,50,0.5,-180)
fpsRight.BackgroundTransparency = 0.3
fpsRight.BackgroundColor3 = Color3.fromRGB(0,0,0)
fpsRight.Font = Enum.Font.SourceSansBold
fpsRight.TextSize = 14
fpsRight.Text = "MS: 0"
fpsRight.TextXAlignment = Enum.TextXAlignment.Center
fpsRight.Visible = false
fpsRight.Parent = gui
Instance.new("UICorner", fpsRight)

-- INTRO 3 DÒNG - MỖI DÒNG 4S
task.spawn(function()
	task.wait(0.5)
	-- DÒNG 1: MÀU ĐỎ BÌNH THƯỜNG
	intro.Text = "cali cc tuổi lồn"
	intro.TextColor3 = Color3.fromRGB(255,0,0)
	intro.Name = ""
	intro.TextSize = 40
	TweenService:Create(intro, TweenInfo.new(0.3), {TextSize = 50}):Play()
	task.wait(4)
	
	-- DÒNG 2: RAINBOW
	intro.Text = "VN muôn năm 💎"
	intro.Name = "RainbowIntro" -- để rainbow riêng
	intro.TextSize = 40
	TweenService:Create(intro, TweenInfo.new(0.3), {TextSize = 50}):Play()
	task.wait(4)
	
	-- DÒNG 3: MÀU ĐỎ BÌNH THƯỜNG
	intro.Text = "cali dell có trình"
	intro.TextColor3 = Color3.fromRGB(255,0,0)
	intro.Name = ""
	intro.TextSize = 40
	TweenService:Create(intro, TweenInfo.new(0.3), {TextSize = 50}):Play()
	task.wait(4)
	
	-- FADE OUT INTRO
	local tween1 = TweenService:Create(intro, TweenInfo.new(0.5), {TextTransparency = 1, TextStrokeTransparency = 1})
	tween1:Play()
	tween1.Completed:Wait()
	intro:Destroy()
	
	-- HIỆN MENU + FPS
	main.Visible = true
	fpsLeft.Visible = true
	fpsRight.Visible = true
	main.BackgroundTransparency = 1
	title.TextTransparency = 1
	contact.TextTransparency = 1
	
	local tween2 = TweenService:Create(main, TweenInfo.new(0.3), {BackgroundTransparency = 0})
	local tween3 = TweenService:Create(title, TweenInfo.new(0.3), {TextTransparency = 0})
	local tween4 = TweenService:Create(contact, TweenInfo.new(0.3), {TextTransparency = 0})
	tween2:Play()
	tween3:Play()
	tween4:Play()
end)

-- RAINBOW CHO MENU + DÒNG 2 INTRO
RunService.Heartbeat:Connect(function()
	hue = (hue + 0.01) % 1
	local color = Color3.fromHSV(hue, 1, 1)
	for _, obj in pairs(gui:GetDescendants()) do
		if obj.Name == "Rainbow" or obj.Name == "RainbowIntro" then
			obj.TextColor3 = color
		end
	end
end)

local frames = 0
RunService.RenderStepped:Connect(function()
	frames = frames + 1
end)

task.spawn(function()
	while task.wait(1) do
		local ping = 0
		pcall(function()
			ping = Stats.Network.ServerStatsItem["Data Ping"]:GetValue()
		end)
		fpsLeft.Visible = showHUD
		fpsRight.Visible = showHUD
		fpsLeft.Text = "FPS: "..frames
		fpsRight.Text = "MS: "..math.floor(ping)
		frames = 0
	end
end)

local function GrayCharacter(char)
	if not char then return end
	for _,v in pairs(char:GetDescendants()) do
		if v:IsA("Accessory") or v:IsA("Shirt") or v:IsA("Pants") or v:IsA("ShirtGraphic") or v:IsA("CharacterMesh") or v:IsA("Decal") or v:IsA("BodyColors") then
			v:Destroy()
		elseif v:IsA("BasePart") then
			v.Material = Enum.Material.SmoothPlastic
			v.Color = Color3.fromRGB(100,100,100)
			v.Reflectance = 0
			v.Transparency = 0
		elseif v:IsA("SpecialMesh") then
			v.TextureId = ""
			v.MeshId = ""
			v.VertexColor = Vector3.new(0.4,0.4)
		end
	end
	local head = char:FindFirstChild("Head")
	if head then
		for _,d in pairs(head:GetChildren()) do
			if d:IsA("Decal") or d.Name == "face" then d:Destroy() end
		end
	end
end

Players.PlayerAdded:Connect(function(plr)
	plr.CharacterAdded:Connect(function(char)
		task.wait(1)
		GrayCharacter(char)
	end)
end)

for _,plr in pairs(Players:GetPlayers()) do
	plr.CharacterAdded:Connect(function(char)
		task.wait(1)
		GrayCharacter(char)
	end)
	if plr.Character then
		GrayCharacter(plr.Character)
	end
end

-- FIX LAG MAX - XÓA RÁC + TỐI ƯU SÂU
local function FixLagMax()
	pcall(function()
		local count = 0
		
		-- XÓA TẤT CẢ RÁC
		for _, obj in pairs(Workspace:GetDescendants()) do
			if obj:IsA("ParticleEmitter") or obj:IsA("Fire") or obj:IsA("Smoke") or obj:IsA("Sparkles") or obj:IsA("Explosion") then
				obj:Destroy()
				count = count + 1
			elseif obj:IsA("Trail") or obj:IsA("Beam") then
				obj:Destroy()
				count = count + 1
			elseif obj:IsA("Decal") or obj:IsA("Texture") then
				obj:Destroy()
				count = count + 1
			elseif obj:IsA("PointLight") or obj:IsA("SpotLight") or obj:IsA("SurfaceLight") then
				obj:Destroy()
				count = count + 1
			elseif obj:IsA("Sound") then
				obj.Volume = 0
			end
		end
		
		-- TỐI ƯU RENDERING
		settings().Rendering.QualityLevel = 1
		settings().Rendering.MeshPartDetailLevel = Enum.MeshPartDetailLevel.Level01
		UserSettings():GetService("UserGameSettings").SavedQualityLevel = 1
		sethiddenproperty(Lighting, "Technology", Enum.Technology.Compatibility)
		
		-- TẮT TẤT CẢ HIỆU ỨNG
		for _, v in pairs(Lighting:GetChildren()) do
			if v:IsA("PostEffect") or v:IsA("BloomEffect") or v:IsA("BlurEffect") or v:IsA("SunRaysEffect") then
				v.Enabled = false
			end
			if v:IsA("Atmosphere") then v:Destroy() end
		end
		
		-- TỐI ƯU TERRAIN
		if Terrain then
			Terrain.WaterWaveSize = 0
			Terrain.WaterWaveSpeed = 0
			Terrain.WaterReflectance = 0
			Terrain.WaterTransparency = 1
			Terrain.Decoration = false
			sethiddenproperty(Terrain,"Decoration",false)
		end
		
		-- TỐI ƯU TẤT CẢ PART
		for _, obj in pairs(Workspace:GetDescendants()) do
			if obj:IsA("BasePart") and not obj:IsA("Terrain") then
				obj.Material = Enum.Material.SmoothPlastic
				obj.Reflectance = 0
				obj.CastShadow = false
			elseif obj:IsA("MeshPart") then
				obj.RenderFidelity = Enum.RenderFidelity.Performance
				obj.CollisionFidelity = Enum.CollisionFidelity.Box
				obj.TextureID = ""
			elseif obj:IsA("UnionOperation") then
				obj.RenderFidelity = Enum.RenderFidelity.Performance
				obj.CollisionFidelity = Enum.CollisionFidelity.Box
			end
		end
		
		game.StarterGui:SetCore("SendNotification",{
			Title = "FIX LAG MAX 💎";
			Text = "Đã xóa "..count.." rác + tối ưu max";
			Duration = 3;
		})
	end)
end

-- NUKE MODE - SÁNG HƠN 1 TÍ THÔI
local function NukeMode()
	pcall(function()
		settings().Rendering.QualityLevel = 1
		settings().Rendering.MeshPartDetailLevel = Enum.MeshPartDetailLevel.Level01
		UserSettings():GetService("UserGameSettings").SavedQualityLevel = 1
		sethiddenproperty(Lighting, "Technology", Enum.Technology.Compatibility)
		
		Lighting.GlobalShadows = false
		Lighting.FogEnd = 9e9
		Lighting.FogStart = 0
		Lighting.Brightness = 1.5
		Lighting.Ambient = Color3.fromRGB(90,90,90)
		Lighting.OutdoorAmbient = Color3.fromRGB(90,90,90)
		Lighting.EnvironmentDiffuseScale = 0
		Lighting.EnvironmentSpecularScale = 0
		Lighting.ShadowSoftness = 0
		Lighting.ClockTime = 17
		
		for _, v in pairs(Lighting:GetChildren()) do
			if v:IsA("PostEffect") or v:IsA("BloomEffect") or v:IsA("BlurEffect") or v:IsA("SunRaysEffect") then
				v.Enabled = false
			end
			if v:IsA("Atmosphere") then v:Destroy() end
		end
		
		local old = Lighting:FindFirstChild("NUKE_CC")
		if old then old:Destroy() end
		local cc = Instance.new("ColorCorrectionEffect")
		cc.Name = "NUKE_CC"
		cc.Saturation = -1.8
		cc.Contrast = -0.7
		cc.Brightness = -0.1
		cc.TintColor = Color3.fromRGB(125,125,125)
		cc.Parent = Lighting
		
		for _, obj in pairs(Workspace:GetDescendants()) do
			if obj:IsA("ParticleEmitter") or obj:IsA("Fire") or obj:IsA("Smoke") or obj:IsA("Sparkles") or obj:IsA("Explosion") then
				obj:Destroy()
			elseif obj:IsA("Trail") or obj:IsA("Beam") then
				obj:Destroy()
			elseif obj:IsA("Decal") or obj:IsA("Texture") then
				obj:Destroy()
			elseif obj:IsA("PointLight") or obj:IsA("SpotLight") or obj:IsA("SurfaceLight") then
				obj:Destroy()
			elseif obj:IsA("Sound") then
				obj.Volume = 0
			elseif obj:IsA("BasePart") and not obj:IsA("Terrain") then
				obj.Material = Enum.Material.SmoothPlastic
				obj.Reflectance = 0
				obj.CastShadow = false
				obj.Color = Color3.fromRGB(100,100,100)
				obj.Transparency = 0
			elseif obj:IsA("MeshPart") then
				obj.RenderFidelity = Enum.RenderFidelity.Performance
				obj.CollisionFidelity = Enum.CollisionFidelity.Box
				obj.TextureID = ""
				obj.Material = Enum.Material.SmoothPlastic
				obj.Color = Color3.fromRGB(100,100,100)
			elseif obj:IsA("UnionOperation") then
				obj.RenderFidelity = Enum.RenderFidelity.Performance
				obj.CollisionFidelity = Enum.CollisionFidelity.Box
				obj.UsePartColor = true
				obj.Color = Color3.fromRGB(100,100,100)
			elseif obj:IsA("SpecialMesh") then
				obj.TextureId = ""
				obj.MeshId = ""
				obj.VertexColor = Vector3.new(0.4,0.4)
			end
		end
		
		if Terrain then
			Terrain.WaterWaveSize = 0
			Terrain.WaterWaveSpeed = 0
			Terrain.WaterReflectance = 0
			Terrain.WaterTransparency = 1
			Terrain.Decoration = false
			sethiddenproperty(Terrain,"Decoration",false)
		end
		
		for _,plr in pairs(Players:GetPlayers()) do
			if plr.Character then
				GrayCharacter(plr.Character)
			end
		end
		
		game.StarterGui:SetCore("SendNotification",{
			Title = "NUKE MODE 💎";
			Text = "Đã bật chế độ xám + fix lag";
			Duration = 3;
		})
	end)
end

local function ResetGraphics()
	pcall(function()
		glitch = false
		settings().Rendering.QualityLevel = originalData.QualityLevel
		settings().Rendering.MeshPartDetailLevel = originalData.MeshPartDetailLevel
		Lighting.Brightness = originalData.Lighting.Brightness
		Lighting.Ambient = originalData.Lighting.Ambient
		Lighting.OutdoorAmbient = originalData.Lighting.OutdoorAmbient
		Lighting.ClockTime = originalData.Lighting.ClockTime
		Lighting.FogEnd = originalData.Lighting.FogEnd
		Lighting.GlobalShadows = originalData.Lighting.GlobalShadows
		Lighting.EnvironmentDiffuseScale = originalData.Lighting.EnvironmentDiffuseScale
		Lighting.EnvironmentSpecularScale = originalData.Lighting.EnvironmentSpecularScale
		Lighting.ShadowSoftness = originalData.Lighting.ShadowSoftness
		sethiddenproperty(Lighting, "Technology", originalData.Lighting.Technology)
		
		local cc = Lighting:FindFirstChild("NUKE_CC")
		if cc then cc:Destroy() end
		
		for _, v in pairs(Lighting:GetChildren()) do
			if v:IsA("PostEffect") then v.Enabled = true end
		end
		
		if Terrain then
			Terrain.WaterWaveSize = originalData.Terrain.WaterWaveSize
			Terrain.WaterWaveSpeed = originalData.Terrain.WaterWaveSpeed
			Terrain.WaterReflectance = originalData.Terrain.WaterReflectance
			Terrain.WaterTransparency = originalData.Terrain.WaterTransparency
		end
		
		for part, data in pairs(originalData.Parts) do
			if part and part.Parent then
				part.Color = data.Color
				part.Material = data.Material
				part.Reflectance = data.Reflectance
				part.CastShadow = data.CastShadow
				part.Transparency = data.Transparency
			end
		end
		
		for mesh, data in pairs(originalData.MeshParts) do
			if mesh and mesh.Parent then
				mesh.TextureID = data.TextureID
				mesh.RenderFidelity = data.RenderFidelity
				mesh.CollisionFidelity = data.CollisionFidelity
			end
		end
		
		for union, data in pairs(originalData.Unions) do
			if union and union.Parent then
				union.RenderFidelity = data.RenderFidelity
				union.CollisionFidelity = data.CollisionFidelity
				union.UsePartColor = data.UsePartColor
			end
		end
		
		game.StarterGui:SetCore("SendNotification",{
			Title = "RESET";
			Text = "Đã về đồ họa gốc 100%";
			Duration = 3;
		})
	end)
end

task.spawn(function()
	while task.wait(0.05) do
		if glitch and Workspace.CurrentCamera then
			pcall(function()
				Workspace.CurrentCamera.CFrame = Workspace.CurrentCamera.CFrame * CFrame.new(
					math.random(-3,3)/100,
					math.random(-3,3)/100,
					math.random(-3,3)/100
				)
			end)
		end
	end
end)

local function makeBtn(text, y, callback)
	local b = Instance.new("TextButton")
	b.Name = "Rainbow"
	b.Size = UDim2.new(1,-20,0,32)
	b.Position = UDim2.new(0,10,0,y)
	b.Text = text
	b.BackgroundColor3 = Color3.fromRGB(40,40,40)
	b.TextColor3 = Color3.fromRGB(255,255,255)
	b.Font = Enum.Font.GothamBold
	b.TextSize = 12
	b.Parent = main
	Instance.new("UICorner", b)
	b.MouseButton1Click:Connect(function()
		pcall(callback)
	end)
end

makeBtn("FIX LAG MAX", 70, FixLagMax)
makeBtn("NUKE MODE", 110, NukeMode)
makeBtn("RESET GRAPHICS", 150, ResetGraphics)
makeBtn("GLITCH ON/OFF", 190, function() glitch = not glitch end)
makeBtn("FPS/MS ON/OFF", 230, function() showHUD = not showHUD end)
