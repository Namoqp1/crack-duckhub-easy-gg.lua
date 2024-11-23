local DuskHub = tostring(game.PlaceId)
if DuskHub == "17167990958" then
    RF = true
elseif DuskHub == "16281300371" then
    BB = true
elseif DuskHub == "17545130379" then
    RY = true
elseif DuskHub == "10260193230" then
    MM = true
end
local Fluent = loadstring(game:HttpGet("https://raw.githubusercontent.com/Lucas-Lua/ui/main/m"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/ZAZA.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/InterfaceManager.lua.txt"))()
local ScreenGui1 = Instance.new("ScreenGui")
local ImageButton1 = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

ScreenGui1.Name = "ImageButton"
ScreenGui1.Parent = game.CoreGui
ScreenGui1.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton1.Parent = ScreenGui1
ImageButton1.BackgroundTransparency = 1
ImageButton1.BorderSizePixel = 0
ImageButton1.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
ImageButton1.Size = UDim2.new(0, 50, 0, 50)
ImageButton1.Draggable = true
ImageButton1.Image = "rbxassetid://18573206393"
ImageButton1.MouseButton1Down:Connect(function()
  game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
  game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
end)
UICorner.Parent = ImageButton1


if RF then
local Fluent = loadstring(game:HttpGet("https://raw.githubusercontent.com/Lucas-Lua/ui/main/m"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/ZAZA.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/InterfaceManager.lua.txt"))()

local ScreenGui1 = Instance.new("ScreenGui")
local ImageButton1 = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

ScreenGui1.Name = "ImageButton"
ScreenGui1.Parent = game.CoreGui
ScreenGui1.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton1.Parent = ScreenGui1
ImageButton1.BackgroundTransparency = 1
ImageButton1.BorderSizePixel = 0
ImageButton1.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
ImageButton1.Size = UDim2.new(0, 50, 0, 50)
ImageButton1.Draggable = true
ImageButton1.Image = "rbxassetid://18573206393"
ImageButton1.MouseButton1Down:Connect(function()
  game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
  game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
end)
UICorner.Parent = ImageButton1

local Window = Fluent:CreateWindow({
	Title = "Rock Fruit Ultimate Script",
	SubTitle = "By > Dazzle Hub ",
	TabWidth = 130,
	Size = UDim2.fromOffset(480, 400),
	Acrylic = false, 
	Theme = "Dark",
	MinimizeKey = Enum.KeyCode.RightControl
})

local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "gamepad-2" }),
    Skill = Window:AddTab({ Title = "Skill", Icon = "sword" }),
    Store = Window:AddTab({ Title = "Inventory", Icon = "backpack" }),
    Event = Window:AddTab({ Title = "Boss Event", Icon = "rocket" }),
    Item = Window:AddTab({ Title = "Item", Icon = "axe" }),
    Stats = Window:AddTab({ Title = "Stats", Icon = "align-end-horizontal" }),
    Misc = Window:AddTab({ Title = "Misc", Icon = "align-left" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}

Tabs.Main:AddDropdown("Select Method", {
        Title = "Select Method",
        Values = {"Upper","Behind","Below"},
        Multi = false,
        Default = 1,
        Callback = function(v)
          _G.Method = v
        end
    })
    
    
    
    spawn(function()
        while wait() do 
            pcall(function()
                if _G.Method == "Behind" then
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)
                elseif _G.Method == "Below" then
                    MethodFarm = CFrame.new(0,-_G.DistanceMob,0) * CFrame.Angles(math.rad(90),0,0)
                elseif _G.Method == "Upper" then
                    MethodFarm = CFrame.new(0,_G.DistanceMob,0)  * CFrame.Angles(math.rad(-90),0,0)
                else
                    MethodFarm = CFrame.new(0,_G.DistanceMob,0)  * CFrame.Angles(math.rad(-90),0,0)
                end
            end)
        end
    end)


Tabs.Main:AddInput("Input", {
        Title = "Distance Mob",
        Default = 0,
        Placeholder = " ",
        Numeric = true,
        Finished = false,
        Callback = function(gay)
         _G.DistanceMob = gay
        end
    })



function Attack()
    local VirtualUser = game:GetService('VirtualUser')
    VirtualUser:CaptureController()
    VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
end
local Wea = Tabs.Main:AddSection("| Weapon") 

local Weaponlist = {}

local SelectWeapon = Wea:AddDropdown("SelectWeapon", {
    Title = "Select Weapon",
    Values = Weaponlist,
    Multi = false,
    Default = false,
    Callback = function(selectedWeapon)
        _G.Weaponnn = selectedWeapon
    end
})

local function RefreshWeaponList()
    Weaponlist = {}
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
    if v:IsA("Tool") then
       table.insert(Weaponlist ,v.Name)
    end
end
for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
    if v:IsA("Tool") then
       table.insert(Weaponlist, v.Name)
    end
end
    SelectWeapon:SetValues(Weaponlist)
end

Wea:AddButton({
    Title = "Refresh Weapon",
    Description = "",
    Callback = RefreshWeaponList
})

RefreshWeaponList()


spawn(function()
  while wait() do
    xpcall(function()
      if _G.AutoStoreFruit or _G.AutoOr or _G.AutoStoreOrbgg or _G.AutoBossspawnAizen or _G.AutoFarmEnabled or _G.AutoFarm then
        repeat
          task.wait(1)
          EquipWeapon(_G.Weaponnn)
          wait(1)
        until _G.AutoStoreFruit or _G.AutoOr or _G.AutoStoreOrbgg or _G.AutoBossspawnAizen or _G.AutoFarm or _G.AutoFarmEnabled
      end 
    end, function(err)
    end)
  end
end)


function EquipWeapon(ToolSe)
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			Tool = game.Players.LocalPlayer.Backpack:WaitForChild(ToolSe)
			wait(30)
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
			wait(0.10)
	end
end

local Farm = Tabs.Main:AddSection("| Auto Farm")  
local Mon = {}
local MonSet = {}
for i, v in pairs(game:GetService("Workspace").Mob:GetChildren()) do
    if not MonSet[v.Name] then
        table.insert(Mon, v.Name)
        MonSet[v.Name] = true
    end
end
_G.SelectedStands = {}

local MultiDropdown = Farm:AddDropdown("Select Mon", {
    Title = "Select Mon",
    Description = "",
    Values = Mon,
    Multi = true,
    Default = {},
    Callback = function(selected)
        _G.SelectedStands = selected
    end
})

MultiDropdown:OnChanged(function(selected)
    _G.SelectedStands = {}
    for stand, isSelected in pairs(selected) do
        if isSelected then
            table.insert(_G.SelectedStands, stand)
        end
    end
end)

Farm:AddToggle("Auto Farm Mon", {
    Title = "Auto Farm Mon",
    Default = false,
    Callback = function(AutoFarm1)
        _G.AutoFarm1 = AutoFarm1
    end
})

spawn(function()
    while task.wait() do
        if _G.AutoFarm1 then
            pcall(function()
                for _, v in pairs(game:GetService("Workspace").Mob:GetChildren()) do
                    if table.find(_G.SelectedStands, v.Name) and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 1 then
                        v.Humanoid.WalkSpeed = 0
                        v.Humanoid.JumpPower = 0
                        repeat
                            task.wait()
                            Attack()
                            TP(v.HumanoidRootPart.CFrame*MethodFarm)
                        until not _G.AutoFarm1 or v.Humanoid.Health <= 0
                    end
                end
            end)
        end
    end
end)

_G.autost = {}
for _, v in pairs(game.ReplicatedStorage.Tools:GetDescendants()) do
    if v:IsA("Tool") and not v:IsDescendantOf(game.ReplicatedStorage.Tools.Weapon) then
        table.insert(_G.autost, v.Name)
    end
end

Tabs.Store:AddToggle("Grab Fruit", {
      Title = "Grab Item", 
      Description = "Fruit / Item",
      Default = false, 
      Callback = function(Fruit) 
      _G.Grab = Fruit
  end})


spawn(function()
        while wait() do
            if _G.Grab then
                pcall(function()
                    for i,v in pairs(game.Workspace.Fruits:GetChildren()) do
                        if v:IsA("Tool") then
                            v.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                        end
                    end    
                end)
            end
        end
end)
  
  


 Tabs.Store:AddToggle("Auto Store Fruit", {
        Title = "Auto Store Fruit", 
        Default = false, 
        Description = "Fruit / Item / Orb",
        Callback = function(AutoStoreFruit) 
        _G.AutoStoreFruit = AutoStoreFruit
    end})
  



local lastEquippedTool = nil
spawn(function()
    while true do
        wait(3)
        if _G.AutoStoreFruit or _G.AutoOr then
            pcall(function()
                local player = game.Players.LocalPlayer
                local backpack = player.Backpack
                local humanoid = player.Character and player.Character:FindFirstChildOfClass("Humanoid")
                local dialogueGui = game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Dialogue")
                local isVisible = dialogueGui and dialogueGui:FindFirstChild("Frame")
                if isVisible then return end
                if not humanoid then return end
                local currentTool = humanoid:FindFirstChildOfClass("Tool")
                if currentTool and table.find(_G.autost, currentTool.Name) then
                    return
                end
                if currentTool and not table.find(_G.autost, currentTool.Name) then
                    currentTool:Destroy()
                end
                for i, v in pairs(backpack:GetChildren()) do
                    if table.find(_G.autost, v.Name) then
                        humanoid:EquipTool(v)
                        lastEquippedTool = v
                        break
                    end
                end
            end)
        end
    end
end)


spawn(function()
    while wait() do
        pcall(function()
            if _G.AutoStoreFruit or _G.AutoOr or _G.AutoStoreOrbgg or _G.AutoBossspawnAizen then
                for i2, v in pairs(game.Players.LocalPlayer.PlayerGui:GetChildren()) do
                    if string.find(v.Name, "Dialogue") then
                   v.Frame["3"].Position = UDim2.new(0, -800 ,0, -700)
                   v.Frame["3"].Size = UDim2.new(5000, 5000, 5000, 5000)
                   v.Frame["3"].BackgroundTransparency = 1
                   v.Frame["3"].ImageTransparency = 1
                    end
                end
            end
        end)
    end
end)



spawn(function()
    while wait() do
      if _G.AutoStoreFruit or _G.AutoOr or _G.AutoStoreOrbgg or _G.AutoBossspawnAizen then
game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
end
end
end)


--Item


function TP(CFrame)
    pcall(function()
        local humanoidRootPart = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            humanoidRootPart.CFrame = CFrame
        else
            wait(1)
        end
    end)
end

Tabs.Item:AddToggle("Auto AFK Tires", {
    Title = "Auto AFK Tires", 
    Default = false, 
    Callback = function(A) 
        _G.AFKTires = A
        if A then
            spawn(function()
                while _G.AFKTires do 
                    TP(CFrame.new(-1090.22766, 15.7292318, -2619.76099, -0.489067197, -1.05199751e-08, 0.872246087, 1.97427563e-09, 1, 1.31677611e-08, -0.872246087, 8.16197421e-09, -0.489067197))
                    wait(0.5)
                end
            end)
        end
    end
})



local Click = Tabs.Item:AddSection("| Auto Farm")  

Click:AddToggle("AutoS", {
    Title = "Auto Click Delta",
    Default = false,
    Callback = function(enabled)
        _G.ACgaa = enabled
    end
})

spawn(function()
    while wait(0.10) do
        if _G.ACgaa then
          pcall(function()
                for i = 1,30 do
      fireclickdetector(game.Workspace.Delta.Part.ClickDetector)
      TP(game.Workspace.Delta.Part)
                end
            end)
        end
    end
end)


Click:AddToggle("AutoS", {
    Title = "Auto Click Dragon Blade",
    Default = false,
    Callback = function(kkl)
        _G.Hak = kkl
    end
})

spawn(function()
    while wait(0.10) do
        if _G.Hak then
          pcall(function()
                for i = 1,30 do
      fireclickdetector(game.Workspace.Rock.Part.ClickDetector)
      TP(game.Workspace.Rock.Part)
                end
            end)
        end
    end
end)



Tabs.Event:AddToggle("Auto Farm Orb Black", {
    Title = "Auto Farm Sukuna", 
    Default = false, 
    Description = "Auto Farm | Farm Orb | Farm Boss",
    Callback = function(AutoFarmOrb) 
        _G.Aizen = AutoFarmOrb
    end
})



localplayer = game.Players.LocalPlayer
local backpack = localplayer.Backpack

Azzx = CFrame.new(-1951.80371, 15.9536476, -422.386139, 0.823755026, 8.34558112e-09, -0.566945851, -5.21725685e-09, 1, 7.13972836e-09, 0.566945851, -2.92348501e-09, 0.823755026)
spawn(function()
    while task.wait() do
        if _G.Aizen then
            pcall(function()
                local localplayer = game.Players.LocalPlayer

                if workspace.Mob:FindFirstChild("Sukuna") then
                    for _, v in pairs(game:GetService("Workspace").Mob:GetChildren()) do
                        if v.Name == "Sukuna" and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                            v.HumanoidRootPart.Size = Vector3.new(10, 10, 10)
                            v.HumanoidRootPart.Transparency = 0.9
                            v.Humanoid.WalkSpeed = 0
                            v.Humanoid.JumpPower = 0
                            repeat task.wait()
                              Attack()
                                TP(v.HumanoidRootPart.CFrame*MethodFarm)
                            until v.Humanoid.Health <= 0
                        end
                    end
                elseif localplayer.Backpack:FindFirstChild("Ord Demon") then
                    TP(Azzx)
                    for i, v in pairs(game:GetService("Workspace"):GetDescendants()) do
                        if v.ClassName == "ProximityPrompt" then
                            fireproximityprompt(v, 30)
                        end
                    end
                elseif not localplayer.Backpack:FindFirstChild("Ord Demon") then
                    for _, v in pairs(game:GetService("Workspace").Mob:GetChildren()) do
                        if v.Name == "Demon Man" and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                            v.HumanoidRootPart.Size = Vector3.new(10, 10, 10)
                            v.HumanoidRootPart.Transparency = 0.9
                            v.Humanoid.WalkSpeed = 0
                            v.Humanoid.JumpPower = 0
                            repeat task.wait()
                            TP(v.HumanoidRootPart.CFrame*MethodFarm)
                              Attack()
                              EquipWeapon(_G.Weaponnn)
                            until v.Humanoid.Health <= 0
                        else
                            print("Demon Man not found or not valid")
                        end
                    end
                end
            end)
        end
    end
    wait(0.1)
end)


Tabs.Skill:AddToggle("Z", {
      Title = "Z", 
      Default = false, 
      Callback = function(z) 
      _G.Z = Z
  end})

spawn(function()
    pcall(function()
        while wait() do
        if _G.Z then
local args = {
    [1] = _G.Weaponnn,
    [2] = "z"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Skill:AddToggle("X", {
      Title = "X", 
      Default = false, 
      Callback = function(X) 
      _G.X = X
  end})
   


spawn(function()
    pcall(function()
        while wait() do
        if _G.X then
local args = {
    [1] = _G.Weaponnn,
    [2] = "x"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Skill:AddToggle("C", {
      Title = "C", 
      Default = false, 
      Callback = function(C) 
      _G.C = C
  end})


    
spawn(function()
    pcall(function()
        while wait() do
        if _G.C then
local args = {
    [1] = _G.Weaponnn,
    [2] = "c"
}

game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Skill:AddToggle("V", {
      Title = "V", 
      Default = false, 
      Callback = function(V) 
      _G.V = V
  end})

spawn(function()
    pcall(function()
        while wait() do
        if _G.V then
local args = {
    [1] = _G.Weaponnn,
    [2] = "v"
}
game:GetService("ReplicatedStorage"):WaitForChild("Remote"):WaitForChild("Action"):FireServer(unpack(args))
end
end
end)
end)

nocooldown = hookfunction(wait, function(seconds)
return nocooldown(0.1)
end)


Tabs.Stats:AddSlider("Slider", {
        Title = "Point",
        Description = "Use Point",
        Default = 5,
        Min = 0,
        Max = 100,
        Rounding = 0,
        Callback = function(Ve)
            _G.Ve = Ve
        end
    })


Tabs.Stats:AddButton({
    Title = "Refresh Stats",
    Description = "",
    Callback = function()
      local args = {
          [1] = "ResetStats"
      }
      
      game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer(unpack(args))
    end
    })

Tabs.Stats:AddToggle("Auto Stats Melee", {
      Title = "Auto Stats Melee", 
      Default = false, 
      Callback = function(Melee) 
      _G.Melee = Melee
  end})


spawn(function()
pcall(function()
while task.wait() do
if _G.Melee then
local args = {
    [1] = "UpStats",
    [2] = "Melee",
    [3] = _G.Ve
}

game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Stats:AddToggle("Auto Stats Sword", {
      Title = "Auto Stats Sword", 
      Default = false, 
      Callback = function(Sword) 
      _G.Sword = Sword
  end})


spawn(function()
pcall(function()
while task.wait() do
if _G.Sword then
local args = {
    [1] = "UpStats",
    [2] = "Sword",
    [3] = _G.Ve
}

game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Stats:AddToggle("Auto Stats DevilFruit", {
      Title = "Auto Stats DevilFruit", 
      Default = false, 
      Callback = function(DevilFruit) 
      _G.DevilFruit = DevilFruit
  end})


spawn(function()
pcall(function()
while task.wait() do
if _G.DevilFruit then
local args = {
    [1] = "UpStats",
    [2] = "DevilFruit",
    [3] = _G.Ve
}

game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Stats:AddToggle("Auto Stats Special", {
      Title = "Auto Stats Special", 
      Default = false, 
      Callback = function(Special) 
      _G.Special = Special
  end})


spawn(function()
pcall(function()
while task.wait() do
if _G.Special then
local args = {
    [1] = "UpStats",
    [2] = "Special",
    [3] = _G.Ve
}

game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer(unpack(args))
end
end
end)
end)

Tabs.Stats:AddToggle("Auto Stats Defense", {
      Title = "Auto Stats Defense", 
      Default = false, 
      Callback = function(Defense) 
      _G.Defense = Defense
  end})



spawn(function()
pcall(function()
while task.wait() do
if _G.Defense then
local args = {
    [1] = "UpStats",
    [2] = "Defense",
    [3] = _G.Ve
}

game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("System"):FireServer(unpack(args))
end
end
end)
end)
Tabs.Misc:AddToggle("Anti AFK", {
      Title = "Anti AFK", 
      Default = true, 
      Callback = function(cbx) 
      _G.AntiAFKEnabled = cbx
      		local vu = game:GetService("VirtualUser")
          game.Players.LocalPlayer.Idled:connect(function()
              if _G.AntiAFKEnabled then
                  vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                  wait(1)
                  vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                  end
            end)
  end})


Tabs.Misc:AddToggle("White Screen", {
      Title = "White Screen", 
      Default = false, 
      Callback = function(cb) 
      _G.White_Screen = cb
  end})


spawn(function()
    while true do
        wait()
      
        if _G.White_Screen then
            game:GetService("RunService"):Set3dRenderingEnabled(false)
        else
            game:GetService("RunService"):Set3dRenderingEnabled(true)
        end
    end
end)

Tabs.Misc:AddButton({
    Title = "Boost FPS",
    Description = "",
    Callback = function()
      local decalsyeeted = true
      			local g, w, l = game, game.Workspace, game.Lighting
      			local t = w.Terrain
      			sethiddenproperty(l, "Technology", 2)
      			sethiddenproperty(t, "Decoration", false)
      			t.WaterWaveSize, t.WaterWaveSpeed, t.WaterReflectance, t.WaterTransparency = 0, 0, 0, 0
      			l.GlobalShadows, l.FogEnd, l.Brightness = false, 9e9, 0
      			Misc().Rendering.QualityLevel = "Level01"
      		
      			local function handleDescendant(v)
      			if v:IsA("Accessory") or v:IsA("Shirt") or v:IsA("Pants") or v:IsA("ShirtGraphic") then
      			v:Remove()
      			elseif v:IsA("BasePart") and not v:IsA("MeshPart") then
      			v.Material, v.Reflectance = "Plastic", 0
      			elseif (v:IsA("Decal") or v:IsA("Texture")) and decalsyeeted then
      			v.Transparency = 1
      			elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
      			v.Lifetime = NumberRange.new(0)
      			elseif v:IsA("Explosion") then
      			v.BlastPressure, v.BlastRadius = 1, 1
      			elseif (v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles")) then
      			v.Enabled = false
      			elseif v:IsA("MeshPart") and decalsyeeted then
      			v.Material, v.Reflectance, v.TextureID = "Plastic", 0, 10385902758728957
      			elseif v:IsA("SpecialMesh") and decalsyeeted then
      			v.TextureId = 0
      			end
      			end
      		
      			for _, v in pairs(w:GetDescendants()) do
      			handleDescendant(v)
      			end
      		
      			w.DescendantAdded:Connect(function(v)
      				wait()
      				handleDescendant(v)
      				end)
      		
      			for _, e in ipairs(l:GetChildren()) do
      			if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
      			e.Enabled = false
      			end
      			end
    end
    })


Tabs.Misc:AddButton({
    Title = "Unlock FPS",
    Description = "",
    Callback = function()
      loadstring(game:HttpGet("https://pastebin.com/raw/y5reZYnG", true))()
    end
    })

InterfaceManager:SetLibrary(Fluent)
InterfaceManager:SetFolder("Dusk_Hub")
InterfaceManager:BuildInterfaceSection(Tabs.Settings)

spawn(function()
    pcall(function()
        game:GetService("RunService").Stepped:Connect(function()
            if _G.AutoFarmOrb or _G.Aizen or _G.AutoFarm1 or _G.AutoStoreOrbgg or _G.ShadowM or _G.AutoBossspawnCid or _G.AutoBossspawnAizen then
                if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    local Noclip = Instance.new("BodyVelocity")
                    Noclip.Name = "BodyClip"
                    Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
                    Noclip.MaxForce = Vector3.new(100000, 100000, 100000)
                    Noclip.Velocity = Vector3.new(0, 0, 0)
                end
            else    
                if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
                end
            end
        end)
    end)
end)



if BB then
end

if RY then
local Window = Fluent:CreateWindow({
	Title = "Royal Sea Ulitmate Script",
	SubTitle = "By > Dazzle Hub ",
	TabWidth = 160,
	Size = UDim2.fromOffset(480, 370),
	Acrylic = false, 
	Theme = "Crimson",
	MinimizeKey = Enum.KeyCode.RightControl
})


local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "gamepad-2" }),
    Stats = Window:AddTab({ Title = "Stats", Icon = "align-end-horizontal" }),
    Boss = Window:AddTab({ Title = "Boss", Icon = "swords" }),
    Event = Window:AddTab({ Title = "Event", Icon = "flame" }),
    Raid = Window:AddTab({ Title = "Raid", Icon = "fingerprint" }),
    SHOP = Window:AddTab({ Title = "SHOP", Icon = "shopping-cart" }),
    Island = Window:AddTab({ Title = "Island", Icon = "anchor" }),
    Misc = Window:AddTab({ Title = "Misc", Icon = "align-left" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}


local Weaponlist = {}

local SelectWeapon = Tabs.Main:AddDropdown("SelectWeapon", {
    Title = "Select Weapon",
    Values = Weaponlist,
    Multi = false,
    Default = false,
    Callback = function(selectedWeapon)
        _G.Weaponnn = selectedWeapon
        print("Selected " .. _G.Weaponnn)
    end
})

local function RefreshWeaponList()
    Weaponlist = {}
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
    if v:IsA("Tool") then
       table.insert(Weaponlist ,v.Name)
    end
end
for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
    if v:IsA("Tool") then
       table.insert(Weaponlist, v.Name)
    end
end
    SelectWeapon:SetValues(Weaponlist)
end

Tabs.Main:AddButton({
    Title = "Refresh Weapon",
    Description = "",
    Callback = RefreshWeaponList
})

RefreshWeaponList()


Tabs.Main:AddToggle("Auto Equipped", {
      Title = "Auto Equipped", 
      Default = false, 
      Callback = function(AutoEquipped) 
      _G.AutoEquipped = AutoEquipped
  end})

spawn(function()
    while true do
        if _G.AutoEquipped then
            pcall(function()
                local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(_G.Weaponnn)
                if tool then
                    game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
                end
            end)
        end
        wait(0.2)
    end
end)
game.Players.LocalPlayer.CharacterAdded:Connect(function()
    wait(4)
    spawn(function()
        while true do
            if _G.AutoEquipped then
                pcall(function()
                    local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(_G.Weaponnn)
                    if tool then
                        game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
                    end
                end)
            end
            wait(0.2)
        end
    end)
end)


Tabs.Main:AddToggle("Auto Farm Level", {
      Title = "Auto Farm Level", 
      Default = false, 
      Callback = function(AutoFarmlv) 
      _G.AutoFarmlv = AutoFarmlv
    end})

    local Monhahaaaa = {}



Tabs.Main:AddToggle("Auto Skill X", {
      Title = "Auto Skill X", 
      Default = false, 
      Callback = function(X) 
      _G.X = X
  end})
  

spawn(function()
    while true do 
        wait()
        pcall(function()
            if _G.X then
                local Key = "X"
                local toolm = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool")
                local args = {
                    [1] = game:GetService("Players").LocalPlayer
                }
                game:GetService("Players").LocalPlayer.Character[tostring(toolm)][Key].RemoteEvent:FireServer(unpack(args))
            end
        end)
    end
end)

Tabs.Main:AddToggle("Auto Skill Z", {
      Title = "Auto Skill Z", 
      Default = false, 
      Callback = function(Z) 
      _G.Z = Z
  end})
  

spawn(function()
    while true do 
        wait()
        pcall(function()
            if _G.Z then
                local Key = "Z"
                local toolm = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool")
                local args = {
                    [1] = game:GetService("Players").LocalPlayer
                }
                game:GetService("Players").LocalPlayer.Character[tostring(toolm)][Key].RemoteEvent:FireServer(unpack(args))
            end
        end)
    end
end)

Tabs.Main:AddToggle("Auto Skill V", {
      Title = "Auto Skill V", 
      Default = false, 
      Callback = function(V) 
      _G.V = V
  end})
  

spawn(function()
    while true do 
        wait()
        pcall(function()
            if _G.V then
                local Key = "V"
                local toolm = game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool")
                local args = {
                    [1] = game:GetService("Players").LocalPlayer
                }
                game:GetService("Players").LocalPlayer.Character[tostring(toolm)][Key].RemoteEvent:FireServer(unpack(args))
            end
        end)
    end
end)


Tabs.Stats:AddToggle("Strength", {
        Title = "Strength", 
        Default = false, 
        Callback = function(Strength) 
        _G.Strength = Strength
    end})
  


spawn(function()
    while wait() do
      if _G.Strength then
local args = {
    [1] = "Strength"
}

game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer(unpack(args))
end 
end 
end)

Tabs.Stats:AddToggle("Defense", {
        Title = "Defense", 
        Default = false, 
        Callback = function(Defense) 
        _G.Defense = Defense
    end})
  


spawn(function()
    while wait() do
      if _G.Defense then
local args = {
    [1] = "Defense"
}

game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer(unpack(args))
end 
end 
end)

Tabs.Stats:AddToggle("Weapon", {
        Title = "Weapon", 
        Default = false, 
        Callback = function(Value) 
        _G.Weapon = Weapon
    end})

spawn(function()
    while wait() do
      if _G.Weapon then
local args = {
    [1] = "Weapon"
}

game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer(unpack(args))
end 
end 
end)

Tabs.Stats:AddToggle("Royal", {
      Title = "Royal", 
      Default = false, 
      Callback = function(Royal) 
      _G.Royal = Royal
  end})
  


spawn(function()
    while wait() do
      if _G.Royal then
local args = {
    [1] = "Royal"
}

game:GetService("ReplicatedStorage"):WaitForChild("StatSystem"):WaitForChild("Points"):FireServer(unpack(args))
end 
end 
end)


function MAQ()
    local Lv = tonumber(string.match(game.Players.LocalPlayer.PlayerGui.Menu.ValueGui.LevelDisplay.Text, "%d+"))
    if Lv then
        if Lv >= 1 and Lv <= 29 then
            Mon = "Bandit"
            QuestB = "Quest Lv.1"
        elseif Lv >= 30 and Lv <= 49 then
            Mon = "StrongBandit"
            QuestB = "BossQuest Lv.30"
        elseif Lv >= 50 and Lv <= 99 then
            Mon = "DesertBandit"
            QuestB = "Quest Lv.50"
        elseif Lv >= 100 and Lv <= 149 then
            Mon = "SandBoss"
            QuestB = "BossQuest Lv.100"
        elseif Lv >= 150 and Lv <= 249 then
            Mon = "Clown"
            QuestB = "Quest Lv.150"
        elseif Lv >= 250 and Lv <= 299 then
            Mon = "Buggy"
            QuestB = "BossQuest Lv.250"
        elseif Lv >= 300 and Lv <= 399 then
            Mon = "Monkey"
            QuestB = "Quest Lv.300"
        elseif Lv >= 400 and Lv <= 499 then
            Mon = "GorillaKing"
            QuestB = "BossQuest Lv.400"
        elseif Lv >= 500 and Lv <= 649 then
            Mon = "SkyNewbie"
            QuestB = "Quest Lv.500"
        elseif Lv >= 650 and Lv <= 749 then
            Mon = "SkyElite"
            QuestB = "BossQuest Lv.650"
        elseif Lv >= 750 and Lv <= 899 then
            Mon = "PinkWeak"
            QuestB = "Quest Lv.750"
        elseif Lv >= 900 and Lv <= 1149 then
            Mon = "PinkStrong"
            QuestB = "BossQuest Lv.900"
        elseif Lv >= 1150 and Lv <= 1499 then
            Mon = "IceMan"
            QuestB = "BossQuest Lv.1150"
        elseif Lv == 1500 or Lv <= 1999 then 
          Mon = "DonutMan"
          QuestB = "Quest Lv.1500"
        elseif Lv == 2000 or Lv <= 999999 then 
          Mon = "SuperDonutMan"
          QuestB = "BossQuest Lv.2000"
        end
    end
end

--- เธเธฑเธเน€เน€เธ”เธ
_G.CheckQuestMAM = true

function CheckQuest()
    while _G.CheckQuestMAM do
        MAQ()
        wait(0.5)
        local questBar = game:GetService("Players").LocalPlayer.PlayerGui.QuestBar
        if questBar and questBar.Frame.Visible == true then
            local NameMonnnn = questBar.NameMon.Value
            if not string.find(NameMonnnn, Mon) then
                local args = {
                    [1] = game:GetService("Players").LocalPlayer
                }
                game:GetService("Players").LocalPlayer.PlayerGui.QuestBar.Frame.Close.LocalScript.RemoteEvent:FireServer(unpack(args))
            end
        end
    end
end

function A()
    game:GetService("Players").LocalPlayer.Character:FindFirstChildOfClass("Tool"):Activate()
end


spawn(function()
    while wait() do
        pcall(function()
            if _G.AutoFarmlv then
                MAQ()
                local player = game.Players.LocalPlayer
                local questBar = player:WaitForChild("PlayerGui"):FindFirstChild("QuestBar")
                if questBar and questBar.Frame.Visible == true then
                    for _, v in pairs(game.Workspace.Boss:GetDescendants()) do
                        if v.Name == Mon and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health >= 1 then
                            repeat
                                wait()
                                A()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 0, 4)
                            until not _G.AutoFarmlv or v.Humanoid.Health <= 0
                        end
                    end
                    for _, v in pairs(game.Workspace.Mon:GetDescendants()) do
                        if v.Name == Mon and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health >= 1 then
                            repeat
                                wait()
                                A()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 0, 4)
                            until not _G.AutoFarmlv or v.Humanoid.Health <= 0
                        end
                    end
                else
                    local questNPC = game.Workspace:FindFirstChild("NPCS")
                    if questNPC then
                        for _, y in pairs(questNPC:GetDescendants()) do
                            if y.Name == QuestB and y:FindFirstChild("HumanoidRootPart") then
                                player.Character.HumanoidRootPart.CFrame = y.HumanoidRootPart.CFrame * CFrame.new(0, 5, 0)
                                wait(0.1)
                            end
                        end
                    else
                        print("quest not found")
                    end
                end
            end
        end)
    end
end)


spawn(function()
    while true do
        if _G.AutoFarmlv then
            pcall(function()
                for _, v in pairs(game:GetService("Workspace"):GetDescendants()) do
                    if v.Name == "ProximityPrompt" then
                        fireproximityprompt(v, 30)
                    end
                end
            end)
        end
        wait(0.5) 
    end
end)


local Players = game:GetService("Players")
local Plr = Players.LocalPlayer
local Character = Plr.Character or Plr.CharacterAdded:Wait()

Plr.CharacterAdded:Connect(function(NewCharacter)
    Character = NewCharacter
end)

local function AddInstantKill(Mob)
    if Mob and Mob:IsA("Model") and Mob:FindFirstChildOfClass("Humanoid") then
        if Mob:GetAttribute("InstantKill") == nil then
            Mob:SetAttribute("InstantKill", true)

            local function CheckKillConditions()
                while true do
                    if Mob:FindFirstChild("HittedPlayers"):FindFirstChild(Plr.Name) and
                        (Mob.HumanoidRootPart.Position - Character.HumanoidRootPart.Position).Magnitude <= 15 then
                        
                        if isnetworkowner(Mob.HumanoidRootPart) or Mob:FindFirstChildOfClass("Humanoid").Health <= 0 then
                            Mob:FindFirstChildOfClass("Humanoid").Health = 0
                            break
                        end
                    end
                    wait() 
                end
                
                Mob:SetAttribute("InstantKill", nil) 
                if Mob:FindFirstChildOfClass("Humanoid") and Mob:FindFirstChildOfClass("Humanoid").Health > 0 then
                    AddInstantKill(Mob) 
                end
            end

            coroutine.wrap(CheckKillConditions)() 
        end
    end
end

local function HandleNewModel(Thing)
    if Thing:IsA("Model") and Thing:FindFirstChildOfClass("Humanoid") then
        AddInstantKill(Thing)
    end
end

workspace.Mon.DescendantAdded:Connect(HandleNewModel)

workspace.Boss.ChildAdded:Connect(function(Boss)
    if Boss:IsA("Model") and Boss:FindFirstChildOfClass("Humanoid") then
        AddInstantKill(Boss)
    end
end)


for _, v in pairs(workspace.Mon:GetDescendants()) do
    if v:IsA("Model") and v:FindFirstChildOfClass("Humanoid") then
        AddInstantKill(v)
    end
end

for _, v in pairs(workspace.Boss:GetChildren()) do
    if v:IsA("Model") and v:FindFirstChildOfClass("Humanoid") then
        AddInstantKill(v)
    end
end



--Event


  

Tabs.Event:AddToggle("Auto Farm Slime", {
      Title = "Auto Farm Slime", 
      Default = false, 
      Callback = function(AutoFarmSlime) 
      _G.AutoFarmSlime = AutoFarmSlime
  end})
  


spawn(function()
  while task.wait() do
    if _G.AutoFarmSlime then
          pcall(function()
     for _, v in pairs(game.Workspace.Mon.Slime:GetChildren()) do
      if v.Name == "Slime" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health >= 0 then
        v.Humanoid.WalkSpeed = 0
        v.Humanoid.JumpPower = 0
      repeat task.wait()
        A()
        TP(v.HumanoidRootPart.CFrame * CFrame.new(0,7,0) * CFrame.Angles(math.rad(-90),0,0))
      until not _G.AutoFarmSlime or v.Humanoid.Health <= 0
      A()
      end
  end
 end)
end
end
end)

Tabs.Event:AddToggle("Auto Spawn Rimuru", {
      Title = "Auto Spawn Rimuru", 
      Default = false, 
      Callback = function(AutoBossspawnRimuru) 
      _G.AutoBossspawnRimuru = AutoBossspawnRimuru
  end})

	
	
	CF = CFrame.new(4467.79736328125, 29.154788970947266, 1355.6102294921875)

	spawn(function()
		while wait() do
		if _G.AutoBossspawnRimuru then
		pcall(function()
			for _,v in pairs(game:GetService("Workspace").Boss:GetChildren()) do
			if v.Name == "Rimuru" and v.Humanoid.Health > 0 then
			_G.MT = false
			repeat task.wait()
			  A()
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,6,0) * CFrame.Angles(math.rad(-90),0,0)
			until _G.AutoBossspawnRimuru == false
			A()
			else
				_G.MT = true
			TP(CF)
			end
			end
			end)
		end
		end
		end)

	
	spawn(function()
		while wait() do
		if _G.AutoBossspawnRimuru then
		pcall(function()
			if _G.MT then
			for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do
			if v.ClassName == "ProximityPrompt" then
			fireproximityprompt(v,30)
			end
			end
			end
			end)
		end
		end
		end)

	


Tabs.Event:AddToggle("Auto Farm Rengoku", {
      Title = "Auto Farm Rengoku", 
      Default = false, 
      Callback = function(Rengoku) 
      _G.Rengoku = Rengoku
  end})


spawn(function()
    pcall(function()
        while wait() do
            if _G.Ev then
                if game:GetService("Workspace").NPCS.RengokuBossQuest.Kills.Value < 200 then
                    for _, v in pairs(game.Workspace.Mon:GetDescendants()) do
                        if v.Name == "DonutMan" and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                    repeat task.wait()
                                    A()
                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 0, 6))
                            until not _G.Ev or v.Humanoid.Health <= 0
                        end
                    end
                end
            end
        end
    end)
end)





spawn(function()
  pcall(function()
    while wait()  do
      if _G.Rengoku then
        local foundRengoku = false
        for _, v in pairs(game:GetService("Workspace").Boss:GetChildren()) do
            if v.Name == "Rengoku" and v.Humanoid.Health > 0 then
                foundRengoku = true
                v.HumanoidRootPart.Size = Vector3.new(10, 10, 10)
                v.HumanoidRootPart.Transparency = 0.9
                v.Humanoid.WalkSpeed = 0
                v.Humanoid.JumpPower = 0
                repeat task.wait()
                      A()
                    TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 0, 6))
                until not _G.Rengoku or v.Humanoid.Health <= 0
            end
        end
        if not foundRengoku then
            _G.Ev = true
        end
        wait()
        end
    end
    end)
end)

spawn(function()
    pcall(function()
        while wait() do
            if _G.Rengoku then
                if game:GetService("Workspace").NPCS.RengokuBossQuest.Kills.Value >= 200 then
                    _G.Ev = false
                    TP(CFrame.new(4619.33398, 22.8328609, 957.305847))
                    AA()
                end
            end
        end
    end)
end)

spawn(function()
    while wait() do
        if _G.Rengoku then
            pcall(function()
                for i, v in pairs(game:GetService("Workspace").NPCS.RengokuBossQuest:GetDescendants()) do
                    if v.ClassName == "ProximityPrompt" then
                        fireproximityprompt(v, 30)
                    end
                end
            end)
        end
    end
end)








Tabs.Event:AddToggle("Auto Farm Shadow", {
      Title = "Auto Farm Shadow", 
      Description = "All 7 of them",
      Default = false, 
      Callback = function(Shadow) 
      _G.Shadow = Shadow
  end})





spawn(function()
    pcall(function()
        game:GetService("RunService").Stepped:Connect(function()
            if _G.Ev or _G.Rengoku or _G.Shadow then
                if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    local Noclip = Instance.new("BodyVelocity")
                    Noclip.Name = "BodyClip"
                    Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
                    Noclip.MaxForce = Vector3.new(100000, 100000, 100000)
                    Noclip.Velocity = Vector3.new(0, 0, 0)
                end
            else    
                if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
                end
            end
        end)
    end)
end)

	

--function



function TP(CFrame)
    pcall(function()
        local humanoidRootPart = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            humanoidRootPart.CFrame = CFrame
        else
            -- เธซเธฒเธเนเธกเนเธเธ HumanoidRootPart (เธเธนเนเน€เธฅเนเธเธ•เธฒเธข) เธเนเธฃเธญเนเธซเนเนเธเนเธ”เน€เธเธกเธ—เธณเธเธฒเธเธญเธตเธเธเธฃเธฑเนเธ
            wait(1)
        end
    end)
end


--Boss

Tabs.Boss:AddToggle("Auto Farm Boss All", {
      Title = "Auto Farm Boss All", 
      Default = false, 
      Callback = function(AutoBoss) 
      _G.AutoBoss = AutoBoss
  end})


spawn(function()
    while wait() do
        if _G.AutoBoss then
            pcall(function()
                    for _, v in pairs(game:GetService("Workspace").Boss:GetChildren()) do
                        if v:IsA("Model") and v.Humanoid.Health > 0 then
                            v.HumanoidRootPart.Size = Vector3.new(10,10,10)
                            v.HumanoidRootPart.Transparency = 0.9
                            v.Humanoid.WalkSpeed = 0
                            v.Humanoid.JumpPower = 0
                            repeat
                                task.wait()
                                A()
                                TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 7, 0) * CFrame.Angles(math.rad(-90), 0, 0))
                            until _G.AutoBossAutoBoss == false or v.Humanoid.Health <= 0
                        end
                    end
            end)
        end
    end
end)

Tabs.Boss:AddToggle("Auto Farm Seabeast", {
      Title = "Auto Farm Seabeast", 
      Default = false, 
      Callback = function(AutoFarmSeabeast) 
      _G.AutoFarmSeabeast = AutoFarmSeabeast
  end})



spawn(function()
  while task.wait() do
    if _G.AutoFarmSeabeast then
          pcall(function()
     for _, v in pairs(game.Workspace.Boss:GetChildren()) do
      if v.Name == "Seabeast" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health >= 0 then
        v.Humanoid.WalkSpeed = 0
        v.Humanoid.JumpPower = 0
      repeat task.wait()
        A()
        TP(v.HumanoidRootPart.CFrame * CFrame.new(0,7,0) * CFrame.Angles(math.rad(-90),0,0))
      until not _G.AutoFarmSeabeast or v.Humanoid.Health <= 0
      A()
      end
  end
 end)
end
end
end)

--Raid

Tabs.Raid:AddToggle("Auto Raid Fast", {
      Title = "Auto Raid Fast", 
      Default = false, 
      Callback = function(KillAura) 
      _G.KillAura = KillAura
  end})


Tabs.Raid:AddToggle("Auto Raid Normal", {
      Title = "Auto Raid Normal", 
      Default = false, 
      Callback = function(Raid) 
      _G.Raid = Raid
  end})


spawn(function()
    pcall(function()
        while task.wait() do
            if _G.Raid then
                for _, v in pairs(game.Workspace.Raid.Mon:GetChildren()) do
                    if v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                        v.Humanoid.WalkSpeed = 0
                        v.Humanoid.JumpPower = 0
                        repeat
                            task.wait()
                            A()
                            TP(v.HumanoidRootPart.CFrame * CFrame.new(0, 7, 0) * CFrame.Angles(math.rad(-90), 0, 0))
                        until not _G.Raid or v.Humanoid.Health <= 0
                        A()
                    end
                end
            end
        end
    end)
end)
spawn(function()
  while wait() do 
    if _G.Raid or _G.KillAura then
if not game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("RaidTimeGui") then
                            -- เธซเธฒเธเนเธกเนเธกเธต เนเธซเนเธขเนเธฒเธขเธเธนเนเน€เธฅเนเธเนเธเธ—เธตเนเธเธดเธเธฑเธ”เธ—เธตเนเธฃเธฐเธเธธ
                            game.Players.LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(4102.5249, 20.3928604, 1239.33179, 0, 0, -1, 1, 0, 0, 0, -1, 0))
end
end
end 
end)

spawn(function()
    pcall(function()
        while wait() do
            if _G.KillAura then
                local mobs = game.workspace.Raid.Mon:GetChildren()
        
                for _, mob in pairs(mobs) do
                    if mob:IsA("Model") and mob:FindFirstChild("Humanoid") then
                        local humanoid = mob:FindFirstChildOfClass("Humanoid")
                        humanoid.Health = -math.huge
                        sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                    end
                end
            end
            wait(0.1)
        end
    end)
end)





--Shop


    Tabs.SHOP:AddDropdown("Select SHOP", {
    Title = "Select SHOP",
    Values = {"DualKatanaSeller","KatanaSeller","RandomRace","RandomRoyal","SukunaSeller","TripleKatanaSeller", "RimuruSeller","ShadowSwordSeller" ,"SBFistSeller","PoleSeller","RengokuKatanaSeller"},
    Multi = false,
    Default = false,
    Callback = function(Selectshop)
        _G.Selectshop = Selectshop
    end
})

Tabs.SHOP:AddButton({
    Title = "Auto Teleport SHOP",
    Description = "",
    Callback = function()
      for _, v in pairs(game.Workspace.NPCS:GetChildren()) do
          if v.Name == _G.Selectshop then
          TP(v.HumanoidRootPart.CFrame * CFrame.new(2, 0, 0))
          end 
          end
    end
    })


---Island

Tabs.Island:AddDropdown("Select Island", {
    Title = "Select Island",
    Values = {"Desert","Monkey","Orange","Sky","Starter"},
    Multi = false,
    Default = false,
    Callback = function(Island)
        _G.Island = Island
    end
})



Tabs.Island:AddButton({
    Title = "Teleport Island",
    Description = "",
    Callback = function()
      for _, v in pairs(game.Workspace.Map.AreaGui:GetChildren()) do
          if v.Name == _G.Island then
          TP(v.CFrame * CFrame.new(2, 0, 0))
      end
      end
    end
    })





--Misc

local Monhahaaaa = {} 

for _, v in pairs(workspace.Mon:GetDescendants()) do
    if v:IsA("Model") and v:FindFirstChildOfClass("Humanoid") then
        table.insert(Monhahaaaa, v.Name)
    end
end

for _, v in pairs(workspace.Boss:GetChildren()) do
    if v:IsA("Model") and v:FindFirstChildOfClass("Humanoid") then
        table.insert(Monhahaaaa, v.Name)
    end
end


local SelectMonu = Tabs.Misc:AddDropdown("SelectMon", {
    Title = "Select Mon",
    Values = Monhahaaaa,
    Multi = false,
    Default = false,
    Callback = function(selected)
        mONN = selected
    end
})

Tabs.Misc:AddToggle("InstantKill", {
    Title = "InstantKill", 
    Default = false, 
    Callback = function(CV) 
        _G.AutoFarmDummy = CV
    end
})

local Kill = Tabs.Misc:AddParagraph({
    Title = "InstantKill Status",
    Content = "Status: โ"
})

spawn(function()
    while wait() do
        pcall(function()
            if _G.AutoFarmDummy == true then
                Kill:SetDesc("Status: โ…")
            else
                Kill:SetDesc("Status: โ")
            end
        end)
    end
end)

spawn(function()
    while wait() do
        if _G.AutoFarmDummy then
            pcall(function()
                local Players = game:GetService("Players")
                local LocalPlayer = Players.LocalPlayer

                for _, v in pairs(workspace.Mon:GetDescendants()) do
                    if v:IsA("Model") and v:FindFirstChild("HumanoidRootPart") then
                        if v.Name == mONN then
                            local function HittedMob(Mob)
                                local HitFolder = Mob:FindFirstChild("HittedPlayers")
                                return HitFolder and HitFolder:FindFirstChild(LocalPlayer.Name), Mob:FindFirstChildOfClass("Humanoid") or false
                            end

                            local Hitted, MobHUM = HittedMob(v)

                            if Hitted and MobHUM then
                                if MobHUM.Health > 0 and MobHUM.Parent.Name ~= LocalPlayer.Name then
                                    wait(0.8)
                                    MobHUM.Health = 0 
                                    print("InstantKill Successful")
                                else
                                    print("You didn't hit Mon")
                                end
                            end
                        end
                    end
                end
            end)
        end
    end
end)



Tabs.Misc:AddToggle("Anti AFK", {
      Title = "Anti AFK", 
      Default = true, 
      Callback = function(cbx) 
      _G.AntiAFKEnabled = cbx
      		local vu = game:GetService("VirtualUser")
          game.Players.LocalPlayer.Idled:connect(function()
              if _G.AntiAFKEnabled then
                  vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                  wait(1)
                  vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
                  end
            end)
  end})


Tabs.Misc:AddToggle("White Screen", {
      Title = "White Screen", 
      Default = false, 
      Callback = function(cb) 
      _G.White_Screen = cb
  end})


spawn(function()
    while true do
        wait()
      
        if _G.White_Screen then
            game:GetService("RunService"):Set3dRenderingEnabled(false)
        else
            game:GetService("RunService"):Set3dRenderingEnabled(true)
        end
    end
end)

Tabs.Misc:AddButton({
    Title = "Boost FPS",
    Description = "",
    Callback = function()
      local decalsyeeted = true
      			local g, w, l = game, game.Workspace, game.Lighting
      			local t = w.Terrain
      			sethiddenproperty(l, "Technology", 2)
      			sethiddenproperty(t, "Decoration", false)
      			t.WaterWaveSize, t.WaterWaveSpeed, t.WaterReflectance, t.WaterTransparency = 0, 0, 0, 0
      			l.GlobalShadows, l.FogEnd, l.Brightness = false, 9e9, 0
      			Misc().Rendering.QualityLevel = "Level01"
      		
      			local function handleDescendant(v)
      			if v:IsA("Accessory") or v:IsA("Shirt") or v:IsA("Pants") or v:IsA("ShirtGraphic") then
      			v:Remove()
      			elseif v:IsA("BasePart") and not v:IsA("MeshPart") then
      			v.Material, v.Reflectance = "Plastic", 0
      			elseif (v:IsA("Decal") or v:IsA("Texture")) and decalsyeeted then
      			v.Transparency = 1
      			elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
      			v.Lifetime = NumberRange.new(0)
      			elseif v:IsA("Explosion") then
      			v.BlastPressure, v.BlastRadius = 1, 1
      			elseif (v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles")) then
      			v.Enabled = false
      			elseif v:IsA("MeshPart") and decalsyeeted then
      			v.Material, v.Reflectance, v.TextureID = "Plastic", 0, 10385902758728957
      			elseif v:IsA("SpecialMesh") and decalsyeeted then
      			v.TextureId = 0
      			end
      			end
      		
      			for _, v in pairs(w:GetDescendants()) do
      			handleDescendant(v)
      			end
      		
      			w.DescendantAdded:Connect(function(v)
      				wait()
      				handleDescendant(v)
      				end)
      		
      			for _, e in ipairs(l:GetChildren()) do
      			if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
      			e.Enabled = false
      			end
      			end
    end
    })


Tabs.Misc:AddButton({
    Title = "Unlock FPS",
    Description = "",
    Callback = function()
      loadstring(game:HttpGet("https://pastebin.com/raw/y5reZYnG", true))()
    end
    })

InterfaceManager:SetLibrary(Fluent)
InterfaceManager:SetFolder("Dusk_Hub")
InterfaceManager:BuildInterfaceSection(Tabs.Settings)
end
end
if MM then
local Window = Fluent:CreateWindow({
	Title = "Meme Sea Dazzle Hub",
	SubTitle = "",
	TabWidth = 160,
	Size = UDim2.fromOffset(480, 370),
	Acrylic = false, 
	Theme = "Crimson",
	MinimizeKey = Enum.KeyCode.RightControl
})

local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "gamepad-2" }),
    Items = Window:AddTab({ Title = "Items", Icon = "backpack" }),
    Stats = Window:AddTab({ Title = "Stats", Icon = "align-end-horizontal" }),
    Raid = Window:AddTab({ Title = "Raid", Icon = "globe" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}


UICorner.Parent = ImageButton1


local Options = Fluent.Options

do

    Tabs.Main:AddParagraph({
        Title = "Auto Farm",
        Content = "- Auto Update"
    })

    Tabs.Main:AddDropdown("Select Method", {
        Title = "Select Method",
        Values = {"None","Behind","Below","Upper"},
        Multi = false,
        Default = 1,
        Callback = function(v)
          _G.Method = v
        end
    })
    
    
    
    spawn(function()
        while wait() do 
            pcall(function()
                if _G.Method == "Behind" then
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)
                elseif _G.Method == "Below" then
                    MethodFarm = CFrame.new(0,-_G.DistanceMob,0) * CFrame.Angles(math.rad(90),0,0)
                elseif _G.Method == "Upper" then
                    MethodFarm = CFrame.new(0,_G.DistanceMob,0)  * CFrame.Angles(math.rad(-90),0,0)
                elseif _G.Method == "None" then
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)                
                else
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)
                end
            end)
        end
    end)

    function Attack()
        local VirtualUser = game:GetService('VirtualUser')
        VirtualUser:CaptureController()
        VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
    end
    

Tabs.Main:AddInput("Input", {
        Title = "Distance Mob",
        Default = "0",
        Placeholder = "Distance",
        Numeric = true, -- Only allows numbers
        Finished = false, -- Only calls callback when you press enter
        Callback = function(gay)
         _G.DistanceMob = gay
        end
    })
    local Weaponlist = {}

    local SelectWeapon = Tabs.Main:AddDropdown("SelectWeapon", {
        Title = "Select Weapon",
        Values = Weaponlist,
        Multi = false,
        Default = false,
        Callback = function(selectedWeapon)
            _G.Weaponnn = selectedWeapon
            print("Selected " .. _G.Weaponnn)
        end
    })
    
    local function RefreshWeaponList()
        Weaponlist = {}
        for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
        if v:IsA("Tool") then
           table.insert(Weaponlist ,v.Name)
        end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
        if v:IsA("Tool") then
           table.insert(Weaponlist, v.Name)
        end
    end
        SelectWeapon:SetValues(Weaponlist)
    end
    
    Tabs.Main:AddButton({
        Title = "Refresh Weapon",
        Description = "",
        Callback = RefreshWeaponList
    })
    
    RefreshWeaponList()

    function EquipWeapon(ToolSe)
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			Tool = game.Players.LocalPlayer.Backpack:WaitForChild(ToolSe)
			wait()
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
			wait(0.10)
	end
end




function TP(CFrame)
    pcall(function()
        local humanoidRootPart = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            humanoidRootPart.CFrame = CFrame
        else
            wait(2)
        end
    end)
end



local data_quest = require(game:GetService("ReplicatedStorage").ModuleScript.Quest_Settings)
local excluded_waves = {
    ["Wave 1"] = true,
    ["Wave 2"] = true,
    ["Wave 3"] = true,
    ["Wave 4"] = true,
    ["Wave 5"] = true,
    ["Wave 6"] = true,
    ["Wave 7"] = true,
    ["Wave 8"] = true,
    ["Wave 9"] = true,
    ["Wave 10"] = true,
    ["Meme Beast Quest"] = true
}

local check_level = function()
    local my_level = game:GetService("Players").LocalPlayer.PlayerData.Level.Value
    local data_level = {}
    for index, value in pairs(data_quest) do
        if tonumber(value.LevelNeed) < tonumber(my_level) then
            table.insert(data_level, value.LevelNeed)
        else
            table.insert(data_level, 1)
        end
    end
    return math.max(unpack(data_level))
end

local check_instance = function()
    local my_level = game:GetService("Players").LocalPlayer.PlayerData.Level.Value
    for index, value in pairs(data_quest) do
        if excluded_waves[index] then
        elseif value.LevelNeed == check_level() and not value.Special_Quest then
            local result = {mob = value.Target, quest = index}
            if my_level >= 1100 and my_level <= 1150 then
                result.mob = "Scary Skull"
                result.quest = "Floppa Quest 22"
            end
            if result.quest == "Floppa Quest 29" then
                result.mob = "Moai"
                result.quest = "Floppa Quest 28"
            end
            if result.quest == "Floppa Quest 32" then
                result.mob = "Sus Duck"
                result.quest = "Floppa Quest 31"
            end
            return result
        end
    end
end



Tabs.Main:AddToggle("Auto Farm Level", {
      Title = "Auto Farm Level",
      Description = "- Auto Farm Level 1 - Max \n( Auto Update )",
      Default = false, 
      Callback = function(Value) 
        _G.Farm = Value
  end})
  
  spawn(function()
        while task.wait() do
          pcall(function()
            if _G.Farm then
                local result = check_instance()
                if result then
                    local Monster = result.mob
                    local QuestB = result.quest
                    local CheckQ = game.Players.LocalPlayer.PlayerGui.QuestGui.Holder.QuestSlot1.QuestGiver.Text
                    if CheckQ ~= QuestB then
                        game.ReplicatedStorage.OtherEvent.QuestEvents.Quest:FireServer("Abandon_Quest", {QuestSlot = "QuestSlot1"})
                      end
                    if game.Players.LocalPlayer.PlayerGui.QuestGui.Holder.QuestSlot1.Visible == true then
                      wait(1)
                        for _, v in ipairs(game.Workspace.Monster:GetDescendants()) do
                            if v.Name == Monster and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                v.Humanoid.WalkSpeed = 0
                                v.Humanoid.JumpPower = 0
                                repeat
                                    task.wait()
                                    TP(v.HumanoidRootPart.CFrame * MethodFarm)
                                    Attack()
                                until not _G.Farm or v.Humanoid.Health <= 0
                            end
                        end
                    else
                        wait(1)
                        for _, y in pairs(game.Workspace.Location.QuestLocaion:GetDescendants()) do
                            if y.Name == QuestB then
                                TP(y.CFrame * CFrame.new(0, 8, 0))
                                
                            end
                        end
                    end
                end
            end
        end)
    end
end)



spawn(function()
  while wait(0.4) do
    pcall(function()
      if _G.Farm then
      for _, v in pairs(game.Workspace.NPCs.Quests_Npc:GetDescendants()) do
        if v.ClassName == "ProximityPrompt" then
         fireproximityprompt(v, 30)
          end
        end
      end
    end)
  end
end)


spawn(function()
    while task.wait() do
        pcall(function()
            if _G.Farm then
                local result = check_instance()
                if result then
                    local Monster = result.mob
                    local M = game.Workspace.Monster
                    local CFrameMon = M[Monster].HumanoidRootPart.Position
                    for i, v in pairs(game:GetService("Workspace").Monster:GetChildren()) do
                        if v.Name == Monster and (v.HumanoidRootPart.CFrame.Position - CFrameMon).magnitude <= 250 then
                            v.HumanoidRootPart.Position = CFrameMon
                            v.Humanoid:ChangeState(14)
                            v.HumanoidRootPart.CanCollide = false
                            v.Head.CanCollide = false
                            v.Humanoid.WalkSpeed = 0
                            v.Humanoid.JumpPower = 0
                            if v.Humanoid:FindFirstChild("Animator") then
                                v.Humanoid.Animator:Destroy()
                            end
                            sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                        end
                    end
                end
            end
        end)
    end
end)


spawn(function()
    while true do
        xpcall(function()
            if _G.Farm then
                task.wait(3)
                EquipWeapon(_G.Weaponnn)
                wait()
            else
                task.wait(1)
            end
        end, function(err)
            print("Error: "..err)
        end)
    end
end)





Tabs.Main:AddToggle("Grab Fruit", {
    Title = "Grab Item", 
    Description = "Fruit / Item",
    Default = false, 
    Callback = function(Fruit) 
        _G.Grab = Fruit
    end
})

spawn(function()
    while wait() do
        if _G.Grab then
            pcall(function()
                for i,v in pairs(workspace.Dropped_Items:GetChildren()) do
                    if v:IsA("Tool") then
                        v.Handle.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                    end
                end    
            end)
        end
    end
end)
  

local function UpgradeStats(target)
    local args = {
        [1] = {
            ["Target"] = target .. "Level",
            ["Action"] = "UpgradeStats",
            ["Amount"] = _G.Ve
        }
    }
    game:GetService("ReplicatedStorage"):WaitForChild("OtherEvent"):WaitForChild("MainEvents"):WaitForChild("StatsFunction"):InvokeServer(unpack(args))
end

Tabs.Stats:AddSlider("Slider", {
    Title = "Point",
    Description = "Use Point",
    Default = 5,
    Min = 0,
    Max = 100,
    Rounding = 0,
    Callback = function(value)
        _G.Ve = value
    end
})

Tabs.Stats:AddButton({
    Title = "Refresh Stats",
    Description = "",
    Callback = function()
        UpgradeStats("Reset")
    end
})

Tabs.Stats:AddToggle("Auto Stats Melee", {
    Title = "Auto Stats Melee",
    Default = false,
    Callback = function(enabled)
        _G.Melee = enabled
    end
})

spawn(function()
    while true do
        if _G.Melee then
            UpgradeStats("Melee")
        end
        task.wait()
    end
end)

Tabs.Stats:AddToggle("Auto Stats Defense", {
    Title = "Auto Stats Defense",
    Default = false,
    Callback = function(enabled)
        _G.Defense = enabled
    end
})

spawn(function()
    while true do
        if _G.Defense then
            UpgradeStats("Defense")
        end
        task.wait()
    end
end)

Tabs.Stats:AddToggle("Auto Stats Sword", {
    Title = "Auto Stats Sword",
    Default = false,
    Callback = function(enabled)
        _G.Sword = enabled
    end
})

spawn(function()
    while true do
        if _G.Sword then
            UpgradeStats("Sword")
        end
        task.wait()
    end
end)

Tabs.Stats:AddToggle("Auto Stats DevilFruit", {
    Title = "Auto Stats MemePower",
    Default = false,
    Callback = function(enabled)
        _G.DevilFruit = enabled
    end
})

spawn(function()
    while true do
        if _G.DevilFruit then
            UpgradeStats("MemePower")
        end
        task.wait()
    end
end)


Tabs.Items:AddParagraph({
    Title = "Auto get all",
    Content = "- Get All Swords/Accessories\n( Update 4 )"
})

Tabs.Items:AddToggle("Auto POP CAT", {
    Title = "Auto Pop Cat",
    Description = "- Auto Clicks Pop Cat",
    Default = false, 
    Callback = function(Value) 
        _G.POP = Value
    end
})

-------------------POPCAT---------------------------

local POPCF = CFrame.new(399.709076, -34.4671745, -586.016052, -0.992933154, -1.27644491e-08, 0.118674792, -1.6724e-08, 1, -3.23688418e-08, -0.118674792, -3.41248168e-08, -0.992933154)
local POPSM = CFrame.new(3493.49097, 23.3810272, -1568.53333, 0.999198854, 8.39129655e-09, -0.0400199406, -7.40410666e-09, 1, 2.48156748e-08, 0.0400199406, -2.44994816e-08, 0.999198854)


spawn(function()
    while true do
        if _G.POP then
            pcall(function()
                local player = game:GetService("Players").LocalPlayer
                local weaponCount = player.Items.Weapon.Popcat.Value
                local popCount = player.PlayerData.Pop.Value

                if weaponCount >= 1 then
                    print("No")
                elseif popCount < 10000 then
                    TP(POPCF)
                    game:GetService("RunService").RenderStepped:Connect(function()
                        local clickDetector = workspace.Island.FloppaIsland.Popcat_Clickable.Part:FindFirstChild("ClickDetector")
                        if clickDetector then
                            fireclickdetector(clickDetector)
                        end
                    end)
                elseif popCount >= 10000 then
                    TP(POPSM)
                    wait(1)
                    local args = {
                        [1] = "Weapon_Seller",
                        [2] = "Ohio Popcat"
                    }
                    game:GetService("ReplicatedStorage"):WaitForChild("OtherEvent"):WaitForChild("MainEvents"):WaitForChild("Modules"):FireServer(unpack(args))
                end
            end)
        end
        wait(0.5)
    end
end)

----------------------------------------------

Tabs.Items:AddToggle("Bonk", {
    Title = "Auto Bonk",
    Description = "- Auto Farm Money Bags ( X 5 )",
    Default = false,
    Callback = function(Value)
        _G.AutoBags = Value
    end
})

-----------------Bonk---------------------
local Pm = CFrame.new(1846.09155, 24.9462662, -5339.56982, 0.997545183, -3.70549236e-09, -0.0700255781, -5.18039056e-10, 1, -6.02959673e-08, 0.0700255781, 6.01842274e-08, 0.997545183)

spawn(function()
    while true do
        wait()
        if _G.AutoBags then
            local Players = game:GetService("Players")
            local LocalPlayer = Players.LocalPlayer
            local ItemStorage = LocalPlayer:FindFirstChild("Items") and LocalPlayer.Items:FindFirstChild("ItemStorage")
            
            if ItemStorage then
                local Money1 = ItemStorage:FindFirstChild("Money Bag") and ItemStorage["Money Bag"].Value or 0
                
                if Money1 >= 0 then
                    pcall(function()
                        local Character = LocalPlayer.Character
                        local HumanoidRootPart = Character and Character:FindFirstChild("HumanoidRootPart")
                        
                        if HumanoidRootPart then
                            local foundMonster = false
                            for _, monster in pairs(workspace:FindFirstChild("Monster"):GetChildren()) do
                                if monster.Name == "MrBeast" and monster:FindFirstChild("Humanoid") and monster.Humanoid.Health > 0 then
                                    local MonsterHumanoidRootPart = monster:FindFirstChild("HumanoidRootPart")
                                    if MonsterHumanoidRootPart then
                                        foundMonster = true
                                        repeat
                                            task.wait()
                                            TP(MonsterHumanoidRootPart.CFrame * MethodFarm)
                                            Attack()
                                        until monster.Humanoid.Health <= 0
                                    end
                                end
                            end
                            if not foundMonster then
                                TP(Pm)
                            end
                        end
                    end)
                end
            end
        end
    end
end)

---------------------------------------------------------------


Tabs.Items:AddToggle("Bonk", {
    Title = "Auto Rick Buddy",
    Description = "- Auto Farm Rick Roller",
    Default = false,
    Callback = function(Value)
        _G.Rick = Value
    end
})

-----------------Rick Buddy---------------------
spawn(function()
    while true do
        wait()
        if _G.Rick then
            local Players = game:GetService("Players")
            local LocalPlayer = Players.LocalPlayer
            local ItemStorage = LocalPlayer:FindFirstChild("Items") and LocalPlayer.Items:FindFirstChild("Accessory")
            
            if ItemStorage then
                local BuddyR = ItemStorage:FindFirstChild("Rick Buddy") and ItemStorage["Rick Buddy"].Value or 0
                
                if BuddyR >= 0 then
                    pcall(function()
                        local Character = LocalPlayer.Character
                        local HumanoidRootPart = Character and Character:FindFirstChild("HumanoidRootPart")
                        
                        if HumanoidRootPart then
                            local foundMonster = false
                            for _, monster in pairs(workspace:FindFirstChild("Monster"):GetChildren()) do
                                if monster.Name == "Rick Roller" and monster:FindFirstChild("Humanoid") and monster.Humanoid.Health > 0 then
                                    local MonsterHumanoidRootPart = monster:FindFirstChild("HumanoidRootPart")
                                    if MonsterHumanoidRootPart then
                                        foundMonster = true
                                        repeat
                                            task.wait()
                                            TP(MonsterHumanoidRootPart.CFrame * MethodFarm)
                                            Attack()
                                        until monster.Humanoid.Health <= 0
                                    end
                                end
                            end
                            if not foundMonster then
                                TP(PmMM)
                            end
                        end
                    end)
                end
            end
        end
    end
end)
--------------------------------------------------------------

Tabs.Items:AddToggle("Bonk", {
    Title = "Auto MrBeast",
    Description = "- Auto Farm MrBeast",
    Default = false,
    Callback = function(Value)
        _G.MrBeast = Value
    end
})


------------------MrBeast--------------------
spawn(function()
    while true do
        wait()
        if _G.MrBeast then
            local Players = game:GetService("Players")
            local LocalPlayer = Players.LocalPlayer
            local ItemStorage = LocalPlayer:FindFirstChild("Items") and LocalPlayer.Items:FindFirstChild("Accessory")
            
            if ItemStorage then
                local BuddyRb = ItemStorage:FindFirstChild("MrBeast") and ItemStorage["MrBeast"].Value or 0
                
                if BuddyRb >= 0 then
                    pcall(function()
                        local Character = LocalPlayer.Character
                        local HumanoidRootPart = Character and Character:FindFirstChild("HumanoidRootPart")
                        
                        if HumanoidRootPart then
                            local foundMonster = false
                            for _, monster in pairs(workspace:FindFirstChild("Monster"):GetChildren()) do
                                if monster.Name == "MrBeast" and monster:FindFirstChild("Humanoid") and monster.Humanoid.Health > 0 then
                                    local MonsterHumanoidRootPart = monster:FindFirstChild("HumanoidRootPart")
                                    if MonsterHumanoidRootPart then
                                        foundMonster = true
                                        repeat
                                            task.wait()
                                            TP(MonsterHumanoidRootPart.CFrame * MethodFarm)
                                            Attack()
                                        until monster.Humanoid.Health <= 0
                                    end
                                end
                            end
                            if not foundMonster then
                                TP(Pm)
                            end
                        end
                    end)
                end
            end
        end
    end
end)
---------------------------------------------------

Tabs.Items:AddToggle("Bonk", {
    Title = "Auto Floppa",
    Description = "- Auto Get Floppa",
    Default = false,
    Callback = function(Value)
        _G.Floppa = Value
    end
})

-------------------Floppa--------------------------------------
local FloppaM = CFrame.new(795.041138, -30.817585, -439.981171, 0.622583807, -8.94893315e-09, 0.782553136, -1.15490861e-08, 1, 2.06237853e-08, -0.782553136, -2.1877808e-08, 0.622583807)
local FloppaQ = CFrame.new(756.196777, -30.4632034, -426.953003, -0.89466244, 8.05907661e-08, 0.446742803, 6.73825014e-08, 1, -4.54538309e-08, -0.446742803, -1.05631868e-08, -0.89466244)

spawn(function()
    while true do
        pcall(function()
            wait(1)
            if _G.Floppa then
                if not game:GetService("Players").LocalPlayer.PlayerGui.QuestGui.Holder.QuestSlot1.Visible then
                    TP(FloppaQ)
                    for i, v in pairs(workspace.NPCs.Quests_Npc["Cool Floppa Quest"].Block:GetChildren()) do
                        if v:IsA("ProximityPrompt") then
                            fireproximityprompt(v, 30)
                        end
                    end
                else
                    TP(FloppaM)
                    local connection
                    connection = game:GetService("RunService").RenderStepped:Connect(function()
                        for i, v in pairs(workspace.Island.FloppaIsland["Lava Floppa"].ClickPart:GetChildren()) do
                            if v:IsA("ProximityPrompt") then
                                fireproximityprompt(v, 30)
                            end
                        end
                    end)
                    wait(10)
                    connection:Disconnect()
                end
            end
        end)
    end
end)


--------------------------------------------------------------



Tabs.Raid:AddToggle("Bonk", {
    Title = "Auto Raid",
    Default = false,
    Callback = function(Value)
        _G.Raid = Value
    end
})

spawn(function()
  while task.wait() do
    pcall(function()
      if _G.Raid then
        if game.Players.LocalPlayer.PlayerGui.RaidGui.RaidFrame.Visible == false then
          TP(CFrame.new(2746.76807, -57.325798, -4530.43652, -0.578812599, 1.91404261e-08, -0.815460563, 5.04050912e-10, 1, 2.3114147e-08, 0.815460563, 1.29677264e-08, -0.578812599))
          else
            game:GetService("ReplicatedStorage").OtherEvent.MiscEvents.StartRaid:FireServer("Start")
        for _, v in pairs(workspace.Monster:GetChildren()) do
          if v:IsA("Model") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
            if game:GetService("Players").LocalPlayer:DistanceFromCharacter(v:FindFirstChild("HumanoidRootPart").Position) < 700 then
              v.Humanoid.WalkSpeed = 0
              v.Humanoid.JumpPower = 0
                repeat
                task.wait()
                 TP(v.HumanoidRootPart.CFrame * MethodFarm)
                   Attack()
                 until not _G.Farm or v.Humanoid.Health <= 0
              end
            end
          end
        end
      end
    end)
  end
end)
spawn(function()
    while wait(0.3) do
        if _G.Raid then
            local success, err = pcall(function()
                local monsters = game:GetService("Workspace").Monster:GetChildren()
                local player = game.Players.LocalPlayer
                local simulationRadius = math.huge

                for i, v in ipairs(monsters) do
                    if v:IsA("Model") and v:FindFirstChild("HumanoidRootPart") then
                        local vPosition = v.HumanoidRootPart.Position
                        for j, y in ipairs(monsters) do
                            if y:IsA("Model") and y:FindFirstChild("HumanoidRootPart") and (vPosition - y.HumanoidRootPart.Position).magnitude <= 700 then
                                v.HumanoidRootPart.CFrame = y.HumanoidRootPart.CFrame
                                v.Humanoid:ChangeState(14)
                                v.HumanoidRootPart.CanCollide = false
                                v.Head.CanCollide = false
                                v.Humanoid.WalkSpeed = 0
                                v.Humanoid.JumpPower = 0
                                
                                y.Humanoid:ChangeState(14)
                                y.HumanoidRootPart.CanCollide = false
                                y.Head.CanCollide = false
                                y.Humanoid.WalkSpeed = 0
                                y.Humanoid.JumpPower = 0

                                if v.Humanoid:FindFirstChild("Animator") then
                                    v.Humanoid.Animator:Destroy()
                                end
                                if y.Humanoid:FindFirstChild("Animator") then
                                    y.Humanoid.Animator:Destroy()
                                end
                                
                                sethiddenproperty(player, "SimulationRadius", simulationRadius)
                            end
                        end
                    end
                end
            end)

            if not success then
                warn("พบข้อผิดพลาด: " .. err)
            end
        end
    end
end)


spawn(function()
    pcall(function()
        game:GetService("RunService").Stepped:Connect(function()
            if _G.Farm or _G.Raid or _G.Floppa or _G.MrBeast or _G.Rick or _G.POP or _G.AutoBags then
                if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    local Noclip = Instance.new("BodyVelocity")
                    Noclip.Name = "BodyClip"
                    Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
                    Noclip.MaxForce = Vector3.new(100000, 100000, 100000)
                    Noclip.Velocity = Vector3.new(0, 0, 0)
                end
            else    
                if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
                end
            end
        end)
    end)
end)  


spawn(function()
    while true do
        xpcall(function()
            if _G.Farm or _G.Raid or _G.Floppa or _G.MrBeast or _G.Rick or _G.POP or _G.AutoBags then
                task.wait(3)
                EquipWeapon(_G.Weaponnn)
                wait()
            else
                task.wait(1)
            end
        end, function(err)
            print("Error: "..err)
        end)
    end
end)




InterfaceManager:SetLibrary(Fluent)
InterfaceManager:SetFolder("Dusk_Hub")
InterfaceManager:BuildInterfaceSection(Tabs.Settings)
end


end
