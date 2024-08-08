
local Players = game:GetService("Players")

-- Function to double the player's currency
local function doubleCurrency(player)
    local playerData = player:FindFirstChild("PlayerData")
    if playerData and playerData:FindFirstChild("Currency") then
        local currency = playerData.Currency.Value
        playerData.Currency.Value = currency * 2
    end
end

-- Example usage: Doubling currency when a player joins
Players.PlayerAdded:Connect(function(player)
    -- Create PlayerData and Currency if they don't exist
    local playerData = Instance.new("Folder")
    playerData.Name = "PlayerData"
    playerData.Parent = player

    local currency = Instance.new("IntValue")
    currency.Name = "Currency"
    currency.Value = 100 -- Initial currency amount
    currency.Parent = playerData

    -- Double currency as an example
    doubleCurrency(player)
end)
