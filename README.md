-- KLZIN King

-- Proteção contra múltiplas execuções
if getgenv().klzinKingLoaded then
    return
end
getgenv().klzinKingLoaded = true

-- Criar GUI
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "KLZINKing"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = game.CoreGui

local Frame = Instance.new("Frame")
Frame.Name = "MainFrame"
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
Frame.Position = UDim2.new(0.35, 0, 0.3, 0)
Frame.Size = UDim2.new(0, 350, 0, 250)
Frame.Active = true
Frame.Draggable = true

local Title = Instance.new("TextLabel")
Title.Name = "Title"
Title.Parent = Frame
Title.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Font = Enum.Font.GothamBold
Title.Text = "KLZIN King"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextSize = 28

local Button1 = Instance.new("TextButton")
Button1.Name = "ScriptButton"
Button1.Parent = Frame
Button1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button1.Position = UDim2.new(0.1, 0, 0.35, 0)
Button1.Size = UDim2.new(0.8, 0, 0.2, 0)
Button1.Font = Enum.Font.Gotham
Button1.Text = "Executar Script"
Button1.TextColor3 = Color3.fromRGB(255, 255, 255)
Button1.TextSize = 20

Button1.MouseButton1Click:Connect(function()
    -- Troque este link pelo seu script do GitHub ou Pastebin
    loadstring(game:HttpGet("https://pastebin.com/raw/YOUR_SCRIPT_LINK"))()
end)

local Close = Instance.new("TextButton")
Close.Name = "Fechar"
Close.Parent = Frame
Close.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
Close.Position = UDim2.new(0.85, 0, 0, 0)
Close.Size = UDim2.new(0.15, 0, 0, 50)
Close.Font = Enum.Font.GothamBold
Close.Text = "X"
Close.TextColor3 = Color3.fromRGB(255, 255, 255)
Close.TextSize = 24

Close.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)
