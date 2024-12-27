-- Script para marcar a posição do seu personagem com uma esfera (indicador visual)
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local head = character:WaitForChild("Head")

-- Criar um indicador visual para marcar a posição
local marker = Instance.new("Part")
marker.Shape = Enum.PartType.Ball
marker.Size = Vector3.new(2, 2, 2)
marker.Color = Color3.fromRGB(255, 0, 0)  -- Cor vermelha
marker.Position = head.Position
marker.Anchored = true
marker.CanCollide = false
marker.Parent = game.Workspace

-- Atualizar a posição do marcador com o movimento do personagem
game:GetService("RunService").Heartbeat:Connect(function()
    marker.Position = head.Position
end)
