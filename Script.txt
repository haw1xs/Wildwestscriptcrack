local _select = select
local function v716(tbl, idx, ...)
    local va = {
        ...,
    }
    for i = 1, _select("#", ...) do
        tbl[idx + i - 1] = va[i]
    end
end
local u1 = cloneref or (function(p1)
    return p1
end)
plrs = u1(game:GetService("Players"))
lp = plrs.LocalPlayer
ws = u1(game:GetService("Workspace"))
cam = ws.Camera
ms = lp:GetMouse()
repst = u1(game:GetService("ReplicatedStorage"))
stats = u1(game:GetService("Stats"))
mps = u1(game:GetService("MarketplaceService"))
vim = u1(game:GetService("VirtualInputManager"))
scriptcontext = u1(game:GetService("ScriptContext"))
rs = u1(game:GetService("RunService"))
uis = u1(game:GetService("UserInputService"))
cg = u1(game:GetService("CoreGui"))
local u2 = getgenv or (function()
    return _G
end)
local v3 = false
local find = table.find
local t1 = {
    [1] = "Solara",
    [2] = "Xeno",
    [3] = "JJSploit",
    [4] = "Zorara",
}
local t2 = {}
v716(t2, 1, identifyexecutor())
if find(t1, t2[1]) or (not getgc or not hookfunction or not getconnections or not hookmetamethod) then
    v3 = true
end
if v3 then
    lp:Kick("[Unsupported Executor] please use a supported executor")
    return
end
local ok, __ = pcall(function()
end)
if not ok then
    lp:Kick("please rejoin reason: failed to load drawing library")
    return
end
task.spawn(function()
    if u2().conn then
        for k, v in next, u2().conn do
            v:Disconnect()
            u2().conn[k] = nil
        end
    end
    if u2().Toggles and type(u2().Toggles) == "table" then
        for k, __ in next, u2().Toggles do
            local v33 = k
            u2().Toggles[v33]:SetValue(false)
            u2().Toggles[v33] = nil
        end
    end
    if u2().FOV and u2().FOV.Visible then
        u2().FOV.Visible = false
    end
end)
utils = {}
utility = {}
conn = {}
local function v9(p2)
    p2()
end
if game.GameId ~= 807930589 then
    return lp:Kick("Invalid Game:\nPlease Join The Wild West")
end
if not u2().FOV or not u2().snap then
    u2().FOV = Drawing and Drawing.new("Circle") or {}
    local FOV = u2().FOV
    local FOV2 = u2().FOV
    u2().FOV.Filled = false
    FOV2.Radius = 200
    FOV.Visible = false
    u2().FOV.Color = Color3.fromRGB(0, 255, 194)
    u2().snap = Drawing and Drawing.new("Line") or {}
    u2().snap.Visible = false
    u2().snap.ZIndex = 999
    u2().snap.Color = Color3.fromRGB(0, 255, 194)
    u2().snap.Thickness = 1
end
v9(function()
    mainModule = repst:FindFirstChild("Global", true)
    getgc = getgc or (function()
        return {}
    end)
    debug = debug or {}
    hookfunction = hookfunction or (function(...)
        return ...
    end)
    newcclosure = newcclosure or (function(...)
        return ...
    end)
    getscripthash = getscripthash or (function(...)
        return ...
    end)
    messagebox = messagebox or (function(...)
        return ...
    end)
    getconnections = getconnections or (function()
        return {}
    end)
    getsenv = getsenv or (function(...)
        return ...
    end)
    Settings = {}
    flags = {}
    task.spawn(function()
        repeat
            task.wait()
            if mainModule and mainModule.ClassName == "ModuleScript" and lib then
                local ok2, result = pcall(require, mainModule)
                if not ok2 then
                    return lib:Notify("[Script Warning] Executor doesn't support [require]", 10, nil)
                end
                mainModule = result
                loadModule = mainModule.LoadModule
                if loadModule and type(loadModule) == "function" then
                    Modules = {
                        Network = loadModule("Network"),
                        cam = loadModule("Camera"),
                        animhandler = loadModule("AnimationHandler"),
                        leaderboard = loadModule("Leaderboard"),
                        animal = loadModule("Animal"),
                        horse = loadModule("Horse"),
                        gunitem = loadModule("GunItemType"),
                        projHandler = loadModule("ProjectileHandler"),
                        plrCharacter = loadModule("PlayerCharacter"),
                        meeleType = loadModule("MeleeItemType"),
                        bowitem = loadModule("BowItemType"),
                        pickaxeType = loadModule("PickaxeItemType"),
                        repChar = loadModule("RepCharHandler"),
                        swimController = loadModule("SwimController"),
                        sharedRadgolls = loadModule("SharedRagdolls"),
                        plrData = loadModule("PlayerData"),
                        repState = loadModule("ReplicatedState"),
                        hotBar = loadModule("Hotbar"),
                    }
                end
                continue
            end
        until lib
    end)
    task.spawn(function()
        local n1 = 0
        repeat
            task.wait()
            n1 += 1
            if not Network and Modules and Modules.Network then
                Network = Modules.Network
            end
        until mainModule and Modules and Modules.Network or n1 >= 1000
        repeat
            task.wait()
        until lib
        if (not Network or not Modules or not Modules.Network) and lib then
            lib:Notify("[Script Warning] Failed to load network module some features won't work", 50, UDim2.new(0, 700, 0, 40))
        end
    end)
    logsev = u1(game:GetService("LogService"))
    for __, v in next, getconnections(logsev.MessageOut) do
        local v37 = v
        if v37.Function then
            local v38 = debug.getinfo(v37.Function)
            if v38 and not v38.source:find("CoreGui") then
                warn("logsev bypassed: ", v38.source)
            end
        end
    end
    for __, v in next, getconnections(scriptcontext.Error) do
        if not not v.Function then
        end
    end
    lighting = u1(game:GetService("Lighting"))
    for __, v in next, getconnections(lighting.Changed) do
        v:Disable()
    end
    conn.curcam = ws:GetPropertyChangedSignal("CurrentCamera"):Connect(function()
        cam = ws.CurrentCamera
    end)
end)
local t3 = {}
v9(function()
    SendReport = function(p3)
        local v252 = nil
        local u253 = nil
        repeat
            if not v252 and http then
                local request = http.request
                if not request then
                    v252 = true
                end
                if not v252 then
                    u253 = request
                end
            else
                v252 = false
                local _http_request = http_request
                if _http_request then
                    u253 = _http_request
                end
            end
        until not v252
        local u256 = u1(game:GetService("HttpService"))
        local u257 = "**Report Sent From:" .. " " .. lp.Name .. " " .. "User ID: " .. tostring(lp.UserId) .. "**"
        local function u258(p4)
            if type(p4) ~= "string" or p4 == "" then
                return {
                    [1] = {
                        name = "**Script Report: TWW**",
                        value = "**error**",
                        inline = false,
                    },
                }
            end
            return {
                [1] = {
                    name = "**Script Report: TWW**",
                    value = "**" .. p4 .. "**",
                    inline = false,
                },
            }
        end
        spawn(function()
            u253({
                Url = webhookUrl,
                Method = "POST",
                Headers = {
                    ["Content-Type"] = "application/json",
                },
                Body = u256:JSONEncode({
                    content = "",
                    embeds = {
                        [1] = {
                            title = "**Alert Script**",
                            description = u257,
                            type = "rich",
                            color = 16711680,
                            fields = u258(p3),
                        },
                    },
                }),
            })
        end)
    end
    local function u43(p5, p6)
        local UICorner = Instance.new("UICorner")
        UICorner.CornerRadius = p6 or UDim.new(0, 5)
        UICorner.Parent = p5
        return UICorner
    end
    MakeFrameInfo = function()
        local ScreenGui = Instance.new("ScreenGui", lp.PlayerGui)
        ScreenGui.Name = "Win_Meter"
        local Frame = Instance.new("Frame", ScreenGui)
        Frame.Size = UDim2.fromOffset(240, 89)
        Frame.BackgroundColor3 = Color3.fromRGB(1, 1, 1)
        Frame.BackgroundTransparency = 0.5
        Frame.Position = UDim2.new(0.4, 50, 0.8, 0)
        u43(Frame)
        local TextLabel = Instance.new("TextLabel")
        TextLabel.Size = UDim2.fromOffset(145, 20)
        TextLabel.Position = UDim2.fromOffset(50, 5)
        TextLabel.BackgroundTransparency = 1
        TextLabel.Text = "Current Target"
        TextLabel.TextXAlignment = Enum.TextXAlignment.Center
        TextLabel.TextYAlignment = Enum.TextYAlignment.Top
        TextLabel.TextScaled = true
        TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
        TextLabel.TextStrokeTransparency = 1
        local clone = TextLabel:Clone()
        clone.Position = UDim2.fromOffset(55, 21)
        clone.TextColor3 = Color3.new()
        clone.TextTransparency = 0.65
        clone.Visible = false
        clone.Parent = Frame
        local clone2 = TextLabel:Clone()
        clone2.Name = "HPText"
        clone2.TextXAlignment = Enum.TextXAlignment.Right
        clone2.Parent = Frame
        clone2.Position = UDim2.fromOffset(70, 30)
        clone2.TextColor3 = Color3.fromHSV(0.44, 1, 1)
        clone2.Text = "100"
        local clone3 = TextLabel:Clone()
        clone3.Name = "chanceText"
        clone3.TextXAlignment = Enum.TextXAlignment.Left
        clone3.Parent = Frame
        clone3.Position = UDim2.fromOffset(20, 30)
        clone3.TextColor3 = Color3.fromHSV(0.44, 1, 1)
        clone3.Text = "Win"
        conn.connsize = TextLabel:GetPropertyChangedSignal("Size"):Connect(function()
            clone.Size = TextLabel.Size
        end)
        TextLabel.Parent = Frame
        local Frame2 = Instance.new("Frame")
        Frame2.Name = "HealthBKG"
        Frame2.Size = UDim2.fromOffset(200, 9)
        Frame2.Position = UDim2.fromOffset(20, 56)
        Frame2.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
        Frame2.BorderSizePixel = 0
        Frame2.Parent = Frame
        u43(Frame2, UDim.new(1, 0))
        local clone4 = Frame2:Clone()
        clone4.Size = UDim2.fromScale(0.8, 1)
        clone4.Position = UDim2.new()
        clone4.BackgroundColor3 = Color3.fromHSV(0.4, 0.89, 0.75)
        clone4.Parent = Frame2
        conn.connsize2 = clone4:GetPropertyChangedSignal("Size"):Connect(function()
            clone4.Visible = clone4.Size.X.Scale > 0.01
        end)
        local clone5 = clone4:Clone()
        clone5.Size = UDim2.new()
        clone5.Position = UDim2.fromScale(1, 0)
        clone5.AnchorPoint = Vector2.new(1, 0)
        clone5.BackgroundColor3 = Color3.fromRGB(255, 170, 0)
        clone5.Visible = true
        clone5.Parent = Frame2
        conn.connsize3 = clone5:GetPropertyChangedSignal("Size"):Connect(function()
            clone5.Visible = clone5.Size.X.Scale > 0.01
        end)
        local UIStroke = Instance.new("UIStroke")
        UIStroke.Enabled = true
        UIStroke.Color = Color3.fromHSV(0.44, 1, 1)
        UIStroke.Parent = Frame
        return TextLabel, clone2, clone3, clone4, clone5
    end
    t3.ChatUI = function(__)
        local ScreenGui = Instance.new("ScreenGui", cg)
        local ScrollingFrame = Instance.new("ScrollingFrame")
        Instance.new("Frame")
        local Frame = Instance.new("Frame")
        local UIListLayout = Instance.new("UIListLayout")
        local TextLabel = Instance.new("TextLabel")
        ScreenGui.Name = "chat_spy"
        ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
        ScrollingFrame.Name = "MainFrame"
        ScrollingFrame.Parent = ScreenGui
        ScrollingFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        ScrollingFrame.BorderColor3 = Color3.fromRGB(70, 70, 70)
        ScrollingFrame.BorderSizePixel = 1.2
        ScrollingFrame.AnchorPoint = Vector2.new(0.5, 0.5)
        ScrollingFrame.BackgroundTransparency = 0.25
        ScrollingFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
        ScrollingFrame.Size = UDim2.fromOffset(300, 200)
        ScrollingFrame.Draggable = true
        Frame.Name = "FrameText"
        Frame.Size = UDim2.fromOffset(300, 25)
        Frame.Position = UDim2.new(0, ScrollingFrame.AbsolutePosition.X, 0, ScrollingFrame.AbsolutePosition.Y - 25)
        Frame.Parent = ScrollingFrame
        Frame.BorderSizePixel = 1.2
        Frame.BackgroundTransparency = 0.25
        Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        Frame.BorderColor3 = Color3.fromRGB(70, 70, 70)
        Frame.Draggable = true
        TextLabel.Name = "NameLabel"
        TextLabel.Parent = Frame
        TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TextLabel.BackgroundTransparency = 1
        TextLabel.Position = UDim2.new(0, 20, -0.00293789315, 0)
        TextLabel.Size = UDim2.new(0, 243, 0, 27)
        TextLabel.Font = Enum.Font.SourceSans
        TextLabel.Text = "Chat Spy"
        TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
        TextLabel.TextSize = 24
        TextLabel.TextWrapped = true
        UIListLayout.Parent = ScrollingFrame
        UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
        ScrollingFrame.CanvasSize = UDim2.new(0, 0, 0, UIListLayout.AbsoluteContentSize.Y)
        t3.AddItem = function(__, p9, p10)
            local TextLabel2 = Instance.new("TextLabel")
            TextLabel2.Name = "Items Container"
            TextLabel2.Parent = ScrollingFrame
            TextLabel2.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
            TextLabel2.BackgroundTransparency = 1
            TextLabel2.Size = UDim2.new(0, 243, 0, 19)
            TextLabel2.Font = Enum.Font.SourceSans
            TextLabel2.Text = tostring(p9)
            TextLabel2.TextXAlignment = Enum.TextXAlignment.Left
            TextLabel2.AutomaticSize = Enum.AutomaticSize.Y
            TextLabel2.TextColor3 = p10 or Color3.fromRGB(255, 255, 255)
            TextLabel2.TextSize = 20
            ScrollingFrame.CanvasSize = UDim2.new(0, 0, 0, UIListLayout.AbsoluteContentSize.Y)
            return TextLabel2
        end
        return ScrollingFrame
    end
    MakeFrameTop = function()
        local ScreenGui = Instance.new("ScreenGui", cg)
        Instance.new("Frame")
        local Frame = Instance.new("Frame")
        Instance.new("UIListLayout")
        local TextLabel = Instance.new("TextLabel")
        ScreenGui.Name = "client_info"
        ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
        Frame.Name = "FrameText"
        Frame.Size = UDim2.fromOffset(300, 25)
        Frame.Position = UDim2.new(0.5, 0, 0.1, 0)
        Frame.AnchorPoint = Vector2.new(0.5, 0.5)
        Frame.Parent = ScreenGui
        Frame.BorderSizePixel = 1.2
        Frame.BackgroundTransparency = 0.25
        Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        Frame.BorderColor3 = Color3.fromRGB(70, 70, 70)
        Frame.Draggable = true
        TextLabel.Name = "NameLabel"
        TextLabel.Parent = Frame
        TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        TextLabel.BackgroundTransparency = 1
        TextLabel.Position = UDim2.new(0, 20, -0.00293789315, 0)
        TextLabel.Size = UDim2.new(0, 243, 0, 27)
        TextLabel.Font = Enum.Font.SourceSans
        TextLabel.Text = "Client FPS: 0 | PING: 0"
        TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
        TextLabel.TextSize = 24
        TextLabel.TextWrapped = true
        return ScreenGui, TextLabel
    end
    CalculateWinChance = function(__, __)
    end
    CheckDevice = function()
        if uis.KeyboardEnabled and not uis.TouchEnabled then
            return "PC"
        end
        if uis.TouchEnabled and not uis.KeyboardEnabled then
            return "Mobile"
        end
        if uis.KeyboardEnabled and uis.TouchEnabled then
            return "Emulator"
        end
        if uis.GamepadEnabled and not uis.TouchEnabled then
            return "Console"
        end
        return "Unknow Device"
    end
    MobileExtra = function(p13, p14, p15, p16, p17)
        local v289 = CheckDevice()
        if v289 == "Emulator" or v289 == "Mobile" then
            return p13:MakeToggle(p14, {
                Text = p15,
                Default = p16,
                Callback = function(p18)
                    p17(p18)
                end,
            })
        end
        return p13:KeybindToggle(p14, {
            Text = p15,
            Default = p16,
            Callback = function(p19)
                p17(p19)
            end,
        })
    end
    CheckTarget = function(p20)
        local Character = p20.Character
        if not p20 or not Character then
            return
        end
        return Character:FindFirstChild("HumanoidRootPart") and (Character:FindFirstChild("Humanoid") and Character.Humanoid.Health > 0)
    end
    GetPlayerState = function(p21)
        local __, result = pcall(Modules.repState.GetPlayerState, _, p21)
        return result
    end
    IsAlive = function(p22)
        local v296 = GetPlayerState(p22)
        if v296 then
            return (v296.State.Health or 0) > 0
        end
        return false
    end
    IsProtected = function(p23)
        local v298 = GetPlayerState(p23)
        if v298 then
            local ProtectionStatus = v298.State.ProtectionStatus
            return ProtectionStatus == "Protected" or ProtectionStatus == "OutlawProtected"
        end
        return false
    end
    getconstantsnc = function(...)
        local t4 = {}
        local v301 = debug.getconstants(...)
        for __, v in pairs(v301) do
            if (type(v) ~= "function" or not islclosure(v)) and typeof(v) ~= "userdata" then
                table.insert(t4, v)
            end
        end
        return t4
    end
    local function u44()
        local t5 = {}
        local Team = ESP:GetTeam(lp)
        local v306 = GetPlayerState(lp)
        local WeaponSafetyEnabled = v306.State.WeaponSafetyEnabled
        local DuelingPlayer = v306.State.DuelingPlayer
        for __, v in next, plrs:GetPlayers() do
            if v ~= lp and IsAlive(v) and not IsProtected(v) then
                local v311 = true
                local v312 = GetPlayerState(v)
                if v ~= DuelingPlayer then
                    if Settings.friendlycheck and WeaponSafetyEnabled and Team == ESP:GetTeam(v) then
                        v311 = false
                    end
                    if Settings.rbfcheck and lp:IsFriendsWith(v.UserId) then
                        v311 = false
                    end
                    local CurrentFactionId = v306.State.CurrentFactionId
                    if Settings.factioncheck and CurrentFactionId and CurrentFactionId == v312.State.CurrentFactionId and Settings.factioncheck then
                        v311 = false
                    end
                end
                if v311 then
                    t5[#t5 + 1] = v
                end
            end
        end
        return t5
    end
    MakeHighlight = function()
        local Highlight = Instance.new("Highlight", game.Workspace)
        Highlight.Name = "Highlighted_Target"
        Highlight.DepthMode = "AlwaysOnTop"
        Highlight.OutlineColor = Color3.fromRGB(0, 255, 194)
        Highlight.OutlineTransparency = 0
        Highlight.FillColor = Color3.fromRGB(166, 0, 255)
        Highlight.FillTransparency = 1
        return Highlight
    end
    local t6 = {}
    local t7 = {}
    task.spawn(function()
        local Animals = ws:WaitForChild("WORKSPACE_Entities"):WaitForChild("Animals")
        local NPCs = ws:WaitForChild("WORKSPACE_Entities"):WaitForChild("NPCs")
        local function u317(p24)
            local t8 = {}
            local t9 = {}
            local function v628(p25)
                table.insert(t9, p25)
            end
            local Model = p24:FindFirstChild("Model")
            if Model then
                local NPCTemplateNoHumanV4 = Model:FindFirstChild("NPCTemplateNoHumanV4")
                if NPCTemplateNoHumanV4 then
                    v628(p24:GetAttributeChangedSignal("Health"):Connect(function()
                        local Health = p24:GetAttribute("Health")
                        t8.health = type(Health) == "number" and Health or 0
                    end))
                    t8.head = NPCTemplateNoHumanV4:WaitForChild("Head", 10)
                    t8.health = p24:GetAttribute("Health") or 0
                    t8.body = NPCTemplateNoHumanV4
                    t8.name = p24.Name
                    table.insert(t7, t8)
                end
            elseif p24.Name == "Model" and p24:FindFirstChild("NPCTemplateNoHumanV4") then
                local NPCTemplateNoHumanV4 = p24.NPCTemplateNoHumanV4
                v628(p24:GetAttributeChangedSignal("Health"):Connect(function()
                    local Health = p24:GetAttribute("Health")
                    t8.health = type(Health) == "number" and Health or 0
                end))
                t8.head = NPCTemplateNoHumanV4:WaitForChild("Head", 10)
                t8.health = p24.Parent:GetAttribute("Health") or 0
                t8.body = NPCTemplateNoHumanV4
                t8.name = p24.Parent.Name
                table.insert(t7, t8)
            end
        end
        local function v318(p26)
            local t10 = {}
            local t11 = {}
            local function u635()
                for i2 = #t11, 1, -1 do
                    local v712 = table.remove(t11, i2)
                    if v712 then
                        v712:disconnect()
                    end
                end
            end
            local function u636()
                local v714 = table.find(t6, t10)
                if v714 then
                    table.remove(t6, v714)
                end
                u635()
            end
            local Head = p26:WaitForChild("Head", 10)
            local Health = p26:WaitForChild("Health", 10)
            if not Head or not Health then
                return
            end;
            (function(p27)
                table.insert(t11, p27)
            end)(Health:GetPropertyChangedSignal("Value"):Connect(function()
                t10.health = Health.Value
                if Health.Value <= 0 then
                    task.spawn(u636)
                end
            end))
            t10.head = Head
            t10.health = Health.Value
            t10.body = p26
            table.insert(t6, t10)
        end
        Animals.ChildAdded:Connect(v318)
        NPCs.ChildAdded:Connect(u317)
        for __, v in next, Animals:GetChildren() do
            task.spawn(v318, v)
        end
        spawn(function()
            for __, v in next, NPCs:GetChildren() do
                if v:IsA("Folder") then
                    v.ChildAdded:Connect(function(child)
                        if child:IsA("Model") and child.Name == "Model" then
                            u317(child)
                        end
                    end)
                end
            end
        end)
        for __, v in next, NPCs:GetChildren() do
            task.spawn(u317, v)
        end
    end)
    GetTarget = function()
        local p = cam.CFrame.p
        local v324 = nil
        local v325 = nil
        local v326 = nil
        local v327 = nil
        local v328 = nil
        local v329 = nil
        for __, v in pairs(u44()) do
            local v332 = v
            if ws.WORKSPACE_Entities.Players[v332.Name] then
                local v333 = Settings.targetpart and (Settings.targetpart == "Torso" and "UpperTorso") or "Head"
                local v334 = ws.WORKSPACE_Entities.Players[v332.Name]:FindFirstChild(v333)
                if v334 then
                    local v335, v336 = cam:WorldToViewportPoint(v334.Position)
                    if v336 then
                        local Magnitude = (cam.CFrame.p - v334.Position).Magnitude
                        local ray = Ray.new(p, CFrame.new(cam.CFrame.p, v334.Position).LookVector.Unit * v335.Z)
                        local PartOnRayWithIgnoreList = nil
                        if Settings.vischeck then
                            local t12 = {}
                            t12[#t12 + 1] = ws.WORKSPACE_Entities.Players[lp.Name]
                            t12[#t12 + 1] = v334.Parent
                            t12[#t12 + 1] = ws:FindFirstChild("Ignore")
                            PartOnRayWithIgnoreList = ws:FindPartOnRayWithIgnoreList(ray, t12)
                        end
                        local v341 = not PartOnRayWithIgnoreList
                        if v341 then
                            v341 = Magnitude <= (Settings.sdist or 1000)
                        end
                        if v341 then
                            local Magnitude2 = nil
                            local v343 = true
                            if Settings.silentmode == "FOV" then
                                Magnitude2 = (Vector3.new(ms.X, ms.Y + 36, 0) - Vector3.new(v335.X, v335.Y, 0)).Magnitude
                                v343 = not (Magnitude2 > u2().FOV.Radius)
                            elseif Settings.silentmode == "Closest" then
                                Magnitude2 = (p - v334.Position).Magnitude
                            end
                            if not v324 and v343 then
                                v324 = Magnitude2
                                v325 = v334
                                local __ = ws.WORKSPACE_Entities.Players[v332.Name]
                            end
                            if v343 and Magnitude2 and Magnitude2 < v324 then
                                v324 = Magnitude2
                                v325 = v334
                                local __ = ws.WORKSPACE_Entities.Players[v332.Name]
                            end
                        end
                    end
                end
            end
        end
        for i3 = 1, #t6 do
            local v347 = t6[i3]
            local head = v347.head
            if head then
                local v349, v350 = cam:WorldToViewportPoint(head.Position)
                if v350 then
                    local magnitude = (cam.CFrame.p - head.Position).magnitude
                    local ray = Ray.new(p, CFrame.new(cam.CFrame.p, head.Position).LookVector.Unit * v349.Z)
                    local PartOnRayWithIgnoreList = nil
                    if Settings.vischeck then
                        local t13 = {}
                        t13[#t13 + 1] = ws.WORKSPACE_Entities.Players[lp.Name]
                        t13[#t13 + 1] = head.Parent
                        t13[#t13 + 1] = ws:FindFirstChild("Ignore")
                        PartOnRayWithIgnoreList = ws:FindPartOnRayWithIgnoreList(ray, t13)
                    end
                    local v355 = not PartOnRayWithIgnoreList
                    if v355 then
                        v355 = magnitude <= (Settings.sdist or 1000)
                    end
                    if v355 then
                        local magnitude2 = nil
                        local v357 = true
                        if Settings.silentmode == "FOV" then
                            magnitude2 = (Vector3.new(ms.X, ms.Y + 36, 0) - Vector3.new(v349.X, v349.Y, 0)).magnitude
                            v357 = not (magnitude2 > u2().FOV.Radius)
                        elseif Settings.silentmode == "Closest" then
                            magnitude2 = (p - head.Position).magnitude
                        end
                        if not v326 and v357 then
                            v326 = magnitude2
                            v327 = head
                            local __ = v347.body
                        end
                        if v357 and magnitude2 and magnitude2 < v326 then
                            v326 = magnitude2
                            v327 = head
                            local __ = v347.body
                        end
                    end
                end
            end
        end
        for i4 = 1, #t7 do
            local v361 = t7[i4]
            local head = v361.head
            local v363 = true
            local v364 = Modules.repState.State.Bounty or 0
            if v361.name == "Elf" and v364 <= 0 then
                v363 = false
            elseif v361.Name == "EvilSnowman" and v364 >= 0 then
                v363 = false
            end
            if head and v363 and v361.health > 0 then
                local v365, v366 = cam:WorldToViewportPoint(head.Position)
                if v366 then
                    local magnitude = (cam.CFrame.p - head.Position).magnitude
                    local ray = Ray.new(p, CFrame.new(cam.CFrame.p, head.Position).LookVector.Unit * v365.Z)
                    local PartOnRayWithIgnoreList = nil
                    if Settings.vischeck then
                        local t14 = {}
                        t14[#t14 + 1] = ws.WORKSPACE_Entities.Players[lp.Name]
                        t14[#t14 + 1] = head.Parent
                        t14[#t14 + 1] = ws:FindFirstChild("Ignore")
                        PartOnRayWithIgnoreList = ws:FindPartOnRayWithIgnoreList(ray, t14)
                    end
                    local v371 = not PartOnRayWithIgnoreList
                    if v371 then
                        v371 = magnitude <= (Settings.sdist or 1000)
                    end
                    if v371 then
                        local magnitude3 = nil
                        local v373 = true
                        if Settings.silentmode == "FOV" then
                            magnitude3 = (Vector3.new(ms.X, ms.Y + 36, 0) - Vector3.new(v365.X, v365.Y, 0)).magnitude
                            v373 = not (magnitude3 > u2().FOV.Radius)
                        elseif Settings.silentmode == "Closest" then
                            magnitude3 = (p - head.Position).magnitude
                        end
                        if not v328 and v373 then
                            v328 = magnitude3
                            v329 = head
                            local __ = v361.body
                        end
                        if v373 and magnitude3 and magnitude3 < v328 then
                            v328 = magnitude3
                            v329 = head
                            local __ = v361.body
                        end
                    end
                end
            end
        end
        if Settings.spriority and type(Settings.spriority) == "table" then
            local t15 = {}
            local t16 = {
                [1] = "Entities",
                [2] = v327,
            }
            v716(t16, 3, table.find(Settings.spriority, "Entities"))
            t15[1] = t16
            local t17 = {
                [1] = "Players",
                [2] = v325,
            }
            v716(t17, 3, table.find(Settings.spriority, "Players"))
            t15[2] = t17
            local t18 = {
                [1] = "NPCs",
                [2] = v329,
            }
            v716(t18, 3, table.find(Settings.spriority, "NPCs"))
            t15[3] = t18
            table.sort(t15, function(p28, __)
                return p28[1] == table.find(Settings.spriority, p28[1])
            end)
            for i5 = 1, #t15 do
                local __, v382, v383 = unpack(t15[i5])
                if v382 and v383 then
                    return v382
                end
            end
        elseif Settings.spriority then
            if Settings.spriority == "Players" then
                return v325
            end
            if Settings.spriority == "NPCs" then
                return v329
            end
            if Settings.spriority == "Entities" then
                return v327
            end
        end
    end
    GetClosestMouseV2 = function()
        local p = cam.CFrame.p
        local v385 = nil
        local v386 = nil
        for __, v in pairs(u44()) do
            local v389 = v
            if ws.WORKSPACE_Entities.Players[v389.Name] then
                local Head = ws.WORKSPACE_Entities.Players[v389.Name]:FindFirstChild("Head")
                if Head then
                    local v391, v392 = cam:WorldToViewportPoint(Head.Position)
                    if v392 then
                        local Magnitude = (cam.CFrame.p - Head.Position).Magnitude
                        local ray = Ray.new(p, CFrame.new(cam.CFrame.p, Head.Position).LookVector.Unit * v391.Z)
                        local PartOnRayWithIgnoreList = nil
                        if Settings.vischeck then
                            local t19 = {}
                            t19[#t19 + 1] = ws.WORKSPACE_Entities.Players[lp.Name]
                            t19[#t19 + 1] = Head.Parent
                            t19[#t19 + 1] = ws:FindFirstChild("Ignore")
                            PartOnRayWithIgnoreList = ws:FindPartOnRayWithIgnoreList(ray, t19)
                        end
                        if not PartOnRayWithIgnoreList and Magnitude <= (Settings.sdist or 1000) then
                            local Magnitude3 = nil
                            local v398 = true
                            if Settings.silentmode == "FOV" then
                                Magnitude3 = (Vector3.new(ms.X, ms.Y + 36, 0) - Vector3.new(v391.X, v391.Y, 0)).Magnitude
                                v398 = not (Magnitude3 > u2().FOV.Radius)
                            elseif Settings.silentmode == "Closest" then
                                Magnitude3 = (p - Head.Position).Magnitude
                            end
                            if not v386 and v398 then
                                v386 = Magnitude3
                                v385 = Head
                                local __ = ws.WORKSPACE_Entities.Players[v389.Name]
                            end
                            if v398 and Magnitude3 and Magnitude3 < v386 then
                                v386 = Magnitude3
                                v385 = Head
                                local __ = ws.WORKSPACE_Entities.Players[v389.Name]
                            end
                        end
                    end
                end
            end
        end
        return v385
    end
    GetClosestMouse = function(p30)
        local v402 = nil
        local v403 = u2().FOV.Radius or 200
        for __, v in next, ws.WORKSPACE_Entities.Players:GetChildren() do
            local v406 = v
            if v406.Name ~= lp.Name and v406:IsA("Model") then
                local HealthProgressFrame = v406:FindFirstChild("HealthProgressFrame", true)
                local Head = v406:FindFirstChild("Head")
                if Head and HealthProgressFrame and HealthProgressFrame.Size.X.Scale * 100 > 0 then
                    local v409 = true
                    if Settings.friendlycheck and ESP:GetTeam(lp) == ESP:GetTeam(plrs[tostring(v406)]) then
                        v409 = false
                    end
                    local v410, v411 = cam.WorldToViewportPoint(cam, Head.Position)
                    if v411 and v409 then
                        local Magnitude = (Head.Position - p30).Magnitude
                        local ray = Ray.new(p30, CFrame.new(p30, Head.Position).LookVector.Unit * v410.Z)
                        local PartOnRayWithIgnoreList = nil
                        if Settings.vischeck then
                            local t20 = {}
                            t20[#t20 + 1] = ws.WORKSPACE_Entities.Players[lp.Name]
                            t20[#t20 + 1] = Head.Parent
                            t20[#t20 + 1] = ws:FindFirstChild("Ignore")
                            PartOnRayWithIgnoreList = ws:FindPartOnRayWithIgnoreList(ray, t20)
                        end
                        local v416 = not PartOnRayWithIgnoreList
                        if v416 then
                            v416 = Magnitude <= (Settings.sdist or 1000)
                        end
                        if v416 then
                            local Magnitude4 = (Vector3.new(ms.X, ms.Y + 36, 0) - Vector3.new(v410.X, v410.Y, 0)).Magnitude
                            if Magnitude4 <= v403 then
                                v403 = Magnitude4
                                v402 = Head
                            end
                        end
                    end
                end
            end
        end
        return v402
    end
    GetClosest = function(p31)
        local v419 = p31 or math.huge
        local UpperTorso = nil
        for __, v in next, ws.WORKSPACE_Entities.Players:GetChildren() do
            local v423 = v
            if v423:IsA("Model") and v423.Name ~= lp.Name and v423:FindFirstChild("UpperTorso") and ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name) then
                local v424 = ws.WORKSPACE_Entities.Players[lp.Name]
                if v424:FindFirstChild("UpperTorso") then
                    local Magnitude = (v423.UpperTorso.Position - v424.UpperTorso.Position).Magnitude
                    if Magnitude <= v419 then
                        UpperTorso = v423.UpperTorso
                        v419 = Magnitude
                    end
                end
            end
        end
        return UpperTorso
    end
    GetClosestResource = function(p32, p33)
        local v428 = nil
        local v429 = p33 or math.huge
        for __, v in next, ws.WORKSPACE_Interactables.Mining.OreDeposits:GetDescendants() do
            local v432 = v
            if string.find(v432.Name, "Ore") and v432.Parent:FindFirstChild("DepositInfo") and v432.Parent.DepositInfo:FindFirstChild("OreRemaining") and v432.Parent.DepositInfo.OreRemaining.Value ~= 0 and not v432:IsA("RayValue") then
                local Magnitude = (v432.Position - p32.HumanoidRootPart.Position).Magnitude
                if Magnitude <= v429 then
                    v428 = v432
                    v429 = Magnitude
                end
            end
        end
        return v428
    end
    Equip = function(p34)
        for __, v in next, Modules.plrData:GetContainer("Inventory").Items do
            if v.Type and string.find(v.Type:lower(), p34 or "") then
                Modules.plrCharacter:_DirectEquipItem(v)
            end
        end
    end
    GetPickaxe = function(p35)
        if not p35 then
            return false
        end
        for __, v in next, p35:GetChildren() do
            if v:IsA("Model") and not string.match(v.Name:lower(), "loadoutitem") and string.match(v.Name:lower(), "pickaxe") then
                return v
            end
        end
        return false
    end
    wwguard = function(p36, p37)
        return function(...)
            local v643 = debug.getconstants(2)
            if table.find(v643, "StackSize") then
                print("did this print?")
                return p36(...)
            end
            return p37(...)
        end
    end
    GetPositionAtTime = function(p38, p39, p40, p41)
        return p38 + p39 * p40 + 0.5 * p41 * p40 ^ 2
    end
    SolveTime = function(p42, p43, p44, p45)
        local v452 = p44 - p42
        local vector3 = Vector3.new(v452.X, 0, v452.Z)
        local v454 = vector3.Magnitude / p43
        local v455 = (v452.Y + 0.5 * p45 * v454 * v454) / v454
        local v456 = vector3.Unit * p43
        return Vector3.new(v456.X, v455, v456.Z), v454
    end
    randomVector = function(p46, p47, p48)
        return (CFrame.new(Vector3.new(), p47) * CFrame.Angles(0, 0, p46:NextNumber(0, 2 * math.pi)) * CFrame.Angles(math.acos(p46:NextNumber(math.cos(p48), 1)), 0, 0)).lookVector
    end
    getSpreadVector = function(p49, p50, p51)
        local random = Random.new(p49)
        return p50 - (randomVector(random, p50, p51) - p50)
    end
    isPartVisible = function(p52)
        local p = ws.CurrentCamera.CFrame.p
        local ray = Ray.new(p, p52.Position - p)
        local t21 = {
            [1] = ws.WORKSPACE_Entities.Players[lp.Name],
            [2] = p52.Parent,
        }
        v716(t21, 3, ws:FindFirstChild("Ignore"))
        if ws:FindPartOnRayWithIgnoreList(ray, t21) then
            return false
        end
        return true
    end
end)
local Utils = require(game:GetService("ReplicatedStorage").Modules.Utils.Utils)
local GetMouseHit = Utils.GetMouseHit
Utils.GetMouseHit = function(p53, ...)
    if type(p53) == "number" then
        p53 = math.max(p53, 5000)
    end
    return GetMouseHit(p53, ...)
end
v9(function()
    httpserv = u1(game:GetService("HttpService"))
    FindFunc = function(p54, ...)
        local t22 = {}
        v716(t22, 1, ...)
        local v470 = #t22
        local n2 = 0
        for __, v in next, p54 do
            if table.find(t22, tostring(v)) then
                n2 += 1
            end
        end
        if v470 <= n2 then
            return true
        end
        return false
    end
    task.spawn(function()
        repeat
            task.wait()
            if Network and Network.FireServer and type(Network.FireServer) == "function" then
                local FireServer = Network.FireServer
                local t23 = {}
                local function u476(p55)
                    task.wait(p55.time)
                    for __, v in next, p55.bullets do
                        local v647 = v
                        local Reference = Network:GetReference(p55.target, "CharacterPart")
                        if not p55.player or Reference then
                            FireServer(Network, "ProjectileEvent", v647, mainModule.SyncedTime:GetTime(), "Final", p55.npc and {
                                [1] = p55.target.Parent.Parent,
                                [2] = p55.target.Name,
                            } or (p55.animal and p55.target or Reference), p55.cframe:PointToObjectSpace(p55.hitPos), p55.cframe:VectorToObjectSpace(Vector3.FromNormalId(Enum.NormalId.Front)), p55.cframe:VectorToObjectSpace(p55.velocity.unit), p55.hitPos, Vector3.FromNormalId(Enum.NormalId.Front), p55.target.Material.Name)
                            task.defer(FireServer, Network, "RemoveProjectile", v647)
                            t23[v647] = nil
                        end
                    end
                end
                local function u477(p56)
                    if type(p56) == "table" then
                        for __, v in next, p56 do
                            t23[v] = true
                        end
                    end
                end
                Network.FireServer = function(p57, p58, ...)
                    local t24 = {}
                    v716(t24, 1, ...)
                    if p58 == "LowerStamina" and Settings.infStamina then
                        return
                    end
                    if (p58 == "DamageSelf" or p58 == "TrainSmack") and Settings.NoSelfDamage then
                        return
                    end
                    if if p58 ~= "CharUpdate" then p58 == "InitProjectiles" else p58 == "InitProjectiles" then
                        local EquippedItem = Modules.plrCharacter:GetEquippedItem()
                        local v656 = t24[2]
                        local v657 = type(EquippedItem) == "table" and EquippedItem.SharedData
                        local v658 = false
                        local v659 = (debug.getstack(3) or {})[2]
                        if type(v659) ~= "string" then
                            warn("projtype wrong #1", type(v659))
                        elseif not v659:find("Projectile") then
                            warn("projtype wrong #2", v659)
                        end
                        warn("got it", v659)
                        if Settings.silentAim then
                            local v660 = GetTarget()
                            if v660 and math.random(1, 100) <= (Settings.hitchance or 50) then
                                warn("silent aim-> target=", v660)
                                local v661 = v659 == "TomahawkProjectile" and 200 or v657.ProjectilePower
                                local v662 = v659 == "TomahawkProjectile" and Vector3.new(0, -150, 0) or (v657.Gravity or Vector3.new(0, -32, 0))
                                if type(v657.GravityMultiplier) == "number" then
                                    v662 *= v657.GravityMultiplier
                                end
                                if type(v656.power) == "number" and type(v656.drawStart) == "number" then
                                    local v663 = math.min(v656.power, 1)
                                    v661 = if v656.arrowType == "ExplosiveArrow" then math.max(v657.MaxPower, v663) else math.min(v657.MinPower, v663)
                                end
                                local CFrame2 = v660.CFrame
                                local Position = v660.Position
                                local origin = v656.origin
                                local v667, v668 = SolveTime(origin, v661, Position, math.abs(v662.Y))
                                if v667 then
                                    local Unit = v667.Unit
                                    local v670 = v657.ProjectileAccuracy or 1
                                    if v656.ammoType == "ShotgunRound" then
                                        v670 *= v657.ShotgunRoundAccuracy or 1
                                    end
                                    local v671 = ((v657.NumProjectiles or 1) > 1 and math.rad(10) or math.rad(12.5)) * math.clamp(1 - v670, 0, 1)
                                    if v659 ~= "TomahawkProjectile" and v659 ~= "ArrowProjectile" then
                                        v656.direction = getSpreadVector(v656.seed, Unit, v671)
                                        v656.accuracy = 1
                                    elseif v659 == "ArrowProjectile" then
                                        v656.direction = (Position - v656.origin).Unit
                                    else
                                        v656.direction = Unit
                                    end
                                    if type(v656.power) == "number" and type(v656.drawStart) ~= "number" then
                                        v656.power = 1
                                    end
                                    v658 = true
                                    if Settings.backTrack then
                                        if not not Settings.wallBang then
                                        end
                                        pass = true
                                        if pass then
                                            local part2, position = ws:FindPartOnRayWithWhitelist(Ray.new(origin, Position - origin), {
                                                [1] = v660,
                                            })
                                            part = part2
                                            table.foreach(t24[3], warn)
                                            FireServer(p57, p58, unpack(t24))
                                            u477(t24[3])
                                            task.spawn(u476, {
                                                cframe = CFrame2,
                                                hitPos = position,
                                                player = not not game.Players:GetPlayerFromCharacter(v660.Parent),
                                                animal = v660:IsDescendantOf(ws:WaitForChild("WORKSPACE_Entities"):WaitForChild("Animals")),
                                                npc = v660:IsDescendantOf(ws:WaitForChild("WORKSPACE_Entities"):WaitForChild("NPCs")),
                                                origin = origin,
                                                direction = Unit,
                                                speed = v661,
                                                velocity = Unit * v661,
                                                time = v668,
                                                startTime = mainModule.SyncedTime:GetTime(),
                                                target = v660,
                                                bullets = t24[3],
                                            })
                                            return
                                        end
                                    end
                                end
                            end
                        end
                        if not v658 and Settings.noSpread and type(EquippedItem) == "table" and type(v657) == "table" and type(v656) == "table" and v659 ~= "TomahawkProjectile" and v659 ~= "ArrowProjectile" then
                            local v674 = v657.ProjectileAccuracy or 1
                            if v656.ammoType == "ShotgunRound" then
                                v674 *= v657.ShotgunRoundAccuracy or 1
                            end
                            local v675 = ((v657.NumProjectiles or 1) > 1 and math.rad(10) or math.rad(12.5)) * math.clamp(1 - v674, 0, 1)
                            v656.accuracy = 1
                            v656.direction = getSpreadVector(v656.seed, v656.direction, v675)
                        end
                    elseif p58 == "ProjectileEvent" or p58 == "RemoveProjectile" then
                        print(debug.traceback())
                        if t23[t24[1]] then
                            return
                        end
                        if t24[3] == "Final" and t24[4] == nil then
                            return
                        end
                    end
                    return FireServer(p57, p58, unpack(t24))
                end
            end
        until Network and Network.FireServer
    end)
end)
tpsev = u1(game:GetService("TeleportService"))
togglelib = "LeftControl"
local ok3, __ = pcall(function()
    lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/olympokram/new/refs/heads/main/DefinitiveUI.lua"))()
    window = lib:Window("The Wild West Destroyer", "Version 6", "By Horizon", Color3.fromRGB(0, 255, 194), Enum.KeyCode[togglelib])
    libsky = loadstring(game:HttpGet("https://raw.githubusercontent.com/BigHacker123/skybox/main/.lua", true))()
    ESP = loadstring(game:HttpGet("https://raw.githubusercontent.com/MorryNgo/ESP-Library/refs/heads/main/Kiriot%20ESP%20Lib.lua"))()
end)
if not ok3 then
    tpsev:Teleport(2317712696, lp)
    return
end
local v17 = window:Tab("Main")
local u18 = window:Tab("Combat")
local u19 = window:Tab("Visual")
local u20 = window:Tab("Client")
local v21 = window:Tab("Horse")
local v22 = window:Tab("UI Settings")
v17:Label("Mine Aura Section")
MobileExtra(v17, "mineAura", "Mine Aura", false, function(p59)
    Settings.mineAura = p59
    local n3 = 0
    while Settings.mineAura do
        if Modules and Modules.plrCharacter then
            local EquippedItem = Modules.plrCharacter:GetEquippedItem()
            if EquippedItem and EquippedItem.Character and CheckTarget(EquippedItem) and string.find(tostring(EquippedItem.Model), "Pickaxe") and EquippedItem.IsEquipped then
                local v51 = GetClosestResource(EquippedItem.Character, 15)
                if v51 then
                    local Hitbox = EquippedItem.Hitbox
                    local HitboxCFrame = Hitbox.CFrame
                    local v54 = Hitbox.Size.X / 2
                    local v55 = HitboxCFrame * Vector3.new(v54, 0, 0)
                    local v56 = -Hitbox.CFrame.XVector
                    if tick() - n3 >= (EquippedItem.Cooldown or 1) then
                        EquippedItem:NetworkActivate("MeleeSwing", mainModule.SyncedTime:GetTime() or 0, "Swing")
                        EquippedItem:NetworkActivate("MineDeposit", mainModule.SyncedTime:GetTime() or 0, v51.Parent, v55, v56)
                        n3 = tick()
                    end
                end
            end
        end
        task.wait()
    end
end)
u18:Label("Silent Aim Section")
MobileExtra(u18, "silentAim", "Enable Silent Aim", false, function(p60)
    Settings.silentAim = p60
end)
u18:MakeDropdown("targetpart", {
    Values = {
        [1] = "Head",
        [2] = "Torso",
    },
    Multi = false,
    Text = "Target Part",
    Default = "Head",
    Callback = function(p61)
        Settings.targetpart = p61
    end,
})
u18:NewSlider("hitchance", {
    Text = "Hit Chance",
    Min = 0,
    Max = 100,
    Precise = false,
    Default = 50,
    Callback = function(p62)
        Settings.hitchance = p62
    end,
})
u18:MakeDropdown("saimmode", {
    Values = {
        [1] = "FOV",
        [2] = "Closest",
    },
    Multi = false,
    Text = "Aim Mode",
    Default = "FOV",
    Callback = function(p63)
        Settings.silentmode = p63
    end,
})
u18:NewSlider("sdistlimit", {
    Text = "Distance Limit",
    Min = 500,
    Max = 5000,
    Precise = false,
    Default = 1000,
    Callback = function(p64)
        Settings.sdist = p64
    end,
})
u18:MakeDropdown("spriority", {
    Values = {
        [1] = "NPCs",
        [2] = "Players",
        [3] = "Entities",
    },
    Multi = true,
    Text = "Target Priority",
    Default = "Players",
    Callback = function(p65)
        Settings.spriority = p65
    end,
})
v9(function()
    local v63, v64, v65, v66, v67 = MakeFrameInfo()
    local u68 = v67
    local u69 = v66
    local u70 = v65
    local u71 = v64
    local u72 = v63
    local Parent = nil
    if u72 then
        u72.Parent.Parent.Enabled = false
    end
    local n4 = 0
    u18:MakeToggle("winmeter", {
        Text = "Win Chance Meter",
        Default = false,
        Callback = function(p66)
            Settings.winmeter = p66
            local PlayerGui = lp:WaitForChild("PlayerGui")
            while Settings.winmeter do
                if not u72 or not u72.Parent or not u72.Parent.Parent then
                    if conn.connsize and conn.connsize2 and conn.connsize3 then
                        conn.connsize:Disconnect()
                        conn.connsize2:Disconnect()
                        conn.connsize3:Disconnect()
                        conn.connsize = nil
                        conn.connsize2 = nil
                        conn.connsize3 = nil
                    end
                    local v480, v481, v482, v483, v484 = MakeFrameInfo()
                    u68 = v484
                    u69 = v483
                    u70 = v482
                    u71 = v481
                    u72 = v480
                    u72.Parent.Parent.Enabled = false
                end
                local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
                local ContainerHealth = PlayerGui:FindFirstChild("ContainerHealth", true)
                if lpName and u72 and u72.Parent and ContainerHealth and tonumber(tostring(ContainerHealth.ValueText.Text):match("(%d+)")) > 0 then
                    local v487 = tostring(ContainerHealth.ValueText.Text):match("(%d+)")
                    local v488 = GetTarget()
                    if not Parent and v488 and v488.Parent then
                        Parent = v488.Parent
                    end
                    if v488 and Parent and v488.Parent and tostring(Parent) == tostring(v488.Parent) and v487 then
                        local HealthProgressFrame = v488:FindFirstChild("HealthProgressFrame", true)
                        if HealthProgressFrame then
                            u72.Text = tostring(v488.Parent)
                            u71.Text = "HP: " .. tostring(math.round(HealthProgressFrame.Size.X.Scale * 100))
                            u72.Parent.Parent.Enabled = true
                            u72.Parent.Position = UDim2.new(0.4, 50, 0.2, 0)
                            if CalculateWinChance(tonumber(v487), HealthProgressFrame.Size.X.Scale * 100) >= 50 then
                                u70.Text = "Possible Win"
                                u70.TextColor3 = Color3.fromHSV(0.44, 1, 1)
                            else
                                u70.Text = "Possible Lost"
                                u70.TextColor3 = Color3.fromRGB(255, 0, 0)
                            end
                            if HealthProgressFrame.Size.X.Scale * 100 ~= n4 then
                                local v490 = math.max(HealthProgressFrame.Size.X.Scale * 100 / 100, 0)
                                u69.Size = UDim2.fromScale(math.min(v490, 1), 1)
                                u68.Size = UDim2.fromScale(math.clamp(v490 - 1, 0, 0.8), 1)
                                n4 = HealthProgressFrame
                            end
                        end
                    elseif Parent and u72 then
                        Parent = nil
                        n4 = 0
                        u72.Parent.Parent.Enabled = false
                    end
                elseif Parent and u72 then
                    n4 = 0
                    Parent = nil
                    u72.Parent.Parent.Enabled = false
                end
                task.wait()
            end
            if Parent then
                Parent = nil
            end
            n4 = 0
            if u72 and u72.Parent and u72.Parent.Parent then
                u72.Parent.Parent:Destroy()
            end
        end,
    })
end)
v9(function()
    local Parent = nil
    local u76 = nil
    u18:MakeToggle("htargetvis", {
        Text = "Highlight Visible Target",
        Default = false,
        Callback = function(p67)
            Settings.hvistarget = p67
            while Settings.hvistarget do
                local v492 = GetTarget()
                if not Parent and v492 and v492.Parent then
                    Parent = v492.Parent
                end
                if v492 and v492.Parent and Parent and tostring(v492.Parent) == tostring(Parent) then
                    if not u76 then
                        local v493 = MakeHighlight()
                        v493.Adornee = v492.Parent
                        u76 = v493
                    end
                    if isPartVisible(v492) and u76 then
                        u76.OutlineColor = Settings.hviscolor1 or Color3.fromRGB(0, 255, 0)
                    elseif u76 then
                        u76.OutlineColor = Settings.hviscolor2 or Color3.fromRGB(255, 0, 0)
                    end
                else
                    if u76 then
                        u76:Destroy()
                        u76 = nil
                    end
                    if Parent then
                        Parent = nil
                    end
                end
                task.wait()
            end
            if Parent then
                Parent = nil
            end
            if u76 then
                u76:Destroy()
                u76 = nil
            end
        end,
    })
end)
u18:Colorpicker("vistargetc", {
    Title = "On Target Screen Highlight Color",
    Default = Color3.fromRGB(0, 255, 0),
    Callback = function(p68)
        Settings.hviscolor1 = p68
    end,
})
u18:Colorpicker("unvistargetc", {
    Title = "Off Target Screen Highlight Color",
    Default = Color3.fromRGB(255, 0, 0),
    Callback = function(p69)
        Settings.hviscolor2 = p69
    end,
})
u18:MakeToggle("fdlycheck", {
    Text = "Friendly Check",
    Default = false,
    Callback = function(p70)
        Settings.friendlycheck = p70
    end,
})
u18:MakeToggle("factioncheck", {
    Text = "Ignore Faction Members",
    Default = false,
    Callback = function(p71)
        Settings.factioncheck = p71
    end,
})
u18:MakeToggle("vischeck", {
    Text = "Visibility Check",
    Default = false,
    Callback = function(p72)
        Settings.vischeck = p72
    end,
})
u18:MakeToggle("rfcheck", {
    Text = "Roblox Friend Check",
    Default = false,
    Callback = function(p73)
        Settings.rbfcheck = p73
    end,
})
local UIHandler = require(game:GetService("ReplicatedStorage").Modules.UI.UIHandler)
local u24 = nil
u24 = hookfunction(UIHandler.GiveNotification, function(...)
    if Settings.hidenotif then
        return nil
    end
    return u24(...)
end)
u18:MakeToggle("hideerrnotif", {
    Text = "Hide Error Notification",
    Default = false,
    Callback = function(p74)
        Settings.hidenotif = p74
    end,
})
u18:MakeToggle("projtp", {
    Text = "Projectile TP",
    Default = false,
    Callback = function(p75)
        Settings.backTrack = p75
    end,
})
u18:MakeToggle("wallBang", {
    Text = "Wall Bang",
    Default = false,
    Callback = function(p76)
        Settings.wallBang = p76
        if Settings.wallBang then
            repeat
                task.wait()
                if Modules and Modules.projHandler then
                    if repst:FindFirstChild("ProjectileHandler", true) then
                        local v86 = getsenv(repst.SharedModules.World.ProjectileHandler)
                        local Raycast = v86.Raycast
                        v86.Raycast = function(...)
                            local t25 = {}
                            v716(t25, 1, ...)
                            if type(t25[1]) == "table" and t25[1].IsOwner and type(t25[4]) == "table" and Settings.wallBang then
                                table.insert(t25[4], ws.Terrain)
                                table.insert(t25[4], ws:FindFirstChild("WORKSPACE_Geometry"))
                                table.insert(t25[4], ws:FindFirstChild("WORKSPACE_Interactables"))
                                table.insert(t25[4], ws:FindFirstChild("Ignore"))
                            end
                            return Raycast(unpack(t25))
                        end
                    else
                        Library:Notify("Script Warning: Projectile Handler Module Doesn't Exist", 5, nil)
                        Toggles.wallBang:SetValue(false)
                    end
                end
            until Modules and Modules.projHandler
        end
    end,
})
v9(function()
    local t26 = {}
    local u89 = nil
    u89 = hookmetamethod(game, "__index", function(p77, p78)
        if not checkcaller() and p77 == cam and p78 == "CameraSubject" then
            if Settings.tpdynamite and t26.targetpart then
                return t26.targetpart
            end
            if not t26.targetpart then
                local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
                if lpName:FindFirstChild("Humanoid") then
                    return lpName.Humanoid
                end
            end
        end
        return u89(p77, p78)
    end)
    u18:MakeToggle("tpdynamite", {
        Text = "TP Dynamite",
        Default = false,
        Callback = function(p79)
            Settings.tpdynamite = p79
            while Settings.tpdynamite do
                local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
                if lpName and lpName:FindFirstChild("Head") and lpName:FindFirstChild("Humanoid") then
                    for __, v in next, workspace.Ignore:GetChildren() do
                        local v502 = v
                        if v502.Name == "Dynamite" and v502:IsA("Model") then
                            local PrimaryPart = v502.PrimaryPart
                            if PrimaryPart then
                                local v504 = GetTarget()
                                if v504 then
                                    PrimaryPart:PivotTo(v504.CFrame * CFrame.new(0, -8, 0))
                                    t26.targetpart = v504
                                    PrimaryPart.AssemblyLinearVelocity = Vector3.new(0, 0.001, 0)
                                    PrimaryPart.AssemblyAngularVelocity = Vector3.zero
                                end
                            elseif t26.targetpart then
                                t26.targetpart = nil
                            end
                        end
                    end
                end
                task.wait()
            end
            if t26.targetpart then
                t26.targetpart = nil
            end
        end,
    })
end)
u18:Label("Weapon Changer Section")
u18:MakeToggle("nospread", {
    Text = "No Spread",
    Default = false,
    Callback = function(p80)
        Settings.noSpread = p80
    end,
})
u18:MakeToggle("norecoil", {
    Text = "No Recoil",
    Default = false,
    Callback = function(p81)
        Settings.NoRecoil = p81
        if Settings.NoRecoil then
            repeat
                task.wait()
                if Modules and Modules.cam then
                    local cam2 = Modules.cam
                    for __, v in pairs({
                        [1] = "AddRecoil",
                        [2] = "Vibrate",
                    }) do
                        local u95 = cam2[v]
                        cam2[v] = function(...)
                            if Settings.NoRecoil then
                                return
                            end
                            return u95(...)
                        end
                    end
                end
            until Modules and Modules.cam
        end
    end,
})
u18:MakeToggle("noshootcd", {
    Text = "No Shoot Cooldown",
    Default = false,
    Callback = function(p82)
        Settings.noshootcd = p82
        if Settings.noshootcd then
            repeat
                task.wait()
                if Modules and Modules.gunitem then
                    local CanShoot = Modules.gunitem.CanShoot
                    Modules.gunitem.CanShoot = function(...)
                        if Settings.noshootcd and not Toggles.quickreload.Value then
                            return true
                        end
                        return CanShoot(...)
                    end
                end
            until Modules and Modules.gunitem
        end
    end,
})
v9(function()
    local u98 = false
    local u99 = false
    local u100 = false
    local t27 = {
        [1] = "LoadStart",
        [2] = "Load",
        [3] = "LoadEnd",
    }
    local str = nil
    local str2 = nil
    u18:MakeToggle("quickreload", {
        Text = "Quick Reload",
        Default = false,
        Callback = function(p83)
            Settings.quickReload = p83
            if Settings.quickReload then
                repeat
                    task.wait()
                    if Modules and Modules.plrCharacter then
                        local EquippedItem = Modules.plrCharacter:GetEquippedItem()
                        if EquippedItem and EquippedItem.Character and EquippedItem.IsEquipped and EquippedItem.IsGunItem and EquippedItem.Character and CheckTarget(EquippedItem) then
                            local PlayTrack = EquippedItem.PlayTrack
                            local function v508(p84, p85, ...)
                                local t28 = {}
                                v716(t28, 1, ...)
                                if Settings.quickReload then
                                    if table.find(t27, p85) and type(t28[#t28]) == "number" then
                                        t28[#t28] = t28[#t28] * 10
                                    elseif p85 == "LoadStart" then
                                        PlayTrack(p84, p85, unpack(t28))
                                        task.spawn(function()
                                            p84:StopTrack(p85, 0.05)
                                        end)
                                    end
                                end
                                return PlayTrack(p84, p85, unpack(t28))
                            end
                            if not u99 then
                                EquippedItem.PlayTrack = v508
                                str = tostring(EquippedItem.Model)
                                u99 = true
                            end
                            if not u98 and str and str ~= tostring(EquippedItem.Model) then
                                EquippedItem.PlayTrack = v508
                                str2 = tostring(EquippedItem.Model)
                                u98 = true
                            end
                            if str2 and str2 ~= tostring(EquippedItem.Model) and not u100 then
                                u100 = true
                                EquippedItem.PlayTrack = v508
                            end
                        end
                    end
                until u98 and u99 and u100 and Modules and Modules.plrCharacter or not Settings.quickReload
            end
        end,
    })
    local t29 = {
        [1] = "Aim",
        [2] = "Knock",
        [3] = "Draw",
        [4] = "Drawn",
    }
    local u105 = nil
    local PlayTrack = nil
    local u107 = nil
    passed2 = false
    u18:MakeToggle("nobowcharge", {
        Text = "Instant Bow Charge",
        Default = false,
        Callback = function(p86)
            Settings.nobowcharge = p86
            repeat
                task.wait()
                if Modules and Modules.bowitem then
                    if not u107 then
                        local StartDrawing = Modules.bowitem.StartDrawing
                        Modules.bowitem.StartDrawing = function(...)
                            local t30 = {}
                            v716(t30, 1, ...)
                            u105 = t30[1]
                            return StartDrawing(...)
                        end
                        u107 = true
                    end
                    if u105 and not passed2 then
                        local PlayTrack2 = u105.PlayTrack
                        PlayTrack = u105.PlayTrack
                        print("hooked playtrack?", u105.PlayTrack)
                        u105.PlayTrack = function(p87, p88, ...)
                            local t31 = {}
                            v716(t31, 1, ...)
                            if Settings.nobowcharge and table.find(t29, p88) and type(t31[#t31]) == "number" then
                                print("bow hoooked", "with track=", p88)
                                t31[#t31] = t31[#t31] * 100
                            end
                            return PlayTrack2(p87, p88, unpack(t31))
                        end
                        passed2 = true
                    end
                end
                task.wait()
            until Modules and Modules.bowitem and u105 and u107 and passed2 and not Settings.nobowcharge
            if u105 then
                u105.PlayTrack = PlayTrack
                PlayTrack = nil
                u105 = nil
                passed2 = nil
                u107 = nil
            end
        end,
    })
end)
u18:Label("Kill Aura Section")
MobileExtra(u18, "killAura", "Kill Aura", false, function(p89)
    Settings.killAura = p89
    while Settings.killAura do
        if Modules and Modules.plrCharacter then
            local EquippedItem = Modules.plrCharacter:GetEquippedItem()
            if EquippedItem and CheckTarget(EquippedItem) and EquippedItem.IsEquipped and (string.find(tostring(EquippedItem.Model), "Knife") or string.find(tostring(EquippedItem.Model), "Pickaxe")) then
                local v110 = GetClosest(EquippedItem.Character, 15)
                if v110 then
                    local v111 = mainModule.SyncedTime:GetTime() or 0
                    local Unit = (v110.Position - EquippedItem.Hitbox.Position).Unit
                    local v113 = -Unit
                    local Reference = Network:GetReference(v110, "CharacterPart")
                    if Reference then
                        EquippedItem:NetworkActivate("MeleeSwing", v111, "Stab")
                        EquippedItem:NetworkActivate("Melee", v111, "Stab", "Player", Reference, nil, v110.Position, Vector3.zero, v113, Unit)
                        EquippedItem:NetworkActivate("MeleeSwing", v111, "Swing")
                        EquippedItem:NetworkActivate("Melee", v111, "Swing", "Player", Reference, nil, v110.Position, Vector3.zero, v113, Unit)
                        tick()
                    end
                end
            end
        end
        task.wait()
    end
end)
u18:Label("FOV Section")
u18:MakeToggle("enableFOV", {
    Text = "Enable FOV",
    Default = false,
    Callback = function(p90)
        Settings.enablefov = p90
        while Settings.enablefov do
            if CheckDevice() == "Mobile" or CheckDevice() == "Emulator" then
                u2().FOV.Position = Vector2.new(cam.ViewportSize.X / 2, cam.ViewportSize.Y / 2)
                u2().FOV.Visible = true
            else
                u2().FOV.Position = Vector2.new(uis:GetMouseLocation().X, uis:GetMouseLocation().Y)
                u2().FOV.Visible = true
            end
            task.wait()
        end
        if u2().FOV.Visible then
            u2().FOV.Visible = false
        end
    end,
})
u18:MakeToggle("fovsnap", {
    Text = "FOV Snapline",
    Default = false,
    Callback = function(p91)
        Settings.snapline = p91
        while Settings.snapline do
            local v117 = GetTarget()
            if v117 then
                local v118, v119 = cam:WorldToViewportPoint(v117.Position)
                if v119 and u2().FOV.Visible then
                    u2().snap.From = u2().FOV.Position
                    u2().snap.To = Vector2.new(v118.X, v118.Y)
                    u2().snap.Visible = true
                else
                    u2().snap.Visible = false
                end
            else
                u2().snap.Visible = false
            end
            task.wait()
        end
        if u2().snap.Visible then
            u2().snap.Visible = false
        end
    end,
})
u18:Colorpicker("FOVColor", {
    Title = "FOV Color",
    Default = Color3.fromRGB(0, 255, 194),
    Callback = function(p92)
        u2().FOV.Color = p92
    end,
})
u18:NewSlider("FOVThickness", {
    Text = "FOV Thickness",
    Min = 0,
    Max = 10,
    Default = 0,
    Callback = function(p93)
        u2().FOV.Thickness = p93
    end,
})
u18:NewSlider("FOVNumSides", {
    Text = "FOV NumSides",
    Min = 60,
    Max = 256,
    Default = 50,
    Callback = function(p94)
        u2().FOV.NumSides = p94
    end,
})
u18:NewSlider("FOVRadius", {
    Text = "FOV Radius",
    Min = 10,
    Max = 1000,
    Default = 200,
    Callback = function(p95)
        u2().FOV.Radius = p95
    end,
})
u18:MakeToggle("FOVFilled", {
    Text = "FOV Filled",
    Default = false,
    Callback = function(p96)
        u2().FOV.Filled = p96
    end,
})
u20:Label("Character Section")
u20:MakeToggle("csprintc", {
    Text = "Client Auto Sprint",
    Default = false,
    Callback = function(p97)
        Settings.cpsprint = p97
        while Settings.cpsprint do
            if Modules and Modules.plrCharacter and not Modules.plrCharacter.IsSprintButtonDown and not Toggles.cspeedchanger.Value then
                Modules.plrCharacter.IsSprintButtonDown = true
            end
            task.wait()
        end
        if Modules and Modules.plrCharacter and Modules.plrCharacter.IsSprintButtonDown then
            Modules.plrCharacter.IsSprintButtonDown = false
        end
    end,
})
u20:MakeToggle("cspeedchanger", {
    Text = "Client Speed Changer",
    Default = false,
    Callback = function(p98)
        Settings.pspeedc = p98
        if Settings.pspeedc then
            conn.sloop = rs.PreSimulation:Connect(function(p99)
                local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
                if lpName and lpName:FindFirstChild("HumanoidRootPart") and lpName:FindFirstChild("Humanoid") then
                    local HumanoidRootPart = lpName.HumanoidRootPart
                    local MoveDirection = lpName.Humanoid.MoveDirection
                    if not lpName.HumanoidRootPart.Anchored and not Toggles.csprintc.Value and lpName.Humanoid:GetState() ~= Enum.HumanoidStateType.Climbing then
                        local v516 = MoveDirection * math.max((Settings.cspeedp or 20) - lpName.Humanoid.WalkSpeed, 0) * p99
                        HumanoidRootPart.CFrame = HumanoidRootPart.CFrame + v516
                    end
                end
            end)
        elseif conn.sloop then
            conn.sloop:Disconnect()
            conn.sloop = nil
        end
    end,
})
u20:NewSlider("chspeed", {
    Text = "Choose Speed",
    Min = 16,
    Max = 50,
    Precise = false,
    Default = 22,
    Callback = function(p100)
        Settings.cspeedp = p100
    end,
})
u20:MakeToggle("nojumpcd", {
    Text = "No jump Cooldown",
    Default = false,
    Callback = function(p101)
        Settings.nojumpcd = p101
        local PlayerGui = lp:WaitForChild("PlayerGui")
        while Settings.nojumpcd do
            local ContainerHealth = PlayerGui:FindFirstChild("ContainerHealth", true)
            if ContainerHealth and tonumber(tostring(ContainerHealth.ValueText.Text):match("(%d+)")) > 0 then
                local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
                if lpName and lpName:FindFirstChild("Humanoid") then
                    if not conn.jumpconn then
                        conn.jumpconn = getconnections(lpName.Humanoid:GetPropertyChangedSignal("Jump"))[1]
                    elseif conn.jumpconn then
                        conn.jumpconn:Disable()
                    end
                end
            elseif conn.jumpconn then
                conn.jumpconn = nil
            end
            task.wait()
        end
        if conn.jumpconn then
            conn.jumpconn:Enable()
        end
    end,
})
MobileExtra(u20, "zoomOut", "Zoom Out", false, function(p102)
    Settings.zoomin = p102
    if Settings.zoomin then
        conn.zoomin = rs.RenderStepped:Connect(function()
            local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
            if Settings.zoomin and lpName and lpName:FindFirstChild("HumanoidRootPart") then
                local HumanoidRootPart = lpName.HumanoidRootPart
                local LookVector = cam.CFrame.LookVector
                local v520 = HumanoidRootPart.Position + LookVector * 100
                cam.CFrame = CFrame.new(v520, v520 + LookVector)
            end
        end)
    elseif conn.zoomin then
        conn.zoomin:Disconnect()
        conn.zoomin = nil
    end
end)
u20:MakeToggle("infStamina", {
    Text = "Infinite Stamina",
    Default = false,
    Callback = function(p103)
        Settings.infStamina = p103
        if Settings.infStamina then
            repeat
                task.wait()
                if Modules and Modules.repState then
                    local repState = Modules.repState
                    local Stamina = repState.State.Stamina
                    setmetatable(repState.State, {
                        __index = function(__, p105)
                            if p105 == "Stamina" then
                                return Settings.infStamina and 100 or Stamina
                            end
                            return nil
                        end,
                        __newindex = function(p106, p107, p108)
                            if p107 == "Stamina" then
                                Stamina = p108
                                return
                            end
                            return rawset(p106, p107, p108)
                        end,
                    })
                    repState.State.Stamina = nil
                end
            until Modules and Modules.repState
        end
    end,
})
u20:MakeToggle("noSelfdmg", {
    Text = "No Fall Damage",
    Default = false,
    Callback = function(p109)
        Settings.NoSelfDamage = p109
    end,
})
u20:MakeToggle("noRadgoll", {
    Text = "No Radgoll",
    Default = false,
    Callback = function(p110)
        Settings.NoRagdoll = p110
        if Settings.NoRagdoll then
            repeat
                task.wait()
                if Modules and Modules.plrCharacter then
                    local Ragdoll = Modules.plrCharacter.Ragdoll
                    Modules.plrCharacter.Ragdoll = function(...)
                        if Settings.NoRagdoll then
                            return
                        end
                        return Ragdoll(...)
                    end
                end
            until Modules and Modules.plrCharacter
        end
    end,
})
u20:MakeToggle("equipeWhileswimming", {
    Text = "Equipe While Swimming",
    Default = false,
    Callback = function(p111)
        Settings.EquipWhileSwimming = p111
        if Settings.EquipWhileSwimming then
            repeat
                task.wait()
                if Modules and Modules.plrCharacter then
                    local CanSwitchToItem = Modules.plrCharacter.CanSwitchToItem
                    local Update = Modules.plrCharacter.Update
                    Modules.plrCharacter.CanSwitchToItem = function(p112, ...)
                        if Settings.EquipWhileSwimming then
                            p112.Swimming = false
                        end
                        return CanSwitchToItem(p112, ...)
                    end
                    Modules.plrCharacter.Update = function(p113, ...)
                        if Settings.EquipWhileSwimming then
                            p113.Swimming = false
                        end
                        return Update(p113, ...)
                    end
                end
            until Modules and Modules.plrCharacter
        end
    end,
})
u20:MakeToggle("autoRetrieveTomahawk", {
    Text = "Auto Retrieve Tomahawk",
    Default = false,
    Callback = function(p114)
        Settings.AutoCollectTomahawk = p114
        if Settings.AutoCollectTomahawk then
            conn.wst = ws:WaitForChild("Ignore").ChildAdded:Connect(function(child)
                if child.Name == "Tomahawk" and Settings.AutoCollectTomahawk then
                    local Handle = child:WaitForChild("Handle", 10)
                    local v530 = Handle and Handle:WaitForChild("ItemId", 10)
                    if v530 then
                        if v530.Value:len() <= 0 then
                            v530:GetPropertyChangedSignal("Value"):Wait()
                        end
                        Network:FireServer("RetrieveTomahawk", v530.Value)
                    end
                end
            end)
        end
    end,
})
u20:MakeToggle("autoGetUP", {
    Text = "Auto Get UP",
    Default = false,
    Callback = function(p115)
        Settings.AutoGetUp = p115
        while Settings.AutoGetUp do
            if Network and Modules and Modules.plrCharacter then
                local lpName = workspace.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
                if lpName and lpName:FindFirstChildOfClass("Humanoid") and lpName.Humanoid:GetState() == Enum.HumanoidStateType.Physics then
                    lpName.Humanoid:ChangeState("GettingUp")
                    Modules.plrCharacter:ToggleSelfRagdoll(false)
                    Network:InvokeServer("AttemptGetUp")
                end
            end
            task.wait()
        end
    end,
})
u20:MakeToggle("autobreakFree", {
    Text = "Auto Break Free",
    Default = false,
    Callback = function(p116)
        Settings.AutoBreakFree = p116
        if Settings.AutoBreakFree then
            repeat
                task.wait()
                if Modules and Modules.plrCharacter then
                    local BreakFreePerc = Modules.plrCharacter.BreakFreePerc
                    setmetatable(Modules.plrCharacter, {
                        __index = function(__, p118)
                            if p118 == "BreakFreePerc" then
                                return BreakFreePerc
                            end
                            return nil
                        end,
                        __newindex = function(p119, p120, p121)
                            if p120 == "BreakFreePerc" then
                                BreakFreePerc = p121
                                if Settings.AutoBreakFree and p121 > 0 then
                                    BreakFreePerc = 1
                                end
                                return
                            end
                            return rawset(p119, p120, p121)
                        end,
                    })
                    Modules.plrCharacter.BreakFreePerc = nil
                end
            until Modules and Modules.plrCharacter
        end
    end,
})
ESP:Toggle(true)
ESP.Names = true
ESP.Distance = true
ESP.Boxes = false
ESP.AutoRemove = true
v9(function()
    local u147 = nil
    task.spawn(function()
        repeat
            task.wait()
            if Modules and Modules.leaderboard then
                local leaderboard = Modules.leaderboard
                u147 = debug.getupvalues(debug.getupvalues(leaderboard.UpdatePlayers)[2].new)[1]
            end
        until Modules and Modules.leaderboard
    end)
    local function u148(p122)
        local v538 = u147[p122]
        if not v538 then
            return Color3.new(0.996078, 0.952941, 0.733333), "Law"
        end
        local State = v538.StateObject.State
        if State.CriminalStatus then
            local CriminalStatus = State.CriminalStatus
            if CriminalStatus == "Menace" then
                return Color3.fromRGB(255, 38, 38), "Outlaw"
            end
            if CriminalStatus == "Wanted" then
                return Color3.fromRGB(191, 100, 26), "Outlaw"
            end
            return Color3.fromRGB(125, 0, 0), "Outlaw"
        end
        if State.Role == "Sheriff" then
            return Color3.fromRGB(26, 92, 214), "Law"
        end
        if State.Role == "Mayor" then
            return Color3.fromRGB(255, 200, 0), "Law"
        end
        if State.Role == "Citizen" then
            return Color3.fromRGB(18, 21, 29), "Law"
        end
        if State.Role == "Law" then
            return Color3.fromRGB(0, 41, 117), "Law"
        end
        if State.Role == "Outlaw" then
            return Color3.fromRGB(191, 100, 26), "Outlaw"
        end
        if State.Role == "Skulled" then
            return Color3.fromRGB(125, 0, 0), "Outlaw"
        end
        if p122.Team and p122.Team.Name == "Lawmen" then
            return Color3.fromRGB(26, 92, 214), "Law"
        end
        return Color3.new(0.996078, 0.952941, 0.733333), "Law"
    end
    local Players = ws.WORKSPACE_Entities.Players
    local function u150(p123)
        local Head = p123:FindFirstChild("Head")
        while not Head do
            Head = p123:FindFirstChild("Head")
            task.wait(0.5)
        end
        ESP:Add(p123, {
            Type = "Model",
            Validator = function(__)
                if not Head then
                    return false
                end
                return true
            end,
            IsEnabled = function(p125)
                if not ESP.plrs then
                    return false
                end
                if (p125.PrimaryPart.CFrame.p - ws.CurrentCamera.CFrame.p).Magnitude >= (Settings.plrsdist or 500) then
                    return false
                end
                local HealthProgressFrame = p125.Object:FindFirstChild("HealthProgressFrame", true)
                if HealthProgressFrame and HealthProgressFrame.Size.X.Scale * 100 <= 0 then
                    return false
                end
                return true
            end,
            ColorDynamic = function(p126)
                local v689 = plrs[tostring(p126.Object)]
                local v690 = nil
                if u147 and u147[v689] then
                    v690 = u147[v689]
                end
                local v691, v692 = u148(v689)
                if v690 then
                    if Settings.plrrole and Settings.plrbounty then
                        p126.Name = tostring(p123) .. " [ " .. "Role: " .. (v692 or "Unknown Role") .. " ] " .. "\n\nBounty: " .. tostring(v690.State.Bounty)
                    elseif Settings.plrbounty then
                        p126.Name = tostring(p123) .. "\n\nBounty: " .. tostring(v690.State.Bounty)
                    elseif Settings.plrrole then
                        p126.Name = tostring(p123) .. " [ " .. "Role: " .. (v692 or "Unknown Role") .. " ] "
                    else
                        p126.Name = tostring(p123)
                    end
                else
                    p126.Name = tostring(p123)
                end
                return v691
            end,
        })
    end
    task.spawn(function()
        for __, v in next, Players:GetChildren() do
            if v.Name ~= lp.Name then
                u150(v)
            end
        end
    end)
    Players.ChildAdded:Connect(function(child)
        if child and child.Name ~= lp.Name then
            u150(child)
        end
    end)
    u19:MakeToggle("espplr", {
        Text = "Enable Player ESP",
        Default = false,
        Callback = function(p127)
            ESP.plrs = p127
        end,
    })
    u19:NewSlider("plrdist", {
        Text = "Player Distance",
        Min = 20,
        Max = 5000,
        Precise = false,
        Default = 500,
        Callback = function(p128)
            Settings.plrsdist = p128
        end,
    })
    u19:MakeToggle("showrole", {
        Text = "Show Player Role",
        Default = false,
        Callback = function(p129)
            Settings.plrrole = p129
        end,
    })
    u19:MakeToggle("showbounty", {
        Text = "Show Player Bounty",
        Default = false,
        Callback = function(p130)
            Settings.plrbounty = p130
        end,
    })
end)
u19:Label("Settings Section")
u19:MakeToggle("espbox", {
    Text = "Show Boxes",
    Default = false,
    Callback = function(p131)
        ESP.Boxes = p131
    end,
})
u19:MakeToggle("showtracers", {
    Text = "Show Tracers",
    Default = false,
    Callback = function(p132)
        ESP.Tracers = p132
    end,
})
u19:MakeToggle("boxfcam", {
    Text = "Boxes face the camera",
    Default = false,
    Callback = function(p133)
        ESP.FaceCamera = p133
    end,
})
u19:MakeToggle("espfcam", {
    Text = "Attach to crosshair",
    Default = false,
    Callback = function(p134)
        if p134 then
            ESP.AttachShift = 2
        else
            ESP.AttachShift = 1
        end
    end,
})
v9(function()
    local OreDeposits = ws:WaitForChild("WORKSPACE_Interactables"):WaitForChild("Mining"):WaitForChild("OreDeposits")
    local t32 = {}
    local function u157(p135)
        return p135:FindFirstChild("DepositInfo") and (p135.DepositInfo:FindFirstChild("OreRemaining") and p135.DepositInfo.OreRemaining.Value > 0)
    end
    local function v158(p136)
        if t32[p136.Name] then
            return
        end
        t32[p136.Name] = true
        while not p136:FindFirstChildOfClass("Model") do
            task.wait(0.1)
        end
        local Color = p136:FindFirstChildOfClass("Model"):WaitForChild("RockOre").Color
        ESP:AddObjectListener(p136, {
            Type = "Model",
            CustomName = p136.Name,
            IsEnabled = function(p137)
                if not ESP.ores then
                    return false
                end
                if (p137.PrimaryPart.CFrame.p - ws.CurrentCamera.CFrame.p).Magnitude >= (Settings.oredist or 500) then
                    return false
                end
                if not u157(p137.Object) then
                    return false
                end
                if not Settings.orepriority then
                    return false
                end
                return type(Settings.orepriority) == "table" and table.find(Settings.orepriority, p136.Name) or type(Settings.orepriority) == "string" and Settings.orepriority == p137.Name
            end,
            Color = Color or Color3.fromRGB(255, 255, 255),
        })
    end
    for __, child in pairs(OreDeposits:GetChildren()) do
        task.spawn(v158, child)
    end
    OreDeposits.ChildAdded:Connect(v158)
    u19:MakeToggle("oreesp", {
        Text = "Ore ESP",
        Default = false,
        Callback = function(p138)
            ESP.ores = p138
        end,
    })
    u19:NewSlider("oredist", {
        Text = "Ore Distance",
        Min = 20,
        Max = 5000,
        Precise = false,
        Default = 500,
        Callback = function(p139)
            Settings.oredist = p139
        end,
    })
    u19:MakeDropdown("orepriority", {
        Values = {
            [1] = "Coal",
            [2] = "Copper",
            [3] = "Gold",
            [4] = "Iron",
            [5] = "Limestone",
            [6] = "Quartz",
            [7] = "Silver",
            [8] = "Zinc",
            [9] = "GoldVein",
            [10] = "SilverVein",
            [11] = "IronVein",
            [12] = "CopperVein",
            [13] = "CoalVein",
        },
        Multi = true,
        Text = "Ore Priority",
        Default = "Coal",
        Callback = function(p140)
            Settings.orepriority = p140
        end,
    })
end)
v9(function()
    local CollectionService = game:GetService("CollectionService")
    local t33 = {}
    local t34 = {}
    local function v164(p141)
        t33[p141] = ESP:Add(p141, {
            Color = Color3.fromHex("209bba"),
            IsEnabled = "Thunderstruck",
            Type = "Model",
            CustomName = function(p142)
                return p142.Name .. " [Thunderstruck Object]"
            end,
        })
    end
    local function v165(p143)
        repeat
            task.wait(0.1)
        until p143.PrimaryPart
        t34[p143] = ESP:Add(p143, {
            Color = Color3.fromHex("7845d1"),
            IsEnabled = function(p144)
                if (p144.Distance or math.floor((ws.CurrentCamera.CFrame.p - p144.PrimaryPart.Position).Magnitude)) > (Settings.droppeditemdist or 500) then
                    return false
                end
                return Settings.espdroppeditems
            end,
        })
    end
    for __, v in next, CollectionService:GetTagged("Thunderstruck") do
        task.spawn(v164, v)
    end
    for __, v in next, CollectionService:GetTagged("DroppedItem") do
        task.spawn(v165, v)
    end
    CollectionService:GetInstanceAddedSignal("DroppedItem"):Connect(v165)
    CollectionService:GetInstanceRemovedSignal("DroppedItem"):Connect(function(p145)
        if t34[p145] then
            t34[p145]:Remove()
            t34[p145] = nil
        end
    end)
    CollectionService:GetInstanceAddedSignal("Thunderstruck"):Connect(v164)
    CollectionService:GetInstanceRemovedSignal("Thunderstruck"):Connect(function(p146)
        if t33[p146] then
            t33[p146]:Remove()
            t33[p146] = nil
        end
    end)
    u19:MakeToggle("droppedesp", {
        Text = "Dropped Items ESP",
        Default = false,
        Callback = function(p147)
            Settings.espdroppeditems = p147
        end,
    })
    u19:NewSlider("droppeddist", {
        Text = "Dropped Item Distance",
        Min = 20,
        Max = 5000,
        Precise = false,
        Default = 500,
        Callback = function(p148)
            Settings.droppeditemdist = p148
        end,
    })
    u19:MakeToggle("showtthunder", {
        Text = "ESP Thunderstruck",
        Default = false,
        Callback = function(p149)
            ESP.Thunderstruck = p149
        end,
    })
end)
v9(function()
    ESP:AddObjectListener(ws:WaitForChild("WORKSPACE_Entities"):WaitForChild("Animals"), {
        Type = "Model",
        IsEnabled = function(p150)
            if not ESP.ent then
                return false
            end
            if Settings.entshowlegendary and not p150.Legendary then
                return false
            end
            if not Settings.entpriority then
                return false
            end
            if math.floor((ws.CurrentCamera.CFrame.p - p150.PrimaryPart.Position).magnitude) >= (Settings.entdist or 500) then
                return false
            end
            local entpriority = Settings.entpriority
            if not Settings.entshowlegendary and type(entpriority) == "string" and entpriority ~= p150.Name then
                return false
            end
            if not Settings.entshowlegendary and type(entpriority) == "table" and not table.find(entpriority, p150.Name) then
                return false
            end
            return true
        end,
        Validator = function(p151)
            local HumanoidRootPart = p151:WaitForChild("HumanoidRootPart", 10)
            if not HumanoidRootPart then
                return false
            end
            return HumanoidRootPart
        end,
        OnAdded = function(p152)
            p152.Legendary = p152.Object:GetAttribute("Legendary")
            p152.AnimalName = p152.Object.Name
            p152.LegendaryColor = Color3.fromHex("e6e035")
            p152.BaseColor = Color3.fromRGB(139, 69, 19)
        end,
        CustomName = function(p153)
            return p153.Name .. (p153:GetAttribute("Legendary") and " [Legendary]" or "")
        end,
        ColorDynamic = function(p154)
            if p154.Legendary then
                return p154.LegendaryColor
            end
            return p154.BaseColor
        end,
    })
    u19:MakeToggle("entesp", {
        Text = "Entity ESP",
        Default = false,
        Callback = function(p155)
            ESP.ent = p155
        end,
    })
    u19:NewSlider("entdist", {
        Text = "Entity Distance",
        Min = 20,
        Max = 5000,
        Precise = false,
        Default = 500,
        Callback = function(p156)
            Settings.entdist = p156
        end,
    })
    u19:MakeToggle("entlegendary", {
        Text = "Only Show Legendary",
        Default = false,
        Callback = function(p157)
            Settings.entshowlegendary = p157
        end,
    })
    u19:MakeDropdown("entpriority", {
        Values = {
            [1] = "Horse",
            [2] = "Gator",
            [3] = "Deer",
            [4] = "Bison",
            [5] = "Bear",
            [6] = "Cow",
            [7] = "Wendigo",
        },
        Multi = true,
        Text = "Entity Priority",
        Default = "Horse",
        Callback = function(p158)
            Settings.entpriority = p158
        end,
    })
end)
v9(function()
    local NPCs = ws:WaitForChild("WORKSPACE_Entities"):WaitForChild("NPCs")
    local function u171(p159)
        local Model = p159:FindFirstChild("Model")
        if Model then
            local NPCTemplateNoHumanV4 = Model:FindFirstChild("NPCTemplateNoHumanV4")
            if NPCTemplateNoHumanV4 then
                ESP:Add(NPCTemplateNoHumanV4, {
                    Type = "Model",
                    Color = Color3.fromRGB(0, 255, 140),
                    Name = tostring(p159),
                    IsEnabled = function(p160)
                        if not ESP.NPCs then
                            return false
                        end
                        if math.floor((ws.CurrentCamera.CFrame.p - p160.PrimaryPart.Position).Magnitude) >= (Settings.npcdist or 500) then
                            return false
                        end
                        if (p160.Object.Parent.Parent:GetAttribute("Health") or 0) <= 0 then
                            return false
                        end
                        return true
                    end,
                })
            end
        elseif p159.Name == "Model" and p159:FindFirstChild("NPCTemplateNoHumanV4") then
            local NPCTemplateNoHumanV4 = p159.NPCTemplateNoHumanV4
            ESP:Add(NPCTemplateNoHumanV4, {
                Type = "Model",
                Color = Color3.fromRGB(0, 255, 140),
                Name = tostring(p159.Parent),
                IsEnabled = function(p161)
                    if not ESP.NPCs then
                        return false
                    end
                    if math.floor((ws.CurrentCamera.CFrame.p - p161.PrimaryPart.Position).Magnitude) >= (Settings.npcdist or 500) then
                        return false
                    end
                    if (p161.Object.Parent.Parent:GetAttribute("Health") or 0) <= 0 then
                        return false
                    end
                    return true
                end,
            })
        end
    end
    NPCs.ChildAdded:Connect(u171)
    spawn(function()
        for __, v in next, NPCs:GetChildren() do
            if v:IsA("Folder") then
                v.ChildAdded:Connect(function(child)
                    if child:IsA("Model") and child.Name == "Model" then
                        u171(child)
                    end
                end)
            end
        end
    end)
    for __, v in next, NPCs:GetChildren() do
        task.spawn(u171, v)
    end
    u19:MakeToggle("npcesp", {
        Text = "NPC ESP",
        Default = false,
        Callback = function(p162)
            ESP.NPCs = p162
        end,
    })
    u19:NewSlider("npcdist", {
        Text = "NPC Distance",
        Min = 20,
        Max = 5000,
        Precise = false,
        Default = 500,
        Callback = function(p163)
            Settings.npcdist = p163
        end,
    })
end)
u19:Label("Lighting Section")
utils.skyboxes = {}
local u25 = loadstring(game:HttpGet("https://raw.githubusercontent.com/BigHacker123/skybox/main/.lua", true))()
if not utils.skyboxes.cce and not lighting:FindFirstChild("Cchanger") then
    utils.skyboxes.cce = Instance.new("ColorCorrectionEffect")
    utils.skyboxes.cce.Name = "Cchanger"
    utils.skyboxes.cce.Parent = lighting
end
repeat
    task.wait()
until ws:FindFirstChildWhichIsA("Terrain")
u19:MakeToggle("DisableShadows", {
    Text = "Disable Shadows",
    Default = false,
    Callback = function(p164)
        lighting.GlobalShadows = not p164
    end,
})
u19:MakeToggle("nfog", {
    Text = "Remove Fog",
    Default = false,
    Callback = function(p165)
        local FogStart = lighting.FogStart
        if p165 then
            lighting.FogStart = 8999999488
        else
            lighting.FogStart = FogStart
        end
    end,
})
u19:MakeToggle("rclouds", {
    Text = "Remove Clouds",
    Default = false,
    Callback = function(p166)
        if p166 and (sethiddenproperty and ws.Terrain:FindFirstChild("Clouds")) then
            sethiddenproperty(ws.Terrain.Clouds, "Enabled", false)
        elseif sethiddenproperty and ws.Terrain:FindFirstChild("Clouds") then
            sethiddenproperty(ws.Terrain.Clouds, "Enabled", true)
        end
    end,
})
u19:Colorpicker("cclouds", {
    Title = "Clouds Color Changer",
    Default = ws.Terrain.Clouds.Color,
    Callback = function(p167)
        ws.Terrain.Clouds.Color = p167
    end,
})
u19:MakeToggle("ratmosphere", {
    Text = "Remove Atmosphere",
    Default = false,
    Callback = function(p168)
        Settings.ratmosphere = p168
        repeat
            task.wait()
            if lighting:FindFirstChild("Atmosphere") then
                lighting.Atmosphere:GetPropertyChangedSignal("Density"):Connect(function()
                    if Settings.ratmosphere then
                        lighting.Atmosphere.Density = 0
                    end
                end)
            end
        until lighting:FindFirstChild("Atmosphere")
    end,
})
v9(function()
    local PoisonCC = lighting:WaitForChild("PoisonCC")
    local SpurBlur = lighting:WaitForChild("SpurBlur")
    u19:MakeToggle("rpoisioneff", {
        Text = "Remove Blur Effect",
        Default = false,
        Callback = function(p169)
            Settings.removepoision = p169
            SpurBlur:GetPropertyChangedSignal("Size"):Connect(function()
                if Settings.removepoision then
                    SpurBlur.Size = 0
                end
            end)
        end,
    })
    u19:MakeToggle("rblur", {
        Text = "Remove Poison Effect",
        Default = false,
        Callback = function(p170)
            Settings.removeblur = p170
            PoisonCC:GetPropertyChangedSignal("Enabled"):Connect(function()
                if Settings.removeblur then
                    PoisonCC.Enabled = false
                end
            end)
        end,
    })
end)
v9(function()
    for __, v in next, getconnections(lighting.Changed) do
        v:Disable()
    end
    local lightingAmbient = lighting.Ambient
    local ClockTime = lighting.ClockTime
    local OutdoorAmbient = lighting.OutdoorAmbient
    local lightingBrightness = lighting.Brightness
    local ColorShift_Bottom = lighting.ColorShift_Bottom
    local ColorShift_Top = lighting.ColorShift_Top
    local FogColor = lighting.FogColor
    local EnvironmentSpecularScale = lighting.EnvironmentSpecularScale
    local EnvironmentDiffuseScale = lighting.EnvironmentDiffuseScale
    local GeographicLatitude = lighting.GeographicLatitude
    u19:MakeToggle("lightingChanger", {
        Text = "Enable Lighting Changer",
        Default = false,
        Callback = function(p171)
            Settings.lightingChanger = p171
            if Settings.lightingChanger then
                lightingAmbient = lighting.Ambient
                OutdoorAmbient = lighting.OutdoorAmbient
                lightingBrightness = lighting.Brightness
                ClockTime = lighting.ClockTime
                ColorShift_Bottom = lighting.ColorShift_Bottom
                ColorShift_Top = lighting.ColorShift_Top
                FogColor = lighting.FogColor
                EnvironmentSpecularScale = lighting.EnvironmentSpecularScale
                EnvironmentDiffuseScale = lighting.EnvironmentDiffuseScale
                GeographicLatitude = lighting.GeographicLatitude
                conn.lightningChanger = rs.RenderStepped:Connect(function()
                    lighting.Ambient = Settings.ambient or lighting.Ambient
                    lighting.OutdoorAmbient = Settings.doorambient or lighting.OutdoorAmbient
                    lighting.Brightness = Settings.brightness or lighting.Brightness
                    lighting.ColorShift_Bottom = Settings.colorshiftbotton or lighting.ColorShift_Bottom
                    lighting.ColorShift_Top = Settings.colorshifttop or lighting.ColorShift_Top
                    lighting.ClockTime = Settings.clock or lighting.ClockTime
                    lighting.FogColor = Settings.fogcolor or lighting.FogColor
                    lighting.EnvironmentSpecularScale = Settings.envspec or lighting.EnvironmentSpecularScale
                    lighting.EnvironmentDiffuseScale = Settings.envdiff or lighting.EnvironmentDiffuseScale
                    lighting.GeographicLatitude = Settings.geographiclatitude or lighting.GeographicLatitude
                end)
            else
                lighting.Ambient = lightingAmbient
                lighting.ClockTime = ClockTime
                lighting.OutdoorAmbient = OutdoorAmbient
                lighting.Brightness = lightingBrightness
                lighting.ColorShift_Bottom = ColorShift_Bottom
                lighting.ColorShift_Top = ColorShift_Top
                lighting.FogColor = FogColor
                lighting.EnvironmentSpecularScale = EnvironmentSpecularScale
                lighting.EnvironmentDiffuseScale = EnvironmentDiffuseScale
                lighting.GeographicLatitude = GeographicLatitude
                if conn.lightningChanger then
                    conn.lightningChanger:Disconnect()
                    conn.lightningChanger = nil
                end
            end
        end,
    })
end)
u19:Colorpicker("Ambient", {
    Title = "Ambient",
    Default = lighting.Ambient,
    Callback = function(p172)
        Settings.ambient = p172
    end,
})
u19:Colorpicker("ColorShift_Bottom", {
    Title = "ColorShift_Bottom",
    Default = lighting.ColorShift_Bottom,
    Callback = function(p173)
        Settings.colorshiftbotton = p173
    end,
})
u19:Colorpicker("ColorShift_Top", {
    Title = "ColorShift_Top",
    Default = lighting.ColorShift_Top,
    Callback = function(p174)
        Settings.colorshifttop = p174
    end,
})
u19:Colorpicker("OutdoorAmbient", {
    Title = "OutdoorAmbient",
    Default = lighting.OutdoorAmbient,
    Callback = function(p175)
        Settings.doorambient = p175
    end,
})
u19:Colorpicker("Fog Color", {
    Title = "Fog Color",
    Default = lighting.FogColor,
    Callback = function(p176)
        Settings.fogcolor = p176
    end,
})
u19:NewSlider("Brightness", {
    Text = "Brightness",
    Min = 0,
    Max = 10,
    Default = lighting.Brightness,
    Callback = function(p177)
        Settings.brightness = p177
    end,
})
u19:NewSlider("Time Of Day", {
    Text = "Time Of Day",
    Min = 0,
    Max = 24,
    Default = lighting.ClockTime,
    Callback = function(p178)
        Settings.clock = p178
    end,
})
u19:NewSlider("Enviroment Specular Scale", {
    Text = "Enviroment Specular Scale",
    Min = 0,
    Max = 1,
    Default = lighting.EnvironmentSpecularScale,
    Callback = function(p179)
        Settings.envspec = p179
    end,
})
u19:NewSlider("Enviroment Diffuse Scale", {
    Text = "Enviroment Diffuse Scale",
    Min = 0,
    Max = 1,
    Default = lighting.EnvironmentDiffuseScale,
    Callback = function(p180)
        Settings.envdiff = p180
    end,
})
u19:NewSlider("Geographic Latitude", {
    Text = "Geographic Latitude",
    Min = 0,
    Max = 360,
    Default = lighting.GeographicLatitude,
    Callback = function(p181)
        Settings.geographiclatitude = p181
    end,
})
if utils.skyboxes.cce then
    u19:NewSlider("Contrast", {
        Text = "Contrast",
        Min = 0,
        Max = 10,
        Default = 0,
        Callback = function(p182)
            utils.skyboxes.cce.Contrast = p182
        end,
    })
    u19:NewSlider("Saturation", {
        Text = "Saturation",
        Min = 0,
        Max = 10,
        Default = 0,
        Callback = function(p183)
            utils.skyboxes.cce.Saturation = p183
        end,
    })
end
v21:MakeToggle("hsprint", {
    Text = "Auto Horse Sprint",
    Default = false,
    Callback = function(p184)
        Settings.HorseSprint = p184
        if Settings.HorseSprint then
            repeat
                task.wait()
                if Modules and Modules.animal then
                    local Update = Modules.animal.Update
                    Modules.animal.Update = function(p185, ...)
                        if Settings.HorseSprint then
                            p185.BoostTimer = tick()
                        end
                        return Update(p185, ...)
                    end
                end
            until Modules and Modules.animal
        end
    end,
})
v21:MakeToggle("nohradgoll", {
    Text = "No Horse Ragdoll",
    Default = false,
    Callback = function(p186)
        Settings.NoHorseRagdoll = p186
        if Settings.NoHorseRagdoll then
            repeat
                task.wait()
                if Modules and Modules.animal then
                    local Ragdoll = Modules.animal.Ragdoll
                    Modules.animal.Ragdoll = function(...)
                        if Settings.NoHorseRagdoll then
                            return
                        end
                        return Ragdoll(...)
                    end
                end
            until Modules and Modules.animal
        end
    end,
})
v21:MakeToggle("nohslowdown", {
    Text = "No Water Slowdown",
    Default = false,
    Callback = function(p187)
        Settings.HorseSwim = p187
        if Settings.HorseSwim then
            repeat
                task.wait()
                if Modules and Modules.horse then
                    local ControlUpdate = Modules.horse.ControlUpdate
                    Modules.horse.ControlUpdate = function(p188, ...)
                        if Settings.HorseSwim then
                            p188.Swimming = false
                        end
                        return ControlUpdate(p188, ...)
                    end
                end
            until Modules and Modules.horse
        end
    end,
})
v21:MakeToggle("hspeedchanger", {
    Text = "Horse Speed Changer",
    Default = false,
    Callback = function(p189)
        Settings.HorseSpeed = p189
        if Settings.HorseSpeed then
            repeat
                task.wait()
                if Modules and Modules.horse then
                    local Update = Modules.horse.Update
                    Modules.horse.Update = function(p190, ...)
                        if Settings.HorseSpeed and uis:IsKeyDown(Enum.KeyCode.W) then
                            p190.WalkSpeedGoal = p190.MaxSpeed * Settings.HorseSpeedScale
                        end
                        return Update(p190, ...)
                    end
                end
            until Modules and Modules.horse
        end
    end,
})
v21:NewSlider("chspeed", {
    Text = "Choose Speed",
    Min = 0,
    Max = 5,
    Precise = true,
    Default = 2,
    Callback = function(p191)
        Settings.HorseSpeedScale = p191
    end,
})
v9(function()
    local LocalPlayer = game.Players.LocalPlayer
    local t35 = {
        [1] = "Tester",
        [2] = "Clothing Designer",
        [3] = "Contributor",
        [4] = "Developer",
        [5] = "Co-Founders",
        [6] = "Holder",
    }
    local function u217(p192, __)
        if Settings.staffalert then
            local ok4, result = pcall(p192.GetRoleInGroup, p192, 3755133)
            if ok4 then
                ok4 = table.find(t35, result)
            end
            if ok4 then
                local v594 = os.date("*t")
                v594.min = v594.min < 10 and "0" .. v594.min or v594.min
                LocalPlayer:Kick("\n[Critical Alert] Staff joined or is in your game: " .. p192.Name .. "\nRank: " .. result .. "\nAt " .. v594.hour .. ":" .. v594.min)
            end
        end
    end
    game.Players.PlayerAdded:Connect(u217)
    for __, player in pairs(game.Players:GetPlayers()) do
        coroutine.wrap(u217)(player, false)
    end
    CheckStaff = function()
        for __, player in pairs(game.Players:GetPlayers()) do
            coroutine.wrap(u217)(player, false)
        end
    end
    u20:MakeToggle("staffdetect", {
        Text = "Staff Alert",
        Default = true,
        Callback = function(p194)
            Settings.staffalert = p194
            CheckStaff()
        end,
    })
end)
u20:Label("World Section")
u20:MakeToggle("SkyboxChanger", {
    Text = "Skybox Changer",
    Default = false,
    Callback = function(p195)
        Settings.skybox = p195
        local Sky = lighting:WaitForChild("Sky")
        while Settings.skybox do
            if Sky and Settings.csky then
                if not utils.skyboxes.sky1 then
                    utils.skyboxes.sky1 = Sky:Clone()
                elseif utils.skyboxes.sky1 then
                    Sky.SkyboxBk = Settings.csky and u25[Settings.csky].SkyboxBk or u25.Neptune.SkyboxUp
                    Sky.SkyboxDn = Settings.csky and u25[Settings.csky].SkyboxDn or u25.Neptune.SkyboxUp
                    Sky.SkyboxFt = Settings.csky and u25[Settings.csky].SkyboxFt or u25.Neptune.SkyboxUp
                    Sky.SkyboxLf = Settings.csky and u25[Settings.csky].SkyboxLf or u25.Neptune.SkyboxUp
                    Sky.SkyboxRt = Settings.csky and u25[Settings.csky].SkyboxRt or u25.Neptune.SkyboxUp
                    Sky.SkyboxUp = Settings.csky and u25[Settings.csky].SkyboxUp or u25.Neptune.SkyboxUp
                end
            end
            task.wait()
        end
        if utils.skyboxes.sky1 then
            Sky:Destroy()
            utils.skyboxes.sky1.Parent = lighting
            utils.skyboxes.sky1 = nil
        end
    end,
})
u20:MakeDropdown("ChooseSky", {
    Values = {
        [1] = "Neptune",
        [2] = "Nebula",
        [3] = "Vaporwave",
        [4] = "Clouds",
        [5] = "Twilight",
        [6] = "Chill",
        [7] = "Redshift",
        [8] = "Blue Stars",
        [9] = "Blue Aurora",
    },
    Multi = false,
    Text = "Choose Sky",
    Default = "Neptune",
    Callback = function(p196)
        Settings.csky = p196
    end,
})
u20:MakeToggle("tgremover", {
    Text = "Terrain Grass Remover",
    Default = false,
    Callback = function(p197)
        if sethiddenproperty and (gethiddenproperty and gethiddenproperty(ws.Terrain, "Decoration")) then
            sethiddenproperty(ws.Terrain, "Decoration", not p197)
        elseif Toggles.tgremover.Value then
            lib:Notify("Error: Unsupported Exploit", 5, nil)
            Toggles.tgremover:SetValue(false)
        end
    end,
})
u20:Colorpicker("ChangeGrassColor", {
    Title = "Grass Color Changer",
    Default = ws.Terrain:GetMaterialColor(Enum.Material.Grass),
    Callback = function(p198)
        ws.Terrain:SetMaterialColor(Enum.Material.Grass, p198)
    end,
})
utils.materials = {}
for __, v in next, Enum.Material:GetEnumItems() do
    if v.Name ~= "Air" and v.Name ~= "Water" then
        table.insert(utils.materials, tostring(v.Name))
    end
end
u20:MakeToggle("TerrainChanger", {
    Text = "Terrain Changer",
    Default = false,
    Callback = function(p199)
        Settings.terrainchanger = p199
        while Settings.terrainchanger do
            local lpName = ws.WORKSPACE_Entities.Players:FindFirstChild(lp.Name)
            if lpName and lpName:FindFirstChild("Humanoid") and lpName.Humanoid.RootPart then
                local RootPartCFrame = lpName.Humanoid.RootPart.CFrame
                local v228 = Settings.crange or 100
                local v229 = Settings.material and Enum.Material[Settings.material] or Enum.Material.SmoothPlastic
                local v230 = Settings.mtoput and Enum.Material[Settings.mtoput] or Enum.Material.Grass
                local v231 = v228 and Vector3.new(v228, v228, v228) or Vector3.new(50, 50, 50)
                ws.Terrain:ReplaceMaterialInTransform(RootPartCFrame, v231, v229, v230)
            end
            task.wait()
        end
    end,
})
u20:NewSlider("trchooser", {
    Text = "Choose Range",
    Min = 50,
    Max = 500,
    Default = 100,
    Callback = function(p200)
        Settings.crange = p200
    end,
})
u20:MakeDropdown("MaterialToChange", {
    Values = utils.materials,
    Multi = false,
    Text = "Material To Change",
    Default = "Grass",
    Callback = function(p201)
        Settings.material = p201
    end,
})
u20:MakeDropdown("MaterialToPut", {
    Values = utils.materials,
    Multi = false,
    Text = "Material To Put",
    Default = "Ice",
    Callback = function(p202)
        Settings.mtoput = p202
    end,
})
v9(function()
    utils.oldtextures = {}
    local function u235()
        for k, v in pairs(utils.oldtextures) do
            local v600 = k
            local v601 = v
            if v600:IsA("BasePart") then
                v600.Material = v601.Material
                if v601.Decals then
                    for __, v2 in ipairs(v601.Decals) do
                        local decal = v2.decal
                        if decal then
                            decal.Texture = v2.Texture
                        end
                    end
                end
            end
        end
    end
    u20:MakeToggle("FPSBoost", {
        Text = "FPS Boost",
        Default = false,
        Callback = function(p203)
            Settings.fpsboost = p203
            local function u606(p204)
                return p204:IsDescendantOf(lp.Character) or (p204:IsA("ProximityPrompt") or p204:IsA("Attachment"))
            end
            local v607 = u1(game:GetService("MaterialService"))
            if Settings.fpsboost then
                conn.fpsboost = ws.DescendantAdded:Connect(function(descendant)
                    if descendant:IsA("ForceField") then
                        rs.Heartbeat:Wait()
                        descendant:Destroy()
                    elseif descendant:IsA("Sparkles") then
                        rs.Heartbeat:Wait()
                        descendant:Destroy()
                    elseif descendant:IsA("Smoke") or descendant:IsA("Fire") then
                        rs.Heartbeat:Wait()
                        descendant:Destroy()
                    end
                end)
                for __, child in pairs(v607:GetChildren()) do
                    child:Destroy()
                end
                v607.Use2022Materials = false;
                (function()
                    for __, descendant in ipairs(ws:GetDescendants()) do
                        local v703 = descendant
                        if v703:IsA("BasePart") and not u606(v703) then
                            if not utils.oldtextures[v703] then
                                utils.oldtextures[v703] = {
                                    Material = v703.Material,
                                }
                                if v703:FindFirstChildOfClass("Decal") then
                                    utils.oldtextures[v703].Decals = {}
                                    for __, child in ipairs(v703:GetChildren()) do
                                        local v706 = child
                                        if v706:IsA("Decal") or v706:IsA("Texture") then
                                            table.insert(utils.oldtextures[v703].Decals, {
                                                decal = v706,
                                                Texture = v706.Texture,
                                            })
                                            v706.Texture = ""
                                        end
                                    end
                                end
                            end
                            v703.Material = Enum.Material.SmoothPlastic
                        end
                    end
                end)()
            end
            while Settings.fpsboost do
                local Terrain = ws.Terrain
                if setfpscap then
                    setfpscap(120)
                end
                lighting.GlobalShadows = false
                lighting.FogEnd = 8999999488
                lighting.ShadowSoftness = 0
                if sethiddenproperty and gethiddenproperty and gethiddenproperty(ws.Terrain, "Decoration") then
                    sethiddenproperty(ws.Terrain, "Decoration", false)
                    sethiddenproperty(lighting, "Technology", 2)
                end
                Terrain.WaterWaveSize = 0
                Terrain.WaterWaveSpeed = 0
                Terrain.WaterReflectance = 0
                Terrain.WaterTransparency = 0
                lighting.GlobalShadows = false
                lighting.FogEnd = 8999999488
                lighting.ShadowSoftness = 0
                settings().Rendering.QualityLevel = 1
                settings().Rendering.MeshPartDetailLevel = Enum.MeshPartDetailLevel.Level04
                task.wait()
            end
            if conn.fpsboost then
                conn.fpsboost:Disconnect()
                conn.fpsboost = nil
            end
            if sethiddenproperty and gethiddenproperty and gethiddenproperty(ws.Terrain, "Decoration") then
                sethiddenproperty(ws.Terrain, "Decoration", true)
            end
            u235()
        end,
    })
end)
u20:Label("Misc Section")
u20:MakeToggle("AntiIdle", {
    Text = "Anti Idle & Afk",
    Default = true,
    Callback = function(p205)
        Settings.antiidle = p205
        if Settings.antiidle then
            repeat
                task.wait()
            until lp
            if #getconnections(lp.Idled) > 0 then
                for __, v in next, getconnections(lp.Idled) do
                    local v239 = v
                    if v239.Disable then
                        v239:Disable()
                    elseif v239.Disconnect then
                        v239:Disconnect()
                    end
                end
            else
                local u240 = u1(game:GetService("VirtualUser"))
                conn.Idled = lp.Idled:Connect(function()
                    u240:CaptureController()
                    u240:ClickButton2(Vector2.new())
                end)
            end
        elseif conn.Idled then
            conn.Idled:Disconnect()
            conn.Idled = nil
        end
    end,
})
v9(function()
    local v241, v242 = MakeFrameTop()
    local u243 = v242
    local u244 = v241
    u244.Enabled = false
    u20:MakeToggle("ClientInformation", {
        Text = "Client Information",
        Default = false,
        Callback = function(p206)
            Settings.cinfo = p206
            if Settings.cinfo then
                if not u244 and not u243 then
                    local v612, v613 = MakeFrameTop()
                    u243 = v613
                    u244 = v612
                end
                u244.Enabled = true
                if u244 and u243 then
                    local timestamp = tick()
                    local n5 = 0
                    local n6 = 60
                    conn.clientinfo = rs.RenderStepped:Connect(function()
                        n5 += 1
                        if tick() - timestamp >= 1 then
                            n6 = n5
                            timestamp = tick()
                            n5 = 0
                        end
                        local Value = stats.Network.ServerStatsItem["Data Ping"]:GetValue()
                        u243.Text = string.format("Client FPS: %s | PING: %s", math.floor(n6), math.floor(Value))
                    end)
                end
            else
                if u244 and u243 then
                    u244:Destroy()
                    u244 = nil
                    u243 = nil
                end
                if conn.clientinfo then
                    conn.clientinfo:Disconnect()
                    conn.clientinfo = nil
                end
            end
        end,
    })
end)
v22:Label("UI Section")
v22:Colorpicker("UI Theme", {
    Title = "UI Theme",
    Default = Color3.fromRGB(0, 255, 190),
    Callback = function(p207)
        lib:ChangePresetColor(Color3.fromRGB(p207.R * 255, p207.G * 255, p207.B * 255))
    end,
})
if CheckDevice() == "PC" or CheckDevice() == "Emulator" then
    v22:Bind("UI Keybind", {
        Text = "UI Keybind",
        Default = togglelib,
        Callback = function(p208)
            lib:ChangeBind(Enum.KeyCode[p208])
        end,
    })
end
v22:Button("Remove Title Animation", function()
    lib.AnimateText = true
end)
v22:Button("Unload UI", function()
    lib:Unload()
end)
