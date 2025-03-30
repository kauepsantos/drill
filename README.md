local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local LocalPlayer = Players.LocalPlayer

local colors = {
    background = Color3.fromRGB(30, 30, 35),
    titleBar = Color3.fromRGB(20, 20, 25),
    buttonIdle = Color3.fromRGB(45, 45, 55),
    buttonHover = Color3.fromRGB(55, 55, 65),
    tabActive = Color3.fromRGB(65, 65, 75),
    tabInactive = Color3.fromRGB(45, 45, 55),
    textPrimary = Color3.fromRGB(255, 255, 255),
    textSecondary = Color3.fromRGB(200, 200, 200),
    accent = Color3.fromRGB(255, 165, 0),
    toggleOn = Color3.fromRGB(0, 200, 100),
    toggleOff = Color3.fromRGB(200, 50, 50)
}

local screenGui = Instance.new("ScreenGui")
screenGui.Name = "DrillDiggingGUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")

local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 280, 0, 350)
mainFrame.Position = UDim2.new(0.75, 0, 0.5, -175)
mainFrame.BackgroundColor3 = colors.background
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Parent = screenGui

local cornerMain = Instance.new("UICorner")
cornerMain.CornerRadius = UDim.new(0, 10)
cornerMain.Parent = mainFrame

local shadow = Instance.new("ImageLabel")
shadow.Name = "Shadow"
shadow.AnchorPoint = Vector2.new(0.5, 0.5)
shadow.Position = UDim2.new(0.5, 0, 0.5, 0)
shadow.Size = UDim2.new(1, 20, 1, 20)
shadow.BackgroundTransparency = 1
shadow.Image = "rbxassetid://6014261993"
shadow.ImageColor3 = Color3.fromRGB(0, 0, 0)
shadow.ImageTransparency = 0.5
shadow.ScaleType = Enum.ScaleType.Slice
shadow.SliceCenter = Rect.new(49, 49, 450, 450)
shadow.ZIndex = 0
shadow.Parent = mainFrame

local titleBar = Instance.new("Frame")
titleBar.Name = "TitleBar"
titleBar.Size = UDim2.new(1, 0, 0, 40)
titleBar.BackgroundColor3 = colors.titleBar
titleBar.BorderSizePixel = 0
titleBar.ZIndex = 2
titleBar.Parent = mainFrame

local cornerTitle = Instance.new("UICorner")
cornerTitle.CornerRadius = UDim.new(0, 10)
cornerTitle.Parent = titleBar

local cornerFix = Instance.new("Frame")
cornerFix.Name = "CornerFix"
cornerFix.Size = UDim2.new(1, 0, 0, 15)
cornerFix.Position = UDim2.new(0, 0, 1, -10)
cornerFix.BackgroundColor3 = colors.titleBar
cornerFix.BorderSizePixel = 0
cornerFix.ZIndex = 1
cornerFix.Parent = titleBar

local logo = Instance.new("ImageLabel")
logo.Name = "Logo"
logo.Size = UDim2.new(0, 24, 0, 24)
logo.Position = UDim2.new(0, 15, 0.5, -12)
logo.BackgroundTransparency = 1
logo.Image = "rbxassetid://7072706318"
logo.ImageColor3 = colors.accent
logo.ZIndex = 3
logo.Parent = titleBar

local title = Instance.new("TextLabel")
title.Name = "Title"
title.Size = UDim2.new(1, -100, 1, 0)
title.Position = UDim2.new(0, 50, 0, 0)
title.BackgroundTransparency = 1
title.Font = Enum.Font.GothamBold
title.Text = "Buggy_videos"
title.TextColor3 = colors.textPrimary
title.TextSize = 18
title.TextXAlignment = Enum.TextXAlignment.Left
title.ZIndex = 3
title.Parent = titleBar

local closeButton = Instance.new("TextButton")
closeButton.Name = "CloseButton"
closeButton.Size = UDim2.new(0, 30, 0, 30)
closeButton.Position = UDim2.new(1, -40, 0.5, -15)
closeButton.BackgroundColor3 = Color3.fromRGB(220, 50, 50)
closeButton.Text = "Ã—"
closeButton.TextColor3 = colors.textPrimary
closeButton.TextSize = 22
closeButton.Font = Enum.Font.GothamBold
closeButton.ZIndex = 3
closeButton.Parent = titleBar

local cornerClose = Instance.new("UICorner")
cornerClose.CornerRadius = UDim.new(0, 6)
cornerClose.Parent = closeButton

closeButton.MouseButton1Click:Connect(function()
    mainFrame.Visible = false
end)

local tabContainer = Instance.new("Frame")
tabContainer.Name = "TabContainer"
tabContainer.Size = UDim2.new(1, 0, 0, 36)
tabContainer.Position = UDim2.new(0, 0, 0, 40)
tabContainer.BackgroundColor3 = colors.background
tabContainer.BorderSizePixel = 0
tabContainer.ZIndex = 2
tabContainer.Parent = mainFrame

local contentFrame = Instance.new("Frame")
contentFrame.Name = "ContentFrame"
contentFrame.Size = UDim2.new(1, -20, 1, -145)
contentFrame.Position = UDim2.new(0, 10, 0, 85)
contentFrame.BackgroundColor3 = colors.buttonIdle
contentFrame.BorderSizePixel = 0
contentFrame.ZIndex = 2
contentFrame.Parent = mainFrame

local cornerContent = Instance.new("UICorner")
cornerContent.CornerRadius = UDim.new(0, 8)
cornerContent.Parent = contentFrame

local footer = Instance.new("Frame")
footer.Name = "Footer"
footer.Size = UDim2.new(1, 0, 0, 40)
footer.Position = UDim2.new(0, 0, 1, -40)
footer.BackgroundColor3 = colors.titleBar
footer.BorderSizePixel = 0
footer.ZIndex = 2
footer.Parent = mainFrame

local cornerFooter = Instance.new("UICorner")
cornerFooter.CornerRadius = UDim.new(0, 10)
cornerFooter.Parent = footer

local cornerFixFooter = Instance.new("Frame")
cornerFixFooter.Name = "CornerFix"
cornerFixFooter.Size = UDim2.new(1, 0, 0, 15)
cornerFixFooter.Position = UDim2.new(0, 0, 0, -5)
cornerFixFooter.BackgroundColor3 = colors.titleBar
cornerFixFooter.BorderSizePixel = 0
cornerFixFooter.ZIndex = 1
cornerFixFooter.Parent = footer

local authorLabel = Instance.new("TextLabel")
authorLabel.Name = "AuthorLabel"
authorLabel.Size = UDim2.new(0.6, 0, 1, 0)
authorLabel.Position = UDim2.new(0, 15, 0, 0)
authorLabel.BackgroundTransparency = 1
authorLabel.Font = Enum.Font.GothamSemibold
authorLabel.Text = "Made by bugged_videos"
authorLabel.TextColor3 = colors.accent
authorLabel.TextSize = 14
authorLabel.TextXAlignment = Enum.TextXAlignment.Left
authorLabel.ZIndex = 3
authorLabel.Parent = footer

local keybindLabel = Instance.new("TextLabel")
keybindLabel.Name = "KeybindLabel"
keybindLabel.Size = UDim2.new(0.4, -15, 1, 0)
keybindLabel.Position = UDim2.new(0.6, 0, 0, 0)
keybindLabel.BackgroundTransparency = 1
keybindLabel.Font = Enum.Font.Gotham
keybindLabel.Text = "modded_scripts"
keybindLabel.TextColor3 = colors.textSecondary
keybindLabel.TextSize = 12
keybindLabel.TextXAlignment = Enum.TextXAlignment.Right
keybindLabel.ZIndex = 3
keybindLabel.Parent = footer

local tabs = {
    "Egg Hatch",
    "Misc",
    "Auto Win"
}

local tabButtons = {}
local tabFrames = {}
local activeTab = tabs[1]

local function createTab(tabName, tabIndex)
    local tabButton = Instance.new("TextButton")
    tabButton.Name = tabName .. "Tab"
    tabButton.Size = UDim2.new(1 / #tabs, -10, 1, -8)
    tabButton.Position = UDim2.new((tabIndex - 1) / #tabs, 5, 0, 4)
    tabButton.BackgroundColor3 = (tabName == activeTab) and colors.tabActive or colors.tabInactive
    tabButton.Text = tabName
    tabButton.TextColor3 = colors.textPrimary
    tabButton.TextSize = 14
    tabButton.Font = Enum.Font.GothamSemibold
    tabButton.ZIndex = 3
    tabButton.Parent = tabContainer
    
    local cornerTab = Instance.new("UICorner")
    cornerTab.CornerRadius = UDim.new(0, 6)
    cornerTab.Parent = tabButton
    
    local tabFrame = Instance.new("ScrollingFrame")
    tabFrame.Name = tabName .. "Frame"
    tabFrame.Size = UDim2.new(1, -20, 1, -20)
    tabFrame.Position = UDim2.new(0, 10, 0, 10)
    tabFrame.BackgroundTransparency = 1
    tabFrame.BorderSizePixel = 0
    tabFrame.ScrollBarThickness = 4
    tabFrame.ScrollBarImageColor3 = colors.accent
    tabFrame.Visible = tabName == activeTab
    tabFrame.CanvasSize = UDim2.new(0, 0, 0, 0)
    tabFrame.AutomaticSize = Enum.AutomaticSize.Y
    tabFrame.ZIndex = 3
    tabFrame.Parent = contentFrame
    
    tabButton.MouseEnter:Connect(function()
        if tabName ~= activeTab then
            tabButton.BackgroundColor3 = colors.buttonHover
        end
    end)
    
    tabButton.MouseLeave:Connect(function()
        if tabName ~= activeTab then
            tabButton.BackgroundColor3 = colors.tabInactive
        end
    end)
    
    tabButtons[tabName] = tabButton
    tabFrames[tabName] = tabFrame
    
    return tabFrame
end

local function switchTab(tabName)
    for name, button in pairs(tabButtons) do
        button.BackgroundColor3 = (name == tabName) and colors.tabActive or colors.tabInactive
    end
    
    for name, frame in pairs(tabFrames) do
        frame.Visible = name == tabName
    end
    
    activeTab = tabName
end

for i, tabName in ipairs(tabs) do
    local tabFrame = createTab(tabName, i)
    tabButtons[tabName].MouseButton1Click:Connect(function()
        switchTab(tabName)
    end)
end

local features = {}

local function createToggle(parent, name, yPos, callback)
    local toggleButton = Instance.new("TextButton")
    toggleButton.Name = name .. "Button"
    toggleButton.Size = UDim2.new(1, 0, 0, 40)
    toggleButton.Position = UDim2.new(0, 0, 0, yPos)
    toggleButton.BackgroundColor3 = colors.buttonIdle
    toggleButton.BorderSizePixel = 0
    toggleButton.Text = ""
    toggleButton.ZIndex = 4
    toggleButton.Parent = parent
    
    local cornerToggle = Instance.new("UICorner")
    cornerToggle.CornerRadius = UDim.new(0, 6)
    cornerToggle.Parent = toggleButton
    
    local label = Instance.new("TextLabel")
    label.Name = "Label"
    label.Size = UDim2.new(1, -65, 1, 0)
    label.Position = UDim2.new(0, 10, 0, 0)
    label.BackgroundTransparency = 1
    label.Font = Enum.Font.Gotham
    label.Text = name
    label.TextColor3 = colors.textPrimary
    label.TextSize = 14
    label.TextXAlignment = Enum.TextXAlignment.Left
    label.ZIndex = 5
    label.Parent = toggleButton
    
    local toggleFrame = Instance.new("Frame")
    toggleFrame.Name = "ToggleFrame"
    toggleFrame.Size = UDim2.new(0, 40, 0, 22)
    toggleFrame.Position = UDim2.new(1, -50, 0.5, -11)
    toggleFrame.BackgroundColor3 = colors.toggleOff
    toggleFrame.BorderSizePixel = 0
    toggleFrame.ZIndex = 5
    toggleFrame.Parent = toggleButton
    
    local cornerToggleFrame = Instance.new("UICorner")
    cornerToggleFrame.CornerRadius = UDim.new(1, 0)
    cornerToggleFrame.Parent = toggleFrame
    
    local toggleCircle = Instance.new("Frame")
    toggleCircle.Name = "ToggleCircle"
    toggleCircle.Size = UDim2.new(0, 18, 0, 18)
    toggleCircle.Position = UDim2.new(0, 2, 0.5, -9)
    toggleCircle.BackgroundColor3 = colors.textPrimary
    toggleCircle.BorderSizePixel = 0
    toggleCircle.ZIndex = 6
    toggleCircle.Parent = toggleFrame
    
    local cornerCircle = Instance.new("UICorner")
    cornerCircle.CornerRadius = UDim.new(1, 0)
    cornerCircle.Parent = toggleCircle
    
    local featureId = name:gsub("%s+", "_"):lower()
    features[featureId] = {
        enabled = false,
        loopRunning = false
    }
    
    local function updateToggleVisual()
        local tweenInfo = TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out)
        local posEnabled = UDim2.new(1, -20, 0.5, -9)
        local posDisabled = UDim2.new(0, 2, 0.5, -9)
        
        local circleTween = TweenService:Create(toggleCircle, tweenInfo, {
            Position = features[featureId].enabled and posEnabled or posDisabled
        })
        
        local colorTween = TweenService:Create(toggleFrame, tweenInfo, {
            BackgroundColor3 = features[featureId].enabled and colors.toggleOn or colors.toggleOff
        })
        
        circleTween:Play()
        colorTween:Play()
    end
    
    toggleButton.MouseButton1Click:Connect(function()
        features[featureId].enabled = not features[featureId].enabled
        updateToggleVisual()
        
        if features[featureId].enabled then
            if not features[featureId].loopRunning then
                features[featureId].loopRunning = true
                task.spawn(function()
                    while features[featureId].enabled do
                        if features[featureId].enabled then
                            callback()
                        else
                            break
                        end
                        task.wait(0.1)
                    end
                    features[featureId].loopRunning = false
                end)
            end
        end
    end)
    
    toggleButton.MouseEnter:Connect(function()
        toggleButton.BackgroundColor3 = colors.buttonHover
    end)
    
    toggleButton.MouseLeave:Connect(function()
        toggleButton.BackgroundColor3 = colors.buttonIdle
    end)
    
    return toggleButton, featureId
end

local eggTypes = {
    "Lava Egg",
    "Jurassic Egg",
    "Blizzard Egg",
    "Ember Egg",
    "Enigma Egg"
}

local eggHatchTab = tabFrames["Egg Hatch"]
for i, eggType in ipairs(eggTypes) do
    local toggle, featureId = createToggle(eggHatchTab, "Auto Hatch " .. eggType, (i - 1) * 45, function()
        local hatchEvent = game:GetService("ReplicatedStorage").KPets.Events.Hatch
        hatchEvent:FireServer(eggType, 8)
    end)
end

local farmCashTab = tabFrames["Misc"]
local cashToggle, cashFeatureId = createToggle(farmCashTab, "inf cash", 0, function()
    local character = LocalPlayer.Character
    if character then
        for _, part in pairs(character:GetChildren()) do
            local args = {
                [1] = part
            }
            game:GetService("ReplicatedStorage").GiveCash:FireServer(unpack(args))
        end
    end
end)

local infoText = Instance.new("TextLabel")
infoText.Name = "InfoText"
infoText.Size = UDim2.new(1, 0, 0, 60)
infoText.Position = UDim2.new(0, 0, 0, 50)
infoText.BackgroundTransparency = 1
infoText.Font = Enum.Font.Gotham
infoText.Text = "Automatically collects cash at rapid intervals for maximum profits."
infoText.TextColor3 = colors.textSecondary
infoText.TextSize = 13
infoText.TextWrapped = true
infoText.ZIndex = 4
infoText.Parent = farmCashTab

local autoWinTab = tabFrames["Auto Win"]
local winLocations = {
    {
        name = "Auto Win (Frozen)",
        position = Vector3.new(4373.234, 6907.957, 123.215)
    },
    {
        name = "Auto Win (Jungle)",
        position = Vector3.new(9154.235, 6907.957, 123.215)
    },
    {
        name = "Auto Win (Magic World)",
        position = Vector3.new(14070.736, 6907.957, 123.215)
    }
}

local lastUsedTime = {}
for _, location in ipairs(winLocations) do
    lastUsedTime[location.name] = 0
end

for i, location in ipairs(winLocations) do
    local toggle, featureId = createToggle(autoWinTab, location.name, (i - 1) * 45, function()
        local character = LocalPlayer.Character
        local humanoid = character and character:FindFirstChild("Humanoid")
        local rootPart = character and character:FindFirstChild("HumanoidRootPart")
        local currentTime = tick()
        
        if (currentTime - lastUsedTime[location.name]) < 1 then
            return
        end
        
        lastUsedTime[location.name] = currentTime
        
        if rootPart and humanoid then
            local originalJumpPower = humanoid.JumpPower
            local originalJumpHeight = humanoid.JumpHeight
            
            humanoid.JumpPower = 0
            humanoid.JumpHeight = 0
            
            local randomOffset = Vector3.new(math.random(-2, 2) * 0.1, 0, math.random(-2, 2) * 0.1)
            rootPart.CFrame = CFrame.new(location.position + randomOffset)
            
            task.delay(0.5, function()
                if humanoid then
                    humanoid.JumpPower = originalJumpPower
                    humanoid.JumpHeight = originalJumpHeight
                end
            end)
        end
    end)
    
    local locationInfo = Instance.new("TextLabel")
    locationInfo.Name = "WinInfoText_" .. i
    locationInfo.Size = UDim2.new(1, 0, 0, 20)
    locationInfo.Position = UDim2.new(0, 0, 0, (i - 1) * 45 + 40)
    locationInfo.BackgroundTransparency = 1
    locationInfo.Font = Enum.Font.Gotham
    locationInfo.Text = "Teleports to " .. location.name:gsub("Auto Win ", "") .. " area."
    locationInfo.TextColor3 = colors.textSecondary
    locationInfo.TextSize = 11
    locationInfo.TextWrapped = true
    locationInfo.ZIndex = 4
    locationInfo.Parent = autoWinTab
end

UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if not gameProcessed and input.KeyCode == Enum.KeyCode.K then
        if screenGui and screenGui.Parent then
            mainFrame.Visible = not mainFrame.Visible
            if mainFrame.Visible then
                mainFrame.Position = UDim2.new(0.75, 0, 1.5, 0)
                local tweenInfo = TweenInfo.new(0.6, Enum.EasingStyle.Quart, Enum.EasingDirection.Out)
                local targetPosition = UDim2.new(0.75, 0, 0.5, -175)
                local tween = TweenService:Create(mainFrame, tweenInfo, {
                    Position = targetPosition
                })
                tween:Play()
            end
        end
    end
end)

mainFrame.Position = UDim2.new(0.75, 0, 1.5, 0)
mainFrame.Visible = true
local tweenInfo = TweenInfo.new(0.6, Enum.EasingStyle.Quart, Enum.EasingDirection.Out)
local targetPosition = UDim2.new(0.75, 0, 0.5, -175)
local tween = TweenService:Create(mainFrame, tweenInfo, {
    Position = targetPosition
})
tween:Play()
