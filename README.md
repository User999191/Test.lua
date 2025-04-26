--// SERVICES \\--
local TweenService = game:GetService("TweenService")
local Input = game:GetService("UserInputService")
local CoreGui = game:GetService("CoreGui")

--// SCREEN GUI \\--
local SG = Instance.new("ScreenGui")
SG.Name = "reach.cc"
SG.Parent = CoreGui

--// MAIN FRAME \\--
local MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.Size = UDim2.new(0, 550, 0, 400)
MainFrame.Position = UDim2.new(0.5, -275, 0.5, -200)
MainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.Parent = SG

local MainCorner = Instance.new("UICorner")
MainCorner.CornerRadius = UDim.new(0, 12)
MainCorner.Parent = MainFrame

--// TOP SECTION \\--
local TopSection = Instance.new("Frame")
TopSection.Name = "TopSection"
TopSection.Size = UDim2.new(1, 0, 0, 40)
TopSection.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
TopSection.BorderSizePixel = 0
TopSection.Parent = MainFrame

local TopCorner = Instance.new("UICorner")
TopCorner.CornerRadius = UDim.new(0, 12)
TopCorner.Parent = TopSection

local TopText = Instance.new("TextLabel")
TopText.Name = "TopText"
TopText.Size = UDim2.new(0, 200, 0, 30)
TopText.Position = UDim2.new(0, 10, 0, 5)
TopText.BackgroundTransparency = 1
TopText.Text = "reach.cc"
TopText.TextColor3 = Color3.fromRGB(255, 255, 255)
TopText.Font = Enum.Font.Code
TopText.TextSize = 20
TopText.TextXAlignment = Enum.TextXAlignment.Left
TopText.Parent = TopSection

--// SECTION TAB \\--
local SectionTab = Instance.new("Frame")
SectionTab.Name = "SectionTab"
SectionTab.Size = UDim2.new(0, 120, 1, -40)
SectionTab.Position = UDim2.new(0, 0, 0, 40)
SectionTab.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
SectionTab.BorderSizePixel = 0
SectionTab.Parent = MainFrame

local SectionLine = Instance.new("Frame")
SectionLine.Name = "SectionLine"
SectionLine.Size = UDim2.new(1, 0, 0, 2)
SectionLine.Position = UDim2.new(0, 0, 0, 45)
SectionLine.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
SectionLine.BorderSizePixel = 0
SectionLine.Parent = SectionTab

--// BUTTON TABS \\--
local ButtonTab1 = Instance.new("TextButton")
ButtonTab1.Name = "ButtonTab1"
ButtonTab1.Size = UDim2.new(1, -10, 0, 30)
ButtonTab1.Position = UDim2.new(0, 5, 0, 10)
ButtonTab1.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
ButtonTab1.Text = "Rage"
ButtonTab1.TextColor3 = Color3.fromRGB(255, 255, 255)
ButtonTab1.Font = Enum.Font.Code
ButtonTab1.TextSize = 14
ButtonTab1.BorderSizePixel = 0
ButtonTab1.Parent = SectionTab

local ButtonTab2 = Instance.new("TextButton")
ButtonTab2.Name = "ButtonTab2"
ButtonTab2.Size = UDim2.new(1, -10, 0, 30)
ButtonTab2.Position = UDim2.new(0, 5, 0, 50)
ButtonTab2.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
ButtonTab2.Text = "Settings"
ButtonTab2.TextColor3 = Color3.fromRGB(255, 255, 255)
ButtonTab2.Font = Enum.Font.Code
ButtonTab2.TextSize = 14
ButtonTab2.BorderSizePixel = 0
ButtonTab2.Parent = SectionTab

--// ELEMENT FRAMES \\--
local function createElementFrame(name)
    local frame = Instance.new("Frame")
    frame.Name = name
    frame.Size = UDim2.new(0, 260, 0, 200)
    frame.Position = UDim2.new(0, 130, 0, 60)
    frame.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
    frame.BorderSizePixel = 0
    frame.Visible = false
    frame.Parent = MainFrame

    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 8)
    corner.Parent = frame

    return frame
end

local Tab1Frame = createElementFrame("Tab1Frame")
local Tab2Frame = createElementFrame("Tab2Frame")

--// TAB 1 CONTENT \\--
local WelcomeLabel = Instance.new("TextLabel")
WelcomeLabel.Name = "WelcomeLabel"
WelcomeLabel.Size = UDim2.new(1, 0, 0, 30)
WelcomeLabel.Position = UDim2.new(0, 0, 0, 10)
WelcomeLabel.BackgroundTransparency = 1
WelcomeLabel.Text = "Welcome to reach.cc!"
WelcomeLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
WelcomeLabel.Font = Enum.Font.Code
WelcomeLabel.TextSize = 18
WelcomeLabel.Parent = Tab1Frame

local ToggleFrame1 = Instance.new("Frame")
ToggleFrame1.Name = "ToggleFrame1"
ToggleFrame1.Size = UDim2.new(0, 240, 0, 40)
ToggleFrame1.Position = UDim2.new(0, 10, 0, 50)
ToggleFrame1.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
ToggleFrame1.BorderSizePixel = 0
ToggleFrame1.Parent = Tab1Frame

local ToggleCorner1 = Instance.new("UICorner")
ToggleCorner1.CornerRadius = UDim.new(0, 6)
ToggleCorner1.Parent = ToggleFrame1

--// Toggle Button Setup \--
local ToggleButton1 = Instance.new("TextButton")
ToggleButton1.Name = "ToggleButton1"
ToggleButton1.Size = UDim2.new(1, -10, 1, -10)
ToggleButton1.Position = UDim2.new(0, 5, 0, 5)
ToggleButton1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
ToggleButton1.Text = "Toggle: OFF"
ToggleButton1.TextColor3 = Color3.fromRGB(255, 255, 255)
ToggleButton1.Font = Enum.Font.Code
ToggleButton1.TextSize = 14
ToggleButton1.BorderSizePixel = 0
ToggleButton1.Parent = ToggleFrame1 -- Make sure ToggleFrame1 exists in the UI!

local toggleState1 = false
ToggleButton1.MouseButton1Click:Connect(function()
    toggleState1 = not toggleState1
    ToggleButton1.Text = toggleState1 and "Toggle: ON" or "Toggle: OFF"
end)

local TextboxFrame1 = Instance.new("Frame")
TextboxFrame1.Name = "TextboxFrame1"
TextboxFrame1.Size = UDim2.new(0, 240, 0, 40)
TextboxFrame1.Position = UDim2.new(0, 10, 0, 100)
TextboxFrame1.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
TextboxFrame1.BorderSizePixel = 0
TextboxFrame1.Parent = Tab1Frame

local TextboxCorner1 = Instance.new("UICorner")
TextboxCorner1.CornerRadius = UDim.new(0, 6)
TextboxCorner1.Parent = TextboxFrame1

local TextBoxElement1 = Instance.new("TextBox")
TextBoxElement1.Name = "TextBoxElement1"
TextBoxElement1.Size = UDim2.new(1, -10, 1, -10)
TextBoxElement1.Position = UDim2.new(0, 5, 0, 5)
TextBoxElement1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
TextBoxElement1.Text = "Type here..."
TextBoxElement1.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBoxElement1.Font = Enum.Font.Code
TextBoxElement1.TextSize = 14
TextBoxElement1.ClearTextOnFocus = true
TextBoxElement1.BorderSizePixel = 0
TextBoxElement1.Parent = TextboxFrame1

--// TAB 2 CONTENT \\--
local ToggleFrame2 = Instance.new("Frame")
ToggleFrame2.Name = "ToggleFrame2"
ToggleFrame2.Size = UDim2.new(0, 240, 0, 40)
ToggleFrame2.Position = UDim2.new(0, 10, 0, 20)
ToggleFrame2.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
ToggleFrame2.BorderSizePixel = 0
ToggleFrame2.Parent = Tab2Frame

local ToggleCorner2 = Instance.new("UICorner")
ToggleCorner2.CornerRadius = UDim.new(0, 6)
ToggleCorner2.Parent = ToggleFrame2

local ToggleButton2 = Instance.new("TextButton")
ToggleButton2.Name = "ToggleButton2"
ToggleButton2.Size = UDim2.new(1, -10, 1, -10)
ToggleButton2.Position = UDim2.new(0, 5, 0, 5)
ToggleButton2.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
ToggleButton2.Text = "Second Toggle: OFF"
ToggleButton2.TextColor3 = Color3.fromRGB(255, 255, 255)
ToggleButton2.Font = Enum.Font.Code
ToggleButton2.TextSize = 14
ToggleButton2.BorderSizePixel = 0
ToggleButton2.Parent = ToggleFrame2

local toggleState2 = false
ToggleButton2.MouseButton1Click:Connect(function()
    toggleState2 = not toggleState2
    ToggleButton2.Text = toggleState2 and "Second Toggle: ON" or "Second Toggle: OFF"
end)

local TextboxFrame2 = Instance.new("Frame")
TextboxFrame2.Name = "TextboxFrame2"
TextboxFrame2.Size = UDim2.new(0, 240, 0, 40)
TextboxFrame2.Position = UDim2.new(0, 10, 0, 80)
TextboxFrame2.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
TextboxFrame2.BorderSizePixel = 0
TextboxFrame2.Parent = Tab2Frame

local TextboxCorner2 = Instance.new("UICorner")
TextboxCorner2.CornerRadius = UDim.new(0, 6)
TextboxCorner2.Parent = TextboxFrame2

local TextBoxElement2 = Instance.new("TextBox")
TextBoxElement2.Name = "TextBoxElement2"
TextBoxElement2.Size = UDim2.new(1, -10, 1, -10)
TextBoxElement2.Position = UDim2.new(0, 5, 0, 5)
TextBoxElement2.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
TextBoxElement2.Text = "Second Tab Type..."
TextBoxElement2.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBoxElement2.Font = Enum.Font.Code
TextBoxElement2.TextSize = 14
TextBoxElement2.ClearTextOnFocus = true
TextBoxElement2.BorderSizePixel = 0
TextBoxElement2.Parent = TextboxFrame2

--// TAB SWITCHING \\--
ButtonTab1.MouseButton1Click:Connect(function()
    Tab1Frame.Visible = true
    Tab2Frame.Visible = false
end)

ButtonTab2.MouseButton1Click:Connect(function()
    Tab1Frame.Visible = false
    Tab2Frame.Visible = true
end)

-- Set default tab
Tab1Frame.Visible = true
Tab2Frame.Visible = false

--// WELCOME ANIMATION \\--
task.spawn(function()
    while task.wait(1) do
        local fadeIn = TweenService:Create(WelcomeLabel, TweenInfo.new(0.2, Enum.EasingStyle.Sine, Enum.EasingDirection.Out), {TextTransparency = 1})
        local fadeOut = TweenService:Create(WelcomeLabel, TweenInfo.new(0.2, Enum.EasingStyle.Sine, Enum.EasingDirection.In), {TextTransparency = 0})
        fadeIn:Play()
        fadeIn.Completed:Wait()
        fadeOut:Play()
    end
end)

print("Reach.cc Loaded")
