	local library = {}

	local module = loadstring(game:HttpGet("https://gist.githubusercontent.com/Enxquity/73e32a376a529184b1c8e626ab6fb5a8/raw/d038e74d487d33702b07b8f6ad6eab1266f8495b/a", true))()

	library.__index = library;
	library.UI = {}

	library.DragBarFills = {}
	library.Colors = {}
	library.DropDowns = {}

	local theme;

	if _G.theme == nil then
		theme = {
			--Assets
			["DropDown"] = {
				["Background"] = Color3.fromRGB(148, 180, 255),
				["DropMenu"] = Color3.fromRGB(148, 180, 255),
				["Text"] = Color3.fromRGB(255, 255, 255),
				["ButtonColor"] = Color3.fromRGB(132, 160, 227)
			},
		
			["ColorAsset"] = {
				["Background"] = Color3.fromRGB(148, 180, 255),
				["Text"] = Color3.fromRGB(124, 151, 213)
			},
		
			["ProgressBar"] = {
				["Background"] = Color3.fromRGB(148, 180, 255),
				["Bar"] = Color3.fromRGB(83, 116, 209),
				["Text"] = Color3.fromRGB(255, 255, 255)
			},
		
			["Toggle"] = {
				["Background"] = Color3.fromRGB(148, 180, 255),
				["ToggleLayer"] = Color3.fromRGB(83, 116, 209),
				["Text"] = Color3.fromRGB(83, 116, 209)
			},
		
			["Button"] = Color3.fromRGB(148, 180, 255),
			["TabButton"] = Color3.fromRGB(101, 142, 255),
		
		
			--Main
			["PrimaryColor"] = Color3.fromRGB(255, 255, 255),
			["SideMenu"] = Color3.fromRGB(83, 116, 209),
			["TopBar"] = Color3.fromRGB(101, 142, 255),
			["UIText"] = Color3.fromRGB(255, 255, 255),
		
			--Other
			["SearchBar"] = {
				["Background"] = Color3.fromRGB(148, 180, 255), 
				["Icon"] = Color3.fromRGB(148, 180, 255),
				["Text"] = {
					["Placeholder"] = Color3.fromRGB(255, 255, 255),
					["TextColor"] = Color3.fromRGB(255, 255, 255)
				}
			},
		
			["Customizeables"] = Color3.fromRGB(66, 93, 168),
		
		}
	elseif _G.theme ~= nil and _G.theme == "Dark" then
		theme = {
			--Assets
			["DropDown"] = {
			["Background"] = Color3.fromRGB(72, 72, 72),
			["DropMenu"] = Color3.fromRGB(38, 38, 38),
			["Text"] = Color3.fromRGB(159, 159, 159),
			["ButtonColor"] = Color3.fromRGB(43, 43, 43)
		},
		
		["ColorAsset"] = {
			["Background"] = Color3.fromRGB(72, 72, 72),
			["Text"] = Color3.fromRGB(159, 159, 159)
		},
		
		["ProgressBar"] = {
			["Background"] = Color3.fromRGB(72, 72, 72),
			["Bar"] = Color3.fromRGB(95, 95, 95),
			["Text"] = Color3.fromRGB(159, 159, 159)
		},
		
		["Toggle"] = {
			["Background"] = Color3.fromRGB(72,72,72),
			["ToggleLayer"] = Color3.fromRGB(95, 95, 95),
			["Text"] = Color3.fromRGB(159, 159, 159)
		},
		
		["Button"] = Color3.fromRGB(72, 72, 72),
		["TabButton"] = Color3.fromRGB(72, 72, 72),
		
		
		--Main
		["PrimaryColor"] = Color3.fromRGB(48, 48, 48),
		["SideMenu"] = Color3.fromRGB(34, 34, 34),
		["TopBar"] = Color3.fromRGB(29, 29, 29),
		["UIText"] = Color3.fromRGB(159, 159, 159),

		--Other
		["SearchBar"] = {
			["Background"] = Color3.fromRGB(59, 59, 59), 
			["Icon"] = Color3.fromRGB(255, 84, 0),
			["Text"] = {
				["Placeholder"] = Color3.fromRGB(159, 159, 159),
				["TextColor"] = Color3.fromRGB(255, 255, 255)
			}
		},
		
		["Customizeables"] = Color3.fromRGB(255, 84, 0),
	}
	else
		theme = _G.theme
	end

	function changeProperties(a,b)
		for i,v in pairs(a) do
			b[i] = v 
		end
	end

	function bindToPress(a,b)
		a.MouseButton1Down:Connect(b);
	end

	function library.createNewUI(name,bool)
		local a = {}
		
		a.UIName = name
		a.AllowCustomization = bool
		
		a.UI = Instance.new("ScreenGui")
		local MainFrame = Instance.new("ImageLabel")
		local LeftMenu = Instance.new("Frame")
		local UICorner = Instance.new("UICorner")
		local Holder = Instance.new("Frame")
		local UIListLayout = Instance.new("UIListLayout")
		local Placeholder = Instance.new("Frame")
		local TextButton_Roundify_12px = Instance.new("ImageLabel")
		local Search = Instance.new("TextBox")
		local ImageLabel = Instance.new("ImageLabel")
		local Assets = Instance.new("Folder")
		local AssetFrame = Instance.new("ScrollingFrame")
		local UIListLayout_2 = Instance.new("UIListLayout")
		local Customizable = Instance.new("Folder")
		local Customizeable = Instance.new("Frame")
		local Customizeable_2 = Instance.new("Frame")
		local Ignore = Instance.new("Folder")
		local ToggleBackground = Instance.new("TextButton");
		local Excess = Instance.new("Frame")
		local Excess_2 = Instance.new("Frame")
		local Excess_3 = Instance.new("Frame")
		local MainUI = Instance.new("Folder")
		local TopBar = Instance.new("Frame")
		local UICorner_2 = Instance.new("UICorner")
		local TextLabel = Instance.new("TextLabel")
		local PossibleAssets = Instance.new("Folder")
		local Description = Instance.new("Frame")
		local UICorner_3 = Instance.new("UICorner")
		local DescriptionLabel = Instance.new("TextLabel")
		local ProgressBar = Instance.new("TextButton")
		local UICorner_4 = Instance.new("UICorner")
		local Cover = Instance.new("Frame")
		local UICorner_5 = Instance.new("UICorner")	
		local TextLabel_2 = Instance.new("TextLabel")
		local CheckBox = Instance.new("TextButton")
		local UICorner_6 = Instance.new("UICorner")
		local Toggle = Instance.new("TextButton")
		local UICorner_7 = Instance.new("UICorner")
		local ToggleLabel = Instance.new("TextLabel")
		local Dropdown = Instance.new("TextButton")
		local UICorner_8 = Instance.new("UICorner")
		local TextButton = Instance.new("TextButton")
		local ColorAsset = Instance.new("Frame")
		local UICorner_1 = Instance.new("UICorner")
		local Color = Instance.new("TextButton")
		local UICorner_18 = Instance.new("UICorner")
		local ColorRGB = Instance.new("TextLabel")
		local UICorner_9 = Instance.new("UICorner")
		local Button = Instance.new("TextButton")
		local UICorner_10 = Instance.new("UICorner")
		local MenuButton = Instance.new("TextButton")
		local UICorner_11 = Instance.new("UICorner")
		local Dropdown = Instance.new("TextButton")
		local UICorner5 = Instance.new("UICorner")
		local DropPlus = Instance.new("TextButton")
		local UICorner_24 = Instance.new("UICorner")
		local Drop = Instance.new("Frame")
		local Excess_5 = Instance.new("Folder")
		local Excess_6 = Instance.new("Frame")
		local UICorner_31 = Instance.new("UICorner")
		local Dropdown_2 = Instance.new("Frame")
		local UIListLayout55 = Instance.new("UIListLayout")
		local DPButton = Instance.new("TextButton")
		
		--Properties:

		a.UI.Name = "UI"
		a.UI.Parent = game.CoreGui

		MainFrame.Name = "MainFrame"
		MainFrame.Parent = a.UI
		MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
		MainFrame.BackgroundColor3 = theme.PrimaryColor
		MainFrame.BackgroundTransparency = 1.000
		MainFrame.ClipsDescendants = true
		MainFrame.Position = UDim2.new(0.5, 0, 0.499519706, 0)
		MainFrame.Size = UDim2.new(0, 637, 0, 367)
		MainFrame.ZIndex = 0
		MainFrame.Image = "rbxassetid://3570695787"
		MainFrame.ScaleType = Enum.ScaleType.Slice
		MainFrame.ImageColor3 = theme.PrimaryColor
		MainFrame.SliceCenter = Rect.new(100, 100, 100, 100)
		MainFrame.SliceScale = 0.180

		a.UI.Enabled = false

		delay(1, function()
			a.UI.Enabled = true;
		end)
		
		--Dragging
		local dragging
		local dragInput
		local dragStart
		local startPos

		local function update(input)
			local delta = input.Position - dragStart
			game:GetService("TweenService"):Create(MainFrame, TweenInfo.new(0.1), {Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)}):Play()
		end

		MainFrame.InputBegan:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
				dragging = true
				dragStart = input.Position
				startPos = MainFrame.Position

				input.Changed:Connect(function()
					if input.UserInputState == Enum.UserInputState.End then
						dragging = false
					end
				end)
			end
		end)

		MainFrame.InputChanged:Connect(function(input)
			if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
				dragInput = input
			end
		end)

		game:GetService("UserInputService").InputChanged:Connect(function(input)
			if input == dragInput and dragging then
				update(input)
			end
		end)
		
		LeftMenu.Name = "LeftMenu"
		LeftMenu.Parent = MainFrame
		LeftMenu.BackgroundColor3 = theme.SideMenu
		LeftMenu.Position = UDim2.new(0, 0, 0.068119891, 0)
		LeftMenu.Size = UDim2.new(0, 137, 0, 349)
		LeftMenu.ZIndex = 0

		UICorner_1.CornerRadius = UDim.new(0.200000003, 0)
		UICorner_1.Parent = LeftMenu

		Holder.Name = "Holder"
		Holder.Parent = LeftMenu
		Holder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Holder.BackgroundTransparency = 1.000
		Holder.Position = UDim2.new(0.0656934306, 0, 0.111747853, 0)
		Holder.Size = UDim2.new(0, 121, 0, 295)
		Holder.ZIndex = 2

		UIListLayout.Parent = Holder
		UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		UIListLayout.Padding = UDim.new(0, 8)

		Placeholder.Name = "Placeholder"
		Placeholder.Parent = MainFrame
		Placeholder.Active = true
		Placeholder.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Placeholder.BackgroundTransparency = 1.000
		Placeholder.BorderSizePixel = 0
		Placeholder.Position = UDim2.new(0.310832024, 0, 0.174386919, 0)
		Placeholder.Selectable = true
		Placeholder.Size = UDim2.new(0, 427, 0, 28)
		Placeholder.ZIndex = 3

		TextButton_Roundify_12px.Name = "TextButton_Roundify_12px"
		TextButton_Roundify_12px.Parent = Placeholder
		TextButton_Roundify_12px.Active = true
		TextButton_Roundify_12px.AnchorPoint = Vector2.new(0.5, 0.5)
		TextButton_Roundify_12px.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TextButton_Roundify_12px.BackgroundTransparency = 1.000
		TextButton_Roundify_12px.Position = UDim2.new(0.5, 0, 0.5, 0)
		TextButton_Roundify_12px.Selectable = true
		TextButton_Roundify_12px.Size = UDim2.new(1, 0, 1, 0)
		TextButton_Roundify_12px.Image = "rbxassetid://3570695787"
		TextButton_Roundify_12px.ImageColor3 = theme.SearchBar.Background
		TextButton_Roundify_12px.ScaleType = Enum.ScaleType.Slice
		TextButton_Roundify_12px.SliceCenter = Rect.new(100, 100, 100, 100)
		TextButton_Roundify_12px.SliceScale = 0.050
		
		ColorAsset.Name = "ColorAsset"
		ColorAsset.Parent = PossibleAssets
		ColorAsset.AnchorPoint = Vector2.new(0.5, 0.5)
		ColorAsset.BackgroundColor3 = theme.ColorAsset.Background
		ColorAsset.BorderSizePixel = 0
		ColorAsset.Position = UDim2.new(0.0400000252, 0, 0.0259769149, 0)
		ColorAsset.Size = UDim2.new(0, 38, 0, 38)
		ColorAsset.Visible = false

		UICorner.CornerRadius = UDim.new(0.200000003, 0)
		UICorner.Parent = ColorAsset

		Color.Name = "Color"
		Color.Parent = ColorAsset
		Color.Active = false
		Color.AnchorPoint = Vector2.new(0.5, 0.5)
		Color.BackgroundColor3 = Color3.fromRGB(80, 98, 139)
		Color.BorderSizePixel = 0
		Color.Position = UDim2.new(0.5, 0, 0.5, 0)
		Color.Selectable = false
		Color.Size = UDim2.new(0.777777791, 0, 0.773005903, 0)
		Color.Text = ""
		Color.AutoButtonColor = false

		UICorner_18.CornerRadius = UDim.new(0.200000003, 0)
		UICorner_18.Parent = Color

		ColorRGB.Name = "ColorRGB"
		ColorRGB.Parent = ColorAsset
		ColorRGB.AnchorPoint = Vector2.new(0.5, 0.5)
		ColorRGB.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ColorRGB.BackgroundTransparency = 1.000
		ColorRGB.Position = UDim2.new(6.73899984, 0, 0.5, 0)
		ColorRGB.Size = UDim2.new(10.7789078, 0, 0.842660606, 0)
		ColorRGB.Font = Enum.Font.SourceSans
		ColorRGB.Text = "Excess - rgb(255, 255, 255)"
		ColorRGB.TextColor3 = theme.ColorAsset.Text
		ColorRGB.TextScaled = true
		ColorRGB.TextSize = 14.000
		ColorRGB.TextWrapped = true
		ColorRGB.TextXAlignment = Enum.TextXAlignment.Left
		
		Search.Name = "Search"
		Search.Parent = Placeholder
		Search.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Search.BackgroundTransparency = 1.000
		Search.BorderSizePixel = 0
		Search.Position = UDim2.new(0.0399999991, 0, 0.170000002, 0)
		Search.Size = UDim2.new(0, 386, 0, 21)
		Search.ZIndex = 5
		Search.Font = Enum.Font.SourceSans
		Search.PlaceholderColor3 = theme.SearchBar.Text.Placeholder
		Search.PlaceholderText = "..."
		Search.Text = ""
		Search.TextColor3 = theme.SearchBar.Text.TextColor
		Search.TextScaled = true
		Search.TextSize = 14.000
		Search.TextWrapped = true
		Search.TextXAlignment = Enum.TextXAlignment.Left

		ImageLabel.Parent = MainFrame
		ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ImageLabel.BackgroundTransparency = 1.000
		ImageLabel.BorderSizePixel = 0
		ImageLabel.Position = UDim2.new(0.248037681, 0, 0.174386933, 0)
		ImageLabel.Size = UDim2.new(0, 28, 0, 28)
		ImageLabel.Image = "http://www.roblox.com/asset/?id=6444245311"
		ImageLabel.ImageColor3 = theme.SearchBar.Icon

		Assets.Name = "Assets"
		Assets.Parent = MainFrame

		AssetFrame.Name = "AssetFrame"
		AssetFrame.Parent = Assets
		AssetFrame.Active = true
		AssetFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		AssetFrame.BackgroundTransparency = 1.000
		AssetFrame.Position = UDim2.new(0.25, 0, 0.289999992, 0)
		AssetFrame.Size = UDim2.new(0, 480, 0, 260)
		AssetFrame.CanvasSize = UDim2.new(0,0,3,0)
		AssetFrame.ZIndex = 15
		AssetFrame.BottomImage = ""
		AssetFrame.MidImage = ""
		AssetFrame.TopImage = ""

		UIListLayout_2.Parent = AssetFrame
		UIListLayout_2.SortOrder = Enum.SortOrder.LayoutOrder
		UIListLayout_2.Padding = UDim.new(0, 15)

		Customizable.Name = "Customizable"
		Customizable.Parent = MainFrame

		Customizeable.Name = "Customizeable"
		Customizeable.Parent = Customizable
		Customizeable.BackgroundColor3 = theme.Customizeables
		Customizeable.BorderSizePixel = 0
		Customizeable.Position = UDim2.new(0.21507065, 0, 0.147138968, 0)
		Customizeable.Size = UDim2.new(0, 500, 0, 2)
		Customizeable.ZIndex = 2

		Customizeable_2.Name = "Customizeable"
		Customizeable_2.Parent = Customizable
		Customizeable_2.BackgroundColor3 = theme.Customizeables
		Customizeable_2.BorderSizePixel = 0
		Customizeable_2.Position = UDim2.new(0.21507065, 0, 0.147138968, 0)
		Customizeable_2.Size = UDim2.new(0, 2, 0, 320)
		Customizeable_2.ZIndex = 2

		Ignore.Name = "Ignore"
		Ignore.Parent = MainFrame

		Excess.Name = "Excess"
		Excess.Parent = Ignore
		Excess.BackgroundColor3 = theme.SideMenu
		Excess.BorderSizePixel = 0
		Excess.Position = UDim2.new(0.117739424, 0, 0.92098093, 0)
		Excess.Size = UDim2.new(0, 62, 0, 29)

		Excess_2.Name = "Excess"
		Excess_2.Parent = Ignore
		Excess_2.BackgroundColor3 = theme.TopBar
		Excess_2.BorderSizePixel = 0
		Excess_2.Position = UDim2.new(0, 0, 0.0681198835, 0)
		Excess_2.Size = UDim2.new(0, 62, 0, 29)

		Excess_3.Name = "Excess"
		Excess_3.Parent = Ignore
		Excess_3.BackgroundColor3 = theme.TopBar
		Excess_3.BorderSizePixel = 0
		Excess_3.Position = UDim2.new(0.902668774, 0, 0.0681198835, 0)
		Excess_3.Size = UDim2.new(0, 62, 0, 29)

		MainUI.Name = "MainUI"
		MainUI.Parent = MainFrame

		TopBar.Name = "TopBar"
		TopBar.Parent = MainUI
		TopBar.BackgroundColor3 = theme.TopBar
		TopBar.Size = UDim2.new(0, 637, 0, 54)

		UICorner_2.CornerRadius = UDim.new(0.300000012, 0)
		UICorner_2.Parent = TopBar

		TextLabel.Parent = TopBar
		TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TextLabel.BackgroundTransparency = 1.000
		TextLabel.Position = UDim2.new(0.0266875979, 0, 0.222222224, 0)
		TextLabel.Size = UDim2.new(0, 103, 0, 34)
		TextLabel.ZIndex = 2
		TextLabel.Font = Enum.Font.Roboto
		TextLabel.Text = name
		TextLabel.TextColor3 = theme.UIText
		TextLabel.TextScaled = true
		TextLabel.TextSize = 14.000
		TextLabel.TextWrapped = true

		PossibleAssets.Name = "PossibleAssets"
		PossibleAssets.Parent = a.UI

		Description.Name = "Description"
		Description.Parent = PossibleAssets
		Description.BackgroundColor3 = Color3.fromRGB(148, 180, 255)
		Description.BorderSizePixel = 0
		Description.Position = UDim2.new(0.248037681, 0, 0.514986396, 0)
		Description.Size = UDim2.new(0, 467, 0, 54)
		Description.Visible = false

		UICorner_3.CornerRadius = UDim.new(0.100000001, 0)
		UICorner_3.Parent = Description

		DescriptionLabel.Name = "DescriptionLabel"
		DescriptionLabel.Parent = Description
		DescriptionLabel.AnchorPoint = Vector2.new(0.5, 0.5)
		DescriptionLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		DescriptionLabel.BackgroundTransparency = 1.000
		DescriptionLabel.Position = UDim2.new(0.504282653, 0, 0.525368035, 0)
		DescriptionLabel.Size = UDim2.new(0.945610285, 0, 0.776661634, 0)
		DescriptionLabel.Font = Enum.Font.SourceSans
		DescriptionLabel.Text = "Description label."
		DescriptionLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
		DescriptionLabel.TextScaled = true
		DescriptionLabel.TextSize = 20.000
		DescriptionLabel.TextWrapped = true
		DescriptionLabel.TextXAlignment = Enum.TextXAlignment.Left
		DescriptionLabel.TextYAlignment = Enum.TextYAlignment.Top

		ProgressBar.Name = "ProgressBar"
		ProgressBar.Parent = PossibleAssets
		ProgressBar.Active = true
		ProgressBar.BackgroundColor3 = theme.ProgressBar.Background
		ProgressBar.BorderSizePixel = 0
		ProgressBar.Position = UDim2.new(0.248037681, 0, 0.702997267, 0)
		ProgressBar.Selectable = true
		ProgressBar.Size = UDim2.new(0, 467, 0, 20)
		ProgressBar.Visible = false
		ProgressBar.Text = ""

		UICorner_4.CornerRadius = UDim.new(0.5, 0)
		UICorner_4.Parent = ProgressBar

		Cover.Name = "Cover"
		Cover.Parent = ProgressBar
		Cover.Active = true
		Cover.BackgroundColor3 = theme.ProgressBar.Bar
		Cover.BorderSizePixel = 0
		Cover.Selectable = true
		Cover.Size = UDim2.new(0.25, 0, 1, 0)

		UICorner_5.CornerRadius = UDim.new(0.5, 0)
		UICorner_5.Parent = Cover

		TextLabel_2.Parent = ProgressBar
		TextLabel_2.AnchorPoint = Vector2.new(0.5, 0.5)
		TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		TextLabel_2.BackgroundTransparency = 1.000
		TextLabel_2.Position = UDim2.new(0.5, 0, 0.5, 0)
		TextLabel_2.Size = UDim2.new(0.269807279, 0, 1, 0)
		TextLabel_2.Font = Enum.Font.SourceSans
		TextLabel_2.Text = "ProgressBar - 25"
		TextLabel_2.TextColor3 = theme.ProgressBar.Text
		TextLabel_2.TextScaled = true
		TextLabel_2.TextSize = 14.000
		TextLabel_2.TextWrapped = true

		CheckBox.Name = "CheckBox"
		CheckBox.Parent = PossibleAssets
		CheckBox.BackgroundColor3 = theme.Toggle.Background
		CheckBox.BorderSizePixel = 0
		CheckBox.Position = UDim2.new(0.248037681, 0, 0.397820175, 0)
		CheckBox.Size = UDim2.new(0, 28, 0, 28)
		CheckBox.Visible = false
		CheckBox.Font = Enum.Font.SourceSans
		CheckBox.Text = ""
		CheckBox.TextColor3 = Color3.fromRGB(255, 255, 255)
		CheckBox.TextSize = 14.000

		UICorner_6.CornerRadius = UDim.new(0.5, 0)
		UICorner_6.Parent = CheckBox

		ToggleBackground.Name = "ToggleBackground"
		ToggleBackground.Parent = CheckBox
		ToggleBackground.AnchorPoint = Vector2.new(0.5, 0.5)
		ToggleBackground.BackgroundColor3 = theme.Toggle.ToggleLayer
		ToggleBackground.BorderSizePixel = 0
		ToggleBackground.Position = UDim2.new(0.5, 0, 0.5, 0)
		ToggleBackground.Size = UDim2.new(0, 20, 0, 20)
		ToggleBackground.Font = Enum.Font.SourceSans
		ToggleBackground.Text = ""
		ToggleBackground.TextColor3 = Color3.fromRGB(255, 255, 255)
		ToggleBackground.TextSize = 14.000
		
		Toggle.Name = "Toggle"
		Toggle.Parent = CheckBox
		Toggle.AnchorPoint = Vector2.new(0.5, 0.5)
		Toggle.BackgroundColor3 = Color3.fromRGB(83, 116, 209)
		Toggle.BorderSizePixel = 0
		Toggle.Position = UDim2.new(0.5, 0, 0.5, 0)
		Toggle.Size = UDim2.new(0, 20, 0, 20)
		Toggle.Font = Enum.Font.SourceSans
		Toggle.Text = ""
		Toggle.BackgroundTransparency = 1;
		Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
		Toggle.TextSize = 14.000

		UICorner_7.CornerRadius = UDim.new(0.5, 0)
		UICorner_7.Parent = ToggleBackground

		ToggleLabel.Name = "ToggleLabel"
		ToggleLabel.Parent = CheckBox
		ToggleLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ToggleLabel.BackgroundTransparency = 1.000
		ToggleLabel.BorderSizePixel = 0
		ToggleLabel.Position = UDim2.new(1.42857146, 0, 0, 0)
		ToggleLabel.Size = UDim2.new(0, 200, 0, 28)
		ToggleLabel.Font = Enum.Font.SourceSans
		ToggleLabel.Text = "CheckBox"
		ToggleLabel.TextColor3 = theme.Toggle.Text
		ToggleLabel.TextScaled = true
		ToggleLabel.TextSize = 14.000
		ToggleLabel.TextWrapped = true
		ToggleLabel.TextXAlignment = Enum.TextXAlignment.Left

		Dropdown.Name = "Dropdown"
		Dropdown.Parent = PossibleAssets
		Dropdown.BackgroundColor3 = theme.DropDown.Background
		Dropdown.BorderSizePixel = 0
		Dropdown.Position = UDim2.new(0.248037681, 0, 0.803814709, 0)
		Dropdown.Size = UDim2.new(0, 302, 0, 28)
		Dropdown.Visible = false
		Dropdown.AutoButtonColor = false
		Dropdown.Font = Enum.Font.SourceSans
		Dropdown.Text = "Drop down"
		Dropdown.TextColor3 = Color3.fromRGB(255, 255, 255)
		Dropdown.TextSize = 20.000
		Dropdown.ZIndex = 100

		UICorner_8.CornerRadius = UDim.new(0.5, 0)
		UICorner_8.Parent = Dropdown

		UICorner_9.CornerRadius = UDim.new(0.5, 0)
		UICorner_9.Parent = TextButton

		Button.Name = "Button"
		Button.Parent = PossibleAssets
		Button.BackgroundColor3 = theme.Button
		Button.BorderSizePixel = 0
		Button.Position = UDim2.new(0.248037681, 0, 0.28337875, 0)
		Button.Size = UDim2.new(0, 208, 0, 28)
		Button.Visible = false
		Button.Font = Enum.Font.SourceSans
		Button.TextColor3 = Color3.fromRGB(255, 255, 255)
		Button.TextSize = 14.000

		UICorner_10.CornerRadius = UDim.new(0.5, 0)
		UICorner_10.Parent = Button

		MenuButton.Name = "MenuButton"
		MenuButton.Parent = PossibleAssets
		MenuButton.BackgroundColor3 = theme.TabButton
		MenuButton.Size = UDim2.new(0, 121, 0, 28)
		MenuButton.Visible = false
		MenuButton.Font = Enum.Font.SourceSans
		MenuButton.Text = "Home"
		MenuButton.TextColor3 = Color3.fromRGB(255, 255, 255)
		MenuButton.TextScaled = true
		MenuButton.TextSize = 14.000
		MenuButton.TextWrapped = true
		MenuButton.ZIndex = 1000

		UICorner5.CornerRadius = UDim.new(0.5, 0)
		UICorner5.Parent = Dropdown

		DropPlus.Name = "Icon"
		DropPlus.Parent = Dropdown
		DropPlus.BackgroundColor3 = Color3.fromRGB(148, 180, 255)
		DropPlus.BorderSizePixel = 0
		DropPlus.Position = UDim2.new(0.906655848, 0, 0.053815566, 0)
		DropPlus.Size = UDim2.new(0, 28, 0, 24)
		DropPlus.ZIndex = 101
		DropPlus.AutoButtonColor = false
		DropPlus.Font = Enum.Font.SourceSans
		DropPlus.Text = "+"
		DropPlus.TextColor3 = theme.DropDown.Text
		DropPlus.TextScaled = true
		DropPlus.TextSize = 14.000
		DropPlus.TextWrapped = true
		DropPlus.BackgroundTransparency = 1
		

		UICorner_24.CornerRadius = UDim.new(0.5, 0)
		UICorner_24.Parent = DropPlus

		Drop.Name = "Drop"
		Drop.Parent = Dropdown
		Drop.BackgroundColor3 = theme.DropDown.DropMenu
		Drop.BorderSizePixel = 0
		Drop.Position = UDim2.new(0, 0, 0.63999939, 0)
		Drop.Size = UDim2.new(1, 0, 0, 0)
		Drop.Visible = true
		Drop.ZIndex = 15
		Drop.ClipsDescendants = true

		Excess_5.Name = "Excess"
		Excess_5.Parent = Drop

		Excess_6.Name = "Excess"
		Excess_6.Parent = Excess_5
		Excess_6.BorderSizePixel = 0
		Excess_6.BackgroundColor3 = theme.DropDown.DropMenu
		Excess_6.ClipsDescendants = true
		Excess_6.Position = UDim2.new(0, 0, 0.93, 0)
		Excess_6.Size = UDim2.new(1, 0, 0.1, 0)
		Excess_6.ZIndex = 15

		UICorner_31.CornerRadius = UDim.new(0, 15)
		UICorner_31.Parent = Excess_6
		
		Dropdown_2.ZIndex = 15
		Dropdown_2.Name = "Dropdown"
		Dropdown_2.Parent = Drop
		Dropdown_2.AnchorPoint = Vector2.new(0.5, 0.5)
		Dropdown_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Dropdown_2.BackgroundTransparency = 1.000
		Dropdown_2.Position = UDim2.new(0.5, 0, 0.55, 0)
		Dropdown_2.Size = UDim2.new(1, 0, 1.02037001, 0)
		Dropdown_2.Visible = true

		UIListLayout55.Parent = Dropdown_2
		UIListLayout55.SortOrder = Enum.SortOrder.LayoutOrder

		DPButton.Name = "DPButton"
		DPButton.Parent = PossibleAssets
		DPButton.BackgroundColor3 = theme.DropDown.ButtonColor
		DPButton.BorderSizePixel = 0
		DPButton.Size = UDim2.new(1, 0, 0, 35)
		DPButton.Visible = false
		DPButton.Font = Enum.Font.SourceSans
		DPButton.Text = "a"
		DPButton.TextColor3 = Color3.fromRGB(255, 255, 255)
		DPButton.TextScaled = true
		DPButton.TextSize = 14.000
		DPButton.TextWrapped = true
		DPButton.ZIndex = 15
		DPButton.AutoButtonColor = true

		UICorner_11.CornerRadius = UDim.new(0.200000003, 0)
		UICorner_11.Parent = MenuButton
		
		for i,v in pairs(PossibleAssets:GetChildren()) do
			if v:IsA("TextButton") and v.Name ~= "Dropdown" and v.Name ~= "DPButton"  then
				v.AutoButtonColor = false;
				v.ClipsDescendants = true;
			end
		end
		
		local circle = Instance.new("ImageLabel",PossibleAssets)
		circle.Name = "ButtonCircle"
		circle.Image = "rbxassetid://3570695787"
		circle.SliceCenter = Rect.new(100,100,100,100)
		circle.SliceScale = 0.5
		circle.AnchorPoint = Vector2.new(0.5,0.5)
		circle.BackgroundTransparency = 1
		circle.ScaleType = Enum.ScaleType.Stretch
		circle.ZIndex = 10000000
		local circleThing = Instance.new("UICorner",circle)
		circleThing.CornerRadius = UDim.new(1,0)
		circle.Size = UDim2.new(0,0,0,0)
		circle.BackgroundColor3 = Color3.fromRGB(255,255,255)
		circle.ImageTransparency = 0.5
		circle.BorderSizePixel = 0;
		
		AssetFrame.ScrollBarImageTransparency = 1;
		
		a.Tabs = {}
		
		table.insert(library.UI,a)
		
		if a.AllowCustomization then
			delay(0.1,function()
				local tab = library.NewTab(a, "Customize", true)
				
				tab:CreateColorAsset("UI Extra Color",  Customizeable.BackgroundColor3, function()
					local color = library:GetColor("UI Extra Color")
					for i,v in pairs(Customizable:GetChildren()) do
						v.BackgroundColor3 = color;
					end
				end)
			end)
		end
		
		return setmetatable(a,library)
	end

	function library.Toggle(ui)
		local mainUI = ui.UI;
		if mainUI.Enabled == false then
			mainUI.Enabled = true
		else
			mainUI.Enabled = false
		end
	end

	function library.NewTab(ui,tabName,bool,textScale)
		local tabTable = {}
		
		tabTable.FocusedUIName = ui.UIName
		tabTable.AllowCustomizations = ui.AllowCustomization
		tabTable.FocusedUI = ui.UI;
		tabTable.Assets = {};
		tabTable.TabName = tabName
		tabTable.CheckBoxBools = {}
		
		local MainUI = tabTable.FocusedUI
		local buttonAsset = MainUI:FindFirstChild("PossibleAssets").MenuButton
		local cloneLocation = MainUI:FindFirstChild("MainFrame").LeftMenu.Holder
		
		local newButton = buttonAsset:Clone()
		newButton.Parent = cloneLocation;
		newButton.Name = tabName
		
		local props = {
			
			["Text"] = tabName,
			["Visible"] = true,
			
		}
		
		changeProperties(props,newButton)
		
		bindToPress(newButton,function(x,y)
			for i,v in pairs(MainUI:FindFirstChild("MainFrame").Assets.AssetFrame:GetChildren()) do
				if v and v.Name ~= "UIListLayout" then
					changeProperties({
						["Visible"] = false;
					}, v)
				end
			end
			for i,v	 in pairs(tabTable.Assets) do
				if v and v.Name ~= "UIListLayout" then
					changeProperties({
						["Visible"] = true;
					}, v)
				end
			end
			if bool then
				local circle = MainUI:FindFirstChild("PossibleAssets").ButtonCircle:Clone();
				circle.Parent = newButton;
				local pos = UDim2.new(0,x-newButton.AbsolutePosition.X,0,y-newButton.AbsolutePosition.Y-36)
				circle.Position = pos
				circle.Size = UDim2.new(0,1,0,1)
				circle.ImageTransparency = .5

				local goal = {}
				goal.Size = UDim2.new(0,500,0,500)
				goal.ImageTransparency = 1

				local tween = game:GetService("TweenService"):Create(circle, TweenInfo.new(1,Enum.EasingStyle.Sine,Enum.EasingDirection.Out), goal)
				tween:Play()
				tween.Completed:Wait()
				circle:Destroy();
			end
		end)
		
		if textScale then
			changeProperties({
				["TextScaled"] = true		
			}
			,newButton)
		end
		
		table.insert(ui.Tabs,tabTable);
		return setmetatable(tabTable,library);
	end

	function library:NewButton(buttonText,bool,f)
		local MainUI = self.FocusedUI
		local buttonAsset = MainUI:FindFirstChild("PossibleAssets").Button
		local cloneLocation = MainUI:FindFirstChild("MainFrame").Assets.AssetFrame
		
		local newButton = buttonAsset:Clone()
		newButton.Parent = cloneLocation;
		newButton.Name = "Tab"..self.TabName..tostring(#self.Assets+1)
		
		
		local props = {
			
			["Text"] = buttonText,
			["Visible"] = true,
			
		}
		
		changeProperties(props,newButton);
		bindToPress(newButton,function(x,y)
			if bool then
				local circle = MainUI:FindFirstChild("PossibleAssets").ButtonCircle:Clone();
				circle.Parent = newButton;
				local pos = UDim2.new(0,x-newButton.AbsolutePosition.X,0,y-newButton.AbsolutePosition.Y-36)
				circle.Position = pos
				circle.Size = UDim2.new(0,1,0,1)
				circle.ImageTransparency = .5

				local goal = {}
				goal.Size = UDim2.new(0,500,0,500)
				goal.ImageTransparency = 1

				local tween = game:GetService("TweenService"):Create(circle, TweenInfo.new(1,Enum.EasingStyle.Sine,Enum.EasingDirection.Out), goal)
				tween:Play()
				tween.Completed:Wait()
				circle:Destroy();
			end
			f();
		end)
		
		table.insert(self.Assets,newButton)
	end

	function library:NewToggle(checkBoxName,toggleBool,fEnabled,fDisabled)
		local MainUI = self.FocusedUI
		local checkBoxAsset = MainUI:FindFirstChild("PossibleAssets").CheckBox
		local cloneLocation = MainUI:FindFirstChild("MainFrame").Assets.AssetFrame

		local newCheckBox = checkBoxAsset:Clone()
		newCheckBox.Parent = cloneLocation;
		newCheckBox.Name = "Tab"..self.TabName..tostring(#self.Assets+1)
		
		local checkBoxText = newCheckBox.ToggleLabel
		local toggleButton = newCheckBox.Toggle
		local background = newCheckBox.ToggleBackground
		
		newCheckBox.ClipsDescendants = false;
		
		background.AutoButtonColor = false;
		toggleButton.AutoButtonColor = false;
		
		self.CheckBoxBools[newCheckBox.Name] = toggleBool;
		
		coroutine.resume(coroutine.create(function()
			wait(0.5)
			if self.CheckBoxBools[newCheckBox.Name] == false then
				background.Size = UDim2.new(0,0,0,0)
			else
				background.Size = UDim2.new(0,20,0,20)
			end
		end))
		
		local propsText = {
			
			["Text"] = checkBoxName,
			["Visible"] = true;
			
		}
		
		local propsToggle = {
			
			["Visible"] = true
			
		}
		
		if toggleBool then
			fEnabled();
		end
		
		bindToPress(toggleButton,function()
			if self.CheckBoxBools[newCheckBox.Name] then
				self.CheckBoxBools[newCheckBox.Name] = false;
				game:GetService("TweenService"):Create(background,TweenInfo.new(0.2),{Size = UDim2.new(0,0,0,0)}):Play()
				fDisabled();
			else
				self.CheckBoxBools[newCheckBox.Name] = true;
				game:GetService("TweenService"):Create(background,TweenInfo.new(0.2),{Size = UDim2.new(0,20,0,20)}):Play()
				fEnabled();
			end
		end)
		
		changeProperties(propsText,checkBoxText)
		changeProperties(propsToggle,toggleButton)
		
		table.insert(self.Assets,newCheckBox)
	end

	function library:NewDragBar(name,max,startingVal,f)
		
		local val;
		
		local holdingDrag = false;
		
		library.DragBarFills[name] = val
		
		local MainUI = self.FocusedUI
		local dragBarAsset = MainUI:FindFirstChild("PossibleAssets").ProgressBar
		local cloneLocation = MainUI:FindFirstChild("MainFrame").Assets.AssetFrame

		local newDrag = dragBarAsset:Clone()
		newDrag.Parent = cloneLocation;
		newDrag.Name = "Tab"..self.TabName..tostring(#self.Assets+1)
		
		local props = {
			
			["Visible"] = true;
			
		}
		
		changeProperties(props,newDrag)
		
		local text = newDrag.TextLabel
		local draggerAsset = newDrag.Cover
		
		local player = game.Players.LocalPlayer
		local mouse = player:GetMouse()	
		
		local absoluteSize = newDrag.AbsoluteSize
		local absolutePos = Vector2.new(newDrag.AbsolutePosition.X,newDrag.AbsolutePosition.Y);
		
		spawn(function()
			game:GetService("RunService").RenderStepped:Connect(function()
				absoluteSize = newDrag.AbsoluteSize
				absolutePos = Vector2.new(newDrag.AbsolutePosition.X,newDrag.AbsolutePosition.Y);
				local size,maxSize = draggerAsset.Size.X.Offset,absoluteSize.X
				library.DragBarFills[name] = math.modf(max*(size/maxSize));
				val = math.modf(max*(size/maxSize));
			end)
		end)
		
		game:GetService("TweenService"):Create(draggerAsset,TweenInfo.new(0.2),{Size = UDim2.new(0,((startingVal/max) * absoluteSize.X),1,0)}):Play()
		text.Text = name.." - "..startingVal
		
		newDrag.MouseButton1Click:Connect(function()
			local scale = (mouse.X-absolutePos.X)
			scale = math.clamp(scale,0,absoluteSize.X)
			game:GetService("TweenService"):Create(draggerAsset,TweenInfo.new(0.2),{Size = UDim2.new(0,scale,1,0)}):Play()
			local size,maxSize = draggerAsset.Size.X.Offset,absoluteSize.X
			local a = max*(size/maxSize);
			val = math.modf(a);
			text.Text = name.." - "..val
			f();
		end)
		
		newDrag.MouseButton1Down:Connect(function()
			local scale = (mouse.X-absolutePos.X)
			scale = math.clamp(scale,0,absoluteSize.X)
			game:GetService("TweenService"):Create(draggerAsset,TweenInfo.new(0.2),{Size = UDim2.new(0,scale,1,0)}):Play()
			local size,maxSize = draggerAsset.Size.X.Offset,absoluteSize.X
			local a = max*(size/maxSize);
			val = math.modf(a);
			text.Text = name.." - "..val
			f();
			holdingDrag = true;
		end)
		
		game:GetService("UserInputService").InputEnded:Connect(function(input, gp)
			if input.UserInputType == Enum.UserInputType.MouseButton1 then
				holdingDrag = false;
			end
		end)
		
		mouse.Move:Connect(function()
			if holdingDrag then
				local scale = (mouse.X-absolutePos.X)
				scale = math.clamp(scale,0,absoluteSize.X)
				game:GetService("TweenService"):Create(draggerAsset,TweenInfo.new(0.2),{Size = UDim2.new(0,scale,1,0)}):Play()
				local size,maxSize = draggerAsset.Size.X.Offset,absoluteSize.X
				local a = max*(size/maxSize);
				val = math.modf(a);
				text.Text = name.." - "..val
				f();
			end
		end)
		
		
		table.insert(self.Assets,newDrag)
	end

	function library:Update(newTable, functionalternative)

		local MainUI = self.mainUI
		local asset = self.asset
		local func = self.func

		if not asset then return "No Asset Found" end

		local dpButton = MainUI:FindFirstChild("PossibleAssets").DPButton

		local buttonFrame = asset.Drop.Dropdown

		local scalePlus = 0
		local buttonScale = 1.3

		for i,v in pairs(asset.Drop.Dropdown:GetChildren()) do
			if v:IsA("TextButton") then v:Destroy() end
		end

		local props = {
			["Visible"] = true
		}

		for i = 1,#newTable do
			local newButton = dpButton:Clone()
			local tableVal = newTable[i]
			newButton.Name = tableVal
			newButton.Text = tableVal
			newButton.Parent = buttonFrame
			changeProperties(props, newButton)
			newButton.MouseButton1Up:Connect(function()
				opened = false;
				asset.Icon.Text = "+"
				local t = 0
				game:GetService("TweenService"):Create(asset.Drop, TweenInfo.new(t), {Size = UDim2.new(asset.Drop.Size.X.Scale,asset.Drop.Size.X.Offset,0,asset.Drop.Size.Y.Offset)}):Play()
				if functionalternative then
					functionalternative(tableVal)
				else
					func(tableVal)
				end
			end)
		end
	end


	function library:CreateDropDown(name, selections, func)
		local MainUI = self.FocusedUI
		local dpAsset = MainUI:FindFirstChild("PossibleAssets").Dropdown
		local dpButton = MainUI:FindFirstChild("PossibleAssets").DPButton
		local cloneLocation = MainUI:FindFirstChild("MainFrame").Assets.AssetFrame

		local dp = {}
		local opened = false;

		local newDP = dpAsset:Clone()
		newDP.Parent = cloneLocation;
		newDP.Name = "Tab"..self.TabName..tostring(#self.Assets+1)

		dp.func = func
		dp.asset = newDP
		dp.mainUI = MainUI


		local props = {

			["Visible"] = true;

		}

		changeProperties(props, newDP)

		newDP.Text = name
		
		local scalePlus = 0
		local buttonScale = 1.3

		local totalScale = scalePlus+(#selections*buttonScale)

		local trueDropDown = newDP.Drop
		local buttonFrame = trueDropDown.Dropdown
		local plus = newDP.Icon

		spawn(function()
			while wait(1) do
				local totalAssets = 0;
				for i,v in pairs(buttonFrame:GetChildren()) do
					if v.ClassName ~= "UIListLayout" then
						totalAssets += 1
					end
				end
				totalScale = scalePlus+(totalAssets*buttonScale)
			end
		end)

		for i = 1,#selections do
			local newButton = dpButton:Clone()
			local tableVal = selections[i]
			newButton.Name = tableVal
			newButton.Text = tableVal
			newButton.Parent = buttonFrame
			changeProperties(props, newButton)
			newButton.MouseButton1Up:Connect(function()
				opened = false;
				plus.Text = "+"
				local t = 0
				game:GetService("TweenService"):Create(trueDropDown, TweenInfo.new(t), {Size = UDim2.new(trueDropDown.Size.X.Scale,trueDropDown.Size.X.Offset,0,trueDropDown.Size.Y.Offset)}):Play()
				func(tableVal)
			end)
		end

		local baseTime = 1
		local perButtonTime = 0.05

		newDP.Icon.MouseButton1Up:Connect(function()
			if not opened then
				opened = true;
				plus.Text = "-"
				local t = (baseTime+#selections*perButtonTime)
				game:GetService("TweenService"):Create(trueDropDown, TweenInfo.new(t), {Size = UDim2.new(trueDropDown.Size.X.Scale,trueDropDown.Size.X.Offset,totalScale,trueDropDown.Size.Y.Offset)}):Play()
			else
				opened = false;
				plus.Text = "+"
				local t = (baseTime+#selections*perButtonTime)
				game:GetService("TweenService"):Create(trueDropDown, TweenInfo.new(t), {Size = UDim2.new(trueDropDown.Size.X.Scale,trueDropDown.Size.X.Offset,0,trueDropDown.Size.Y.Offset)}):Play()
			end
		end)

		table.insert(self.Assets,newDP)
		library.DropDowns[name] = newDP
		return setmetatable(dp, library)
	end

	function library:CreateColorAsset(name, startingColor, func)
		
		local MainUI = self.FocusedUI
		local colorAsset = MainUI:FindFirstChild("PossibleAssets").ColorAsset
		local cloneLocation = MainUI:FindFirstChild("MainFrame").Assets.AssetFrame

		local newColor = colorAsset:Clone()
		newColor.Parent = cloneLocation;
		newColor.Name = "Tab"..self.TabName..tostring(#self.Assets+1)
		
		local newColorButton = newColor.Color
		
		local props = {

			["Visible"] = true;

		}
		
		changeProperties(props,newColor)
		
		local newPicker = module.newColorPicker(name)
		newPicker:Initialize(startingColor, func, func, func, newColor)
		
		library.Colors[name] = newPicker
		
		local lastTick;
		local picker = newPicker:returnAsset()
		
		--Double click
		newColorButton.MouseButton1Click:Connect(function()
			if lastTick and math.modf(tick())-math.modf(lastTick) <= 0.2 then
				lastTick = nil;
				newPicker:ToggleUI(newColor.Color.BackgroundColor3)
			else
				lastTick = tick()
			end
		end)
		
		newColor.Color.BackgroundColor3 = startingColor
		colorAsset.ColorRGB.Text = name.." - rgb("..math.modf(startingColor.R*255)..", "..math.modf(startingColor.G*255)..", "..math.modf(startingColor.B*255)..")"
		func()
		
		table.insert(self.Assets,newColor)
	end

	function library:GetColor(name)
		return library.Colors[name].Color
	end

	function library:GetBarFill(bar)
		return library.DragBarFills[bar]
	end

	function library:SetPrimaryTab()
		wait(.2)
		local MainUI = self.FocusedUI
		local assets = self.Assets
		
		for i,v in pairs(MainUI:FindFirstChild("MainFrame").Assets.AssetFrame:GetChildren()) do
			if v and v.Name ~= "UIListLayout" then
				changeProperties({
				["Visible"] = false;
				}, v)
			end
		end
		
		for i,v in pairs(assets) do
			changeProperties({
				["Visible"] = true;
			}, v)
		end
		
	end

	return library
