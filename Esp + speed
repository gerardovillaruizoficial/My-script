local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

local speedCoil = Instance.new("BodyVelocity")
speedCoil.MaxForce = Vector3.new(0, 500, 0)
speedCoil.Velocity = Vector3.new(0, 50, 0)

local led = Instance.new("PointLight")
led.Range = 10
led.Brightness = 1
led.Color = Color3.fromRGB(255, 0, 0)

local function onPlayerAdded(player)
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoid = character:WaitForChild("Humanoid")
    local head = character:WaitForChild("Head")

    speedCoil.Parent = humanoid.RootPart
    led.Parent = head

    local function onKeyPress(input, gameProcessed)
        if input.KeyCode == Enum.KeyCode.E and not gameProcessed then
            local players = Players:GetPlayers()
            for _, p in ipairs(players) do
                if p ~= player then
                    print(p.Name .. " is a player.")
                end
            end
        end
    end

    UserInputService.InputBegan:Connect(onKeyPress)
end

Players.PlayerAdded:Connect(onPlayerAdded)
