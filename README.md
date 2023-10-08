local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({
    Name = "push",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionTest"
})

local Tab = Window:MakeTab({
    Name = "pizza",
    Icon = "rbxassetid://4483345998",
    PremiumOnly = false
})

local Section = Tab:AddSection({
    Name = "click"
})

Tab:AddButton({
    Name = "other scripts",
    Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/YKT5w84y"))()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/ToraIsMe/ToraIsMe/main/0Push"))()
    end
})
Tab:AddButton({
    Name = "teleport to rainbow",
    Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(3417.23096, 2554.78931, -11.215847, -2.95639038e-05, 0.27556926, -0.9612813, 1, 2.95042992e-05, -2.22623348e-05, 2.22623348e-05, -0.9612813, -0.27556932)
    end
})
Tab:AddButton({
    Name = "teleport to gold",
    Callback = function()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-46.6876907, 7.55449963, 8.70124912, 0, 0, -1, 0, 1, 0, 1, 0, 0)
    end
})
local Section = Tab:AddSection({
    Name = "toggle"
})

Tab:AddToggle({
    Name = "auto hatch basic egg with delete",
    Default = false,
    Callback = function(Value)
        _G.egg = Value
        while _G.egg and wait() do
            local args = {
                [1] = "Hatch1",
                [2] = "Basic",
                [3] = {
                    ["Chicken"] = true,
                    ["Pig"] = true,
                    ["Bull"] = true,
                    ["Poodle Dog"] = true,
                    ["Dog"] = true
                }
            }
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Hatch"):FireServer(unpack(args))
        end
    end
})

Tab:AddToggle({
    Name = "auto hatch egypt egg - no commons",
    Default = false,
    Callback = function(Value)
        _G.egypt = Value
        while _G.egypt and wait() do
            local args = {
                [1] = "Hatch1",
                [2] = "Egypt",
                [3] = {
                    ["Horus"] = true,
                    ["Mummy"] = true
                }
            }

            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Hatch"):FireServer(unpack(args))
        end
    end
})


Tab:AddToggle({
    Name = "claim ugc",
    Default = false,
    Callback = function(Value)
        _G.claim = Value
        while _G.claim and task.wait(0.5) do
			game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("ClaimUGC"):FireServer()
		end
    end
})
Tab:AddToggle({
    Name = "fight pharaoh",
    Default = false,
    Callback = function(Value)
        _G.pharaoh = Value
        while _G.pharaoh and task.wait(0.5) do
                        local args = {
                [1] = workspace:WaitForChild("Map"):WaitForChild("Worlds"):WaitForChild("Ancient"):WaitForChild("Levels"):WaitForChild("Level_5"):WaitForChild("Spawner"),
                [2] = 5.373063564300537,
                [3] = "Simulate"
            }

            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Push"):FireServer(unpack(args))
		end
    end
})


Tab:AddToggle({
    Name = "fight blizzard bot",
    Default = false,
    Callback = function(Value)
        _G.blizzard = Value
        while _G.blizzard and task.wait(0.5) do
			local args = {
				[1] = workspace:WaitForChild("Map"):WaitForChild("Worlds"):WaitForChild("Icey"):WaitForChild("Levels"):WaitForChild("Level_5"):WaitForChild("Spawner"),
				[2] = 5.373063564300537,
				[3] = "Simulate"
			}

			game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Push"):FireServer(unpack(args))
		end
    end
})

OrionLib:Init()
